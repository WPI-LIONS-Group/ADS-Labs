# Real-Time Adversarial Attack on Road Sign Recognition

**Objective:**
- Conduct a real-time adversarial attack on an AI image processor to understand how autonomous vehicles can be manipulated.
- Learn about the defense mechanisms that can be applied to protect AI systems from such attacks.

## Pre-Lab Setup Instructions
Research and Familiarization (1-2 Days Before the Lab)

**Understanding Adversarial Attacks**
- Instructors should review the concept of adversarial attacks in AI, specifically how these attacks can cause AI models to misinterpret inputs, such as road signs.
- Suggested Reading:
  - [Introduction to Adversarial Attacks](https://arxiv.org/abs/1707.07397/)
  - [Cleverhans](https://cleverhans-lab.github.io/cleverhans/)

**Classroom Preparation**
- Ensure that each student or group of students has access to a computer with internet connectivity. 

## Procedure

### Step 1: Introduction (15 minutes)


**Explain Adversarial Attacks**
- Begin by explaining what adversarial attacks are and how they can trick AI models into misinterpreting data. Highlight the importance of understanding these attacks in the context of autonomous vehicles.
- Use examples to illustrate how small, seemingly insignificant changes to an image can cause AI systems to make significant errors.

**Discuss Real-World Implications**
- Discuss the potential dangers of adversarial attacks on autonomous vehicles, such as misinterpreting road signs and making incorrect decisions that could lead to accidents.

### Step 2: Setup the Lab (5-10 minutes)

- **Setup Google Colab Environment**
  - Create a new notebook in [Google Colab](https://colab.research.google.com/)
  - Install required dependencies in the code window:

```
!pip install cleverhans
!pip install -q --upgrade keras

!git clone https://github.com/WPI-LIONS-Group/Road-Sign-Image-Dataset.git
```

- **Import Libraries**

In a new code cell, copy and paste the following to import the required libraries:
```
import os
import tensorflow as tf
import numpy as np
import math
from easydict import EasyDict
from tensorflow.keras import Sequential, layers
from cleverhans.tf2.attacks.projected_gradient_descent import projected_gradient_descent
from cleverhans.tf2.attacks.fast_gradient_method import fast_gradient_method
```

For every new code block, create a new code cell and copy the contents.

### Step 3: Load the Dataset (5-10 minutes)

Using a built-in Keras function, we will load both the train and test datasets:
```
IMG_SIZE = 256

def load_ds(dirname):
    return tf.keras.utils.image_dataset_from_directory(
      dirname,
      seed=123,
      labels='inferred',
      image_size=(IMG_SIZE, IMG_SIZE),
    )

train_ds = load_ds('Road-Sign-Image-Dataset/train/')
test_ds = load_ds('Road-Sign-Image-Dataset/test/')
```

Now we will manipulate the images such that they improve the model. 
- First, we will augment the training data by mirroring the images. This doubles the size of our training data.
- Next, we will normalize the images by dividing each pixel's color by 255. An image is usually represented in code as an array of pixels, where each pixel contains a red, green, and blue value. These values range from 0 to 255, which can cause problems when training AI. By dividing each of these values by 255, each pixel is then represented by three floats ranging from 0 to 1, which is much easier for our model to understand.

```
def mirror(image, label):
    image = tf.image.flip_left_right(image)
    return image, label

train_ds = train_ds.map(mirror).concatenate(train_ds)

normalization_layer = layers.Rescaling(1./255)

train_ds = train_ds.map(lambda x, y: (normalization_layer(x), y)).shuffle(500)
test_ds = test_ds.map(lambda x, y: (normalization_layer(x), y))

data = EasyDict(train=train_ds, test=test_ds)
```

### Step 4: Train the Model (15-20 minutes)

Next, we want to train a model that can read each image and identify each output. Running the following code will take some time.

```
nb_epochs = 5
eps = 0.05
num_classes = 4

model = Sequential([
  layers.Conv2D(16, 3, padding='same', activation='relu'),
  layers.MaxPooling2D(),
  layers.Conv2D(32, 3, padding='same', activation='relu'),
  layers.MaxPooling2D(),
  layers.Conv2D(64, 3, padding='same', activation='relu'),
  layers.MaxPooling2D(),
  layers.Flatten(),
  layers.Dense(128, activation='relu'),
  layers.Dense(num_classes)
])

loss_object = tf.losses.SparseCategoricalCrossentropy(from_logits=True)
optimizer = tf.optimizers.Adam(learning_rate=0.001)

model.compile(loss=loss_object, optimizer=optimizer, metrics=['accuracy'])
model.fit(data.train, epochs=nb_epochs)
```

### Step 5: Test on Clean and Adversarial Data

Test the model on clean data
```
test_acc_clean = tf.metrics.SparseCategoricalAccuracy()

for x, y in data.test:
    y_pred = model(x)
    test_acc_clean(y, y_pred)

print(
    "test acc on clean examples (%): {:.3f}".format(test_acc_clean.result() * 100)
)
```

Now, use Cleverhans to introduce an adversarial attack on the same data.

```
test_acc_fgsm = tf.metrics.SparseCategoricalAccuracy()

for x, y in data.test:
    x_fgm = fast_gradient_method(model, x, eps, np.inf)
    y_pred_fgm = model(x_fgm)
    test_acc_fgsm(y, y_pred_fgm)

print(
    "test acc on FGM adversarial examples (%): {:.3f}".format(
        test_acc_fgsm.result() * 100
    )
)
```

Notice that there is a significant difference in accuracy before and after introducing the adversarial attack.

If you want to see individual examples of the images from the test set, use this code snippet:

```
image, label = next(iter(data.test))

figure = plt.figure(figsize=(8, 8))

y_pred = model(image)
y_pred_label = tf.argmax(y_pred, axis=1)
plt.subplot(2, 2, 1)
plt.imshow(image[0])
plt.axis('off')
plt.title(CLASS_NAMES[label[y_pred_label[0]]])

x_fgm = fast_gradient_method(model, image, eps, np.inf)
y_pred_fgm = model(x_fgm)
y_pred_fgm_label = tf.argmax(y_pred_fgm, axis=1)
plt.subplot(2, 2, 2)
plt.imshow(x_fgm[0])
plt.axis('off')
plt.title(CLASS_NAMES[label[y_pred_fgm_label[0]]])

plt.show()
```

Note that the original model will often have the wrong label since it will have an accuracy lower than 80%.

## Discussion Points
- How do adversarial attacks exploit vulnerabilities in AI image recognition systems?
- What are the potential consequences of such attacks in the context of autonomous vehicles?
- What strategies can be employed to protect AI systems from adversarial attacks?

## Expected Learning Outcomes
- Students will gain hands-on experience with adversarial attacks on AI systems and understand the risks involved in AI misinterpretation.
- Students will learn about the importance of robust AI models in ensuring the safety of autonomous vehicles.
- Students will engage in critical thinking about the role of cybersecurity in AI and the real-world implications of AI vulnerabilities.

## Sources for Further Reading
- [Adversarial Attacks on AI](https://www.forbes.com/sites/forbestechcouncil/2023/07/27/adversarial-attacks-on-ai-systems/)
- [TensorFlow for AI Model Training](https://www.tensorflow.org/)