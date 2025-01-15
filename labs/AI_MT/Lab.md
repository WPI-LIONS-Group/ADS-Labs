# Interactive Road Sign Recognition Simulation

**Objective:**
- Simulate how AI-based image processors in autonomous vehicles recognize and interpret road signs.
- Explore the vulnerabilities in AI systems when exposed to adversarial examples and understand the implications for autonomous driving systems.

## Pre-Lab Setup Instructions
Research and Familiarization (1-2 Days Before the Lab)

**Understanding AI Image Recognition**
- Instructors should review the basics of how AI image recognition works, especially in the context of autonomous vehicles. Focus on how these systems use machine learning models to identify and interpret road signs.
- Suggested Reading:
  - [Basics of AI Image Recognition](https://viso.ai/computer-vision/image-recognition/)
  - [AI in Autonomous Vehicles](https://scienceexchange.caltech.edu/topics/artificial-intelligence-research/autonomous-ai-cars-drones)

**Classroom Preparation**
- Ensure that each student or group of students has access to a computer with internet connectivity.

## Procedure

### Step 1: Introduction (10 minutes)

**Explain AI Image Processing in Autonomous Vehicles**
- Begin by discussing the role of AI in autonomous vehicles, specifically how image processors are trained to recognize road signs and other visual cues.
- Emphasize the importance of accurate road sign recognition for the safety and functionality of autonomous vehicles.

**Introduce Adversarial Attacks**
- Explain how adversarial attacks work, focusing on how subtle changes to an image can trick AI systems into making incorrect classifications. Discuss potential real-world dangers, such as misinterpreting a stop sign as a yield sign.

### Step 2: Road Sign Recognition Simulation (20 minutes)

**Set Up the Simulation**
- Access [Google's Teachable Machine](https://teachablemachine.withgoogle.com/train/image) 
- Download the [image dataset](../AI_HT/images/)
- Demonstrate how the tool processes and recognizes these images, and explain the underlying machine learning principles.

**Run the Initial Simulation**
- Have students create 4 classes: Crosswalk, Speed Limit, Stop Sign, and Traffic Light.
- Upload the contents of each folder to its corresponding class. (Do not upload the test folder)
- Train the model with only 5 epochs. 
  - Click on advanced, then change the Epochs from 50 to 5.
  - This will save time and make it easier to introduce adversarial alterations to the images.
- Test the model with unaltered road sign images from the test folder and record how the AI recognizes each sign.
- Discuss the accuracy of the AI's initial interpretations and why these results are as expected.

**Introduce Adversarial Examples**
- Have students to introduce alterations to the road sign images (e.g., adding noise, blurring, or slight color changes).
- Test the model with these modified images and observe how the AI system’s recognition accuracy is affected.

### Step 3: Analysis and Discussion (20 minutes)
**Group Analysis**
- Break students into small groups to analyze how the AI’s recognition accuracy changed with the introduction of adversarial examples.
- Encourage students to hypothesize why the AI was tricked and what that implies for real-world autonomous systems.

**Present Findings**
- Each group presents their findings, including specific changes made to the road sign images, the AI’s response, and the potential impact on an autonomous vehicle’s behavior.

**Discuss Defense Mechanisms:**
- Conclude with a discussion on how AI systems can be trained or designed to be more resilient to adversarial attacks. 
- Explore ideas such as training with more diverse datasets, incorporating multiple sensors, and using robust AI models.

## Discussion Points
- How do adversarial examples affect the accuracy of AI image recognition?
- What are the implications of AI misinterpreting road signs in autonomous vehicles?
- What strategies can be employed to make AI systems more resilient to adversarial attacks?

## Expected Learning Outcomes
- Students will gain hands-on experience with AI image processing and how it is applied in autonomous vehicles.
- Students will learn about the vulnerabilities of AI systems to adversarial attacks and understand the potential consequences.
- Students will engage in critical thinking about the importance of robust AI systems in ensuring safety in real-world applications.

## Sources for Further Reading
- [Adversarial Examples in AI](https://arxiv.org/abs/1412.6572)
- [Teachable Machine](https://teachablemachine.withgoogle.com/)

This lab guide provides a structured approach for students to interactively explore how AI systems recognize road signs and the impact of adversarial attacks on these systems. The pre-lab setup ensures that both instructors and students are prepared for a meaningful and educational experience.


