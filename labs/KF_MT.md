# Real-World Key Fob Cloning and Hacking Using Flipper Zero

**Objective:**
- Demonstrate how key fob cloning works using a Flipper Zero device.
- Explore real-world hacking scenarios and understand the security vulnerabilities of key fobs.
- Learn the practical techniques used by hackers and the defense mechanisms that can prevent such attacks.

## Materials Needed
- **Flipper Zero Device**
  - A versatile tool for hacking, including the ability to read, analyze, and clone RFID signals.
  - Purchase Link: https://shop.flipperzero.one/
- **Pre-programmed RFID Key Fobs**
  - Blank RFID key fobs that can be programmed with different signals. These will be the targets for your cloning efforts.
  - Purchase Link: [Amazon](https://www.amazon.com/ETEKJOY-Writable-Proximity-Rewritable-Universal/dp/B07GBSP8SD/ref=sr_1_1?dib=eyJ2IjoiMSJ9.zUDykFIb6r6931hbllXcAU-EGtkSaq7kJc03mga5IIimW_7U0-iAwU889yg9oFzuyTqFFaNNdTV6HBG0AoSGcIyPrNBsiJ1prW_7HngX5dUXx0wZgEQwvUuHJ5c9fVASSs6FP0DMMZY3ZtilpD1brX9Dxd8bNUX3yA9hKTVqptlhH72cMCFLsHYR2rqQX0oy0t7jY8fHqhTO63hVvC8eqaQdzcqY4tJcyB8VI8vKvBo.n0-MfyeY4eShWP6tpLL-8qfb7xQIfpjRHt5Nlw9eg-c&dib_tag=se&keywords=Blank%2BRFID%2Bkey%2Bfobs&qid=1722564307&sr=8-1&th=1)
- **Laptop (Optional)**
  - A laptop may be used for advanced configuration and analysis using the Flipper Zero desktop software or for logging the activities.
  - Flipper Zero Desktop Software: https://flipperzero.one/update
- **Secure Environment for Testing**
  - A controlled environment to ensure that the cloned key fobs are not used maliciously and are purely for educational purposes.
- **Reference Material**
  - Documentation on using the Flipper Zero and understanding RFID technology.
  - Flipper Zero Documentation: https://docs.flipperzero.one/

## Before the Lab: Preparatory Steps

### Step 1: Research and Familiarization (1-2 Days Before the Lab)

- **Understanding RFID Technology**
  - Instructors should review basic concepts of RFID (Radio Frequency Identification) technology, how it is used in automotive key fobs, and its common vulnerabilities.
  - [RFID Overview: Beginner’s Guide](https://www.atlasrfidstore.com/rfid-resources/rfid-beginners-guide/?srsltid=AfmBOortVin03SMbpD40Y6Uq1DhLnGUhWwk5o9ge2xT3xmEQO-SYkRwA)
  - [Automotive Key Fob Technology](https://auto.howstuffworks.com/remote-entry2.htm)
- **Familiarize with Flipper Zero**
  - Instructors and students should explore the functionalities of the Flipper Zero device. This includes reading the user manual and watching tutorials.
  - [Getting Started with Flipper Zero](https://www.youtube.com/watch?v=rENJknlWq9o)
- **Download and Install Necessary Software**
  - Ensure that the latest firmware is installed on the Flipper Zero device.
  - Download and install the Flipper Zero desktop software on the laptop (s), if needed, for additional functionalities.
  - Software Download: https://flipperzero.one/update
- **Gather Materials and Setup Environment**
  - Prepare all the necessary materials, including the RFID key fobs and any additional accessories.
  - Set up a secure environment for conducting the lab, ensuring that no unauthorized access to the cloned key fobs occurs.
- **Setup Key Fobs**
  - Make sure to use the Flipper Zero to write a signal on a few blank key fobs. 
  - First, go to the *125 kHz RFID* menu and create an RFID signal with the *Add Manually* option. Then choose a type and create an ID. 
  - Now go back to the *125 kHz RFID* menu and go to *Saved*. Choose the RFID that was created and choose *Write*.
  - Finally, place a blank key fob underneath the Flipper Zero until a *Success!* message is displayed. 

### Step 2: Ethical Considerations and Legal Framework (1 Day Before the Lab)
- **Discuss Ethical Implications**
  - Instructors should lead a discussion about the ethical responsibilities involved in learning and practicing cybersecurity techniques. Emphasize the importance of using these skills for good and within the bounds of the law.
  - Suggested Reading: [Ethics in Cybersecurity](https://www.futureoftech.org/cybersecurity/4-ethical-issues-in-cybersecurity/)
- **Review Legal Aspects**
  - Students should be made aware of the legal boundaries related to hacking activities, especially in regard to RFID technology and key fob cloning.
  - Suggested Reading: [Legal Issues in Hacking](https://dallolaw.com/news/computer-hacking-laws-and-punishments/#:~:text=The%20Computer%20Fraud%20and%20Abuse%20Act%20(CFAA)%20is%20the%20most,system%20for%20an%20unlawful%20purpose.)
- **Pre-Lab Quiz (Optional)**
  - Administer a short quiz to assess students' understanding of RFID technology, the Flipper Zero device, and ethical hacking principles. This ensures they are prepared for the hands-on lab activity.

## Procedure

### Step 1: Introduction (10-15 minutes)

- **Overview of RFID Technology**
  - Begin by explaining what RFID (Radio Frequency Identification) technology is and how it is used in key fobs for cars. Describe how the RFID chip inside the fob stores a unique code that communicates with the vehicle’s receiver.
  - Discuss the importance of securing these signals to prevent unauthorized access and vehicle theft.
- **Introduction to Flipper Zero**
  - Introduce the Flipper Zero device, explaining its capabilities and how it can be used for ethical hacking and educational purposes.

### Step 2: Setting Up the Flipper Zero (10-15 minutes)
- **Powering On and Basic Setup**
  - Turn on the Flipper Zero device. Ensure that it is fully charged and updated with the latest firmware.
  - Familiarize yourself with the interface by navigating through the menu to find the RFID options.
- **Initializing the RFID Reader**
  - Navigate to the *125 kHz RFID* menu on the Flipper Zero and select the *Read* option. Ensure that the device is ready to capture data from an RFID key fob.

### Step 3: Reading the RFID Signal (5-10 minutes)
- **Capture the Signal**
  - Place the pre-programmed RFID key fob near the Flipper Zero’s RFID reader.
  - Wait for the device to read the signal.
- **Analyzing the Captured Data**
  - Review the captured data. The Flipper Zero will typically display the unique identifier and other information associated with the RFID key fob.
  - Click *More*, then *Save* to save the RFID signal.

### Step 4: Cloning the Signal (5-10 minutes)
- **Writing the Signal to a Blank Fob**
  - In the *125 kHz RFID* menu, choose the *Saved* option.
  - Select the signal that was just saved, then choose *Write*.
  - Put a blank key fob behind the Flipper Zero until a success message is displayed.
- **Verification**
  - After cloning, use the Flipper Zero to verify that the blank fob now carries the same signal as the original. This can be done by reading the cloned fob and comparing its data to the original.

### Step 5: Testing the Cloned Fob (15-20 minutes)
- **Simulated Environment**
  - Set up a simulated environment where the cloned key fob can be tested to unlock or start a vehicle system (if available). If a vehicle is not available, simulate the communication process using the Flipper Zero.
- **Testing**
  - Use the cloned key fob in the simulation to see if it successfully mimics the original fob’s functions, such as unlocking a door or starting the ignition.

### Step 6: Defense Mechanisms and Discussion (15-20 minutes)
- **Discuss Security Vulnerabilities**
  - Discuss how easy it was to clone the key fob and the implications of this vulnerability in real-world scenarios. Explore how attackers can exploit this vulnerability and what the consequences might be.
- **Introduce Defense Mechanisms**
  - Explore different methods to prevent such cloning attacks, including rolling codes, encryption, and physical protection measures like Faraday pouches.
  - Discuss how these defense measures can be implemented in modern vehicles to prevent unauthorized access.
- **Role of AI in Enhancing Security**
  - Discuss how AI can be used to detect anomalies in key fob usage patterns and implement adaptive security measures.

### Step 7: Conclusion (10 minutes)
- **Summary**
  - Recap the key lessons learned from the lab, including the steps involved in cloning an RFID signal and the importance of implementing robust security measures.
- **Reflection**
  - Encourage students to reflect on the importance of cybersecurity in protecting personal and property safety, and the ethical implications of hacking knowledge.

## Expected Learning Outcomes
- Students will understand the basic operation of RFID technology in key fobs.
- Students will gain practical experience in reading, cloning, and testing RFID signals using the Flipper Zero.
- Students will learn about the vulnerabilities of key fob systems and explore methods to defend against such attacks.

## Sources for Further Reading:
- Flipper Zero Documentation: https://docs.flipperzero.one/
- [Automotive Cybersecurity: A Review of 2023](https://www.eetimes.com/automotive-cybersecurity-a-review-of-2023/)
- Proxmark3 RFID Hacking Tool: https://proxmark.com/
- [Video - Flipper Zero  Key Fob Hacking](https://www.youtube.com/watch?v=HwdoHMVKTpU)

This lab guide provides a structured approach to learning about RFID key fob cloning, with a strong emphasis on ethical considerations and the responsible use of cybersecurity knowledge.
