# Designing a Smart Key Fob Prototype

**Objective:**
- Understand the components and functionality of a key fob.
- Explore potential vulnerabilities and security measures for automotive key fobs.

## Materials Needed:

- **Paper:**
  - White A4 or Letter-sized sheets for sketching designs.
  - Colored construction paper for creating a 3D model (optional).
- **Markers and Colored Pencils:**
  - Black, blue, red, and green markers for outlining and labeling.
  - Colored pencils or markers for adding details and color coding.
- **Scissors and Glue:**
  - Scissors for cutting out paper components.
  - Glue stick for assembling paper models.
- **Cardboard:**
  - Thick cardboard for creating a durable model base.
  - You can use recycled cardboard from cereal boxes or similar packaging.
- **Ruler:**
  - For measuring and creating straight lines during design and construction.
- **Printed Diagrams of Key Fobs:**
  - Printouts of various key fob designs for reference and inspiration.
  - Images can be found through a simple web search or automotive manuals.
- **Reference Material:**
  - Diagrams and articles explaining key fob technology and vulnerabilities (for teacher reference).
    - https://electronics.stackexchange.com/questions/395936/how-does-a-car-with-keyless-entry-know-where-the-key-is?newreg=4c0744a580274d72a3760fb2d082ec16
    - https://www.researchgate.net/figure/Remote-keyless-entry-for-vehicles_fig2_301443740
    - https://www.autopi.io/blog/what-is-a-key-fob/

## Preparation Before the Lab:
- **Research and Print:**
  - Collect and print several diagrams of key fobs, both basic and advanced models, for students to examine. Ensure these include labeled components like buttons, circuit boards, batteries, and RFID chips.
  - Video: https://www.youtube.com/watch?v=65mhS73_keY
  - Basic: https://misterminit.co/cdn/shop/files/car-key-diagram_900x.png?v=1651188322
  - Detailed: https://www.electronics-project-design.com/KeylessLock.html
- **Setup Workstations:**
  - Set up workstations with all the materials listed above. Ensure each station has a ruler, scissors, markers, and at least one printed diagram for reference.

## Detailed Procedure:

### Step 1: Introduction (10 minutes)

- **Explain the Basics:**
  - Begin by introducing the key fob as a small, handheld device used to remotely control a vehicle's locks, alarm, and sometimes even the ignition. Explain how key fobs use RFID technology to communicate with the vehicle. Show video. 
- **Discuss Vulnerabilities:**
  - Briefly discuss how key fobs can be vulnerable to hacking, such as signal interception and replay attacks, primarily signal interception and replay attacks.
  - **Signal Interception:**
    - Key fobs communicate with the vehicle using radio frequency (RF) signals, typically through RFID technology. These signals can be intercepted by attackers using relatively inexpensive and readily available equipment.
    - Once intercepted, the signal can be recorded, and the attacker can use it to unlock or start the vehicle at a later time. This is often referred to as a "relay attack," where the signal is captured and relayed to the vehicle even if the key fob is far away.
  - **Replay Attacks:**
    - In a replay attack, the attacker captures the signal transmitted by the key fob when a legitimate action, like unlocking the car, is performed. The attacker then retransmits this signal to the car to unlock it at a later time.
    - These attacks exploit the fact that many key fobs do not use sophisticated encryption methods, allowing the signal to be easily replicated.
  - Emphasize the importance of securing these devices.
    - The importance of securing key fobs cannot be overstated, as they are the primary access control mechanism for many vehicles. If compromised, attackers can gain unauthorized access to the vehicle, leading to potential theft or tampering. To mitigate these risks, manufacturers and users should consider the following security measures:
    - **Rolling Code Encryption:** This method changes the signal each time the key fob is used, making it much harder for attackers to reuse intercepted signals.
    - **Faraday Pouches:** These are simple and affordable solutions that block RF signals, preventing signal interception when the key fob is not in use.
    - **Multi-Factor Authentication:** Adding additional verification steps before the vehicle can be unlocked or started can significantly enhance security.

### Step 2: Design Phase (20-25 minutes)

- **Brainstorming:**
  - Ask students to think about the essential features of a key fob, including buttons for lock/unlock, trunk release, and possibly remote start. Encourage them to consider advanced features like biometric authentication or GPS tracking.
- **Sketching the Design:**
  - Students will start by sketching their key fob design on paper. They should outline where each button will be placed, label each component, and consider the internal layout, including where the circuit board, battery, and RFID chip will go.
  - Encourage students to use different colors to represent different components and features.
- **Building the Model (Optional):**
  - Using cardboard, students can cut out and assemble a 3D model of their key fob. This hands-on activity helps them think more deeply about the physical design and placement of components.
  - Glue the pieces together to form the key fob, ensuring it is sturdy enough to be handled.

### Step 3: Vulnerability Assessment (15-20 minutes)
- **Identify Vulnerabilities:**
  - Once the design is complete, ask students to identify potential security vulnerabilities in their key fob. They should consider questions like:
    - Could the signal be intercepted?
    - How secure is the button configuration?
    - Is the fob susceptible to physical tampering?
- **Discussion:**
  - Facilitate a class discussion where students share their designs and discuss potential vulnerabilities. Use this time to introduce concepts like encryption, signal jamming, and replay attacks.

### Step 4: Defense Mechanism Discussion (15 minutes)

- **Security Features:**
  - Discuss with the students the various defense mechanisms that can be implemented in their key fob designs. This could include encryption of signals, use of rolling codes, biometric authentication, or multi-factor authentication.
- **Modify Designs:**
  - Allow students to modify their designs based on the discussion. They can add labels or notes indicating where additional security features would be implemented.

### Step 5: Conclusion and Presentation (10 minutes)

- **Present Designs:**
  - Have students present their final designs to the class, explaining their features and how they have addressed potential vulnerabilities.
- **Reflection:**
  - Conclude with a reflection on what they have learned about key fob technology, its vulnerabilities, and the importance of cybersecurity in everyday objects.

## Expected Learning Outcomes:
- Students will understand the basic components and functionalities of a key fob.
- Students will be able to identify potential security vulnerabilities in key fob designs.
- Students will develop solutions to improve the security of their key fob designs, incorporating concepts such as encryption and multi-factor authentication.

## References for Further Reading/Viewing:
- [Wired - Tesla Model X Hack](https://www.wired.com/story/tesla-ultra-wideband-radio-relay-attacks/)
- [Car Scoops -  Hackers Don’t Need Skills](https://www.carscoops.com/2024/03/thieves-can-now-exploit-keyless-entry-security-lapses-automakers-have-known-about-for-years/)
- [Video  - AAA warns car owners that key fobs are vulnerable to hacking](https://www.youtube.com/watch?v=lmLHAAc-UHk)

This detailed procedure ensures that students not only engage creatively with the material but also critically analyze the importance of cybersecurity in everyday technology.

