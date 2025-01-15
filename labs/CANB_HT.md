# Hacking the CAN Bus in Kali Linux

**Objective:**
- Simulate how autonomous vehicles communicate internally via the CAN Bus.
- Explore a simple adversarial attack on the CAN Bus.

## Pre-Lab Setup Instructions
Research and Familiarization (1-2 Days Before the Lab)

**Understanding the CAN Bus**
- Instructors should review the basics of how the CAN Bus works in autonomous vehicles.
- Suggested Reading:
  - [CAN Bus Explained - A Simple Intro](https://www.csselectronics.com/pages/can-bus-simple-intro-tutorial/)
  - [CAN Bus for Beginners: Everything You Need to Know](https://www.autopi.io/blog/can-bus-explained/)

**Classroom Preparation**
- Ensure that each student or group of students has access to a computer with internet connectivity.
- Install [VirtualBox](https://www.virtualbox.org/) on each student's computer.
- Download a fresh installation of [Kali Linux](https://www.kali.org/get-kali/#kali-virtual-machines).
- Download the [ISO file](https://github.com/WPI-LIONS-Group/ADS-Labs/releases/tag/v0.0.1) for this lab.

## Procedure

### Step 1: Introduction (15 minutes)

**Introduce the CAN Bus**
- Begin by discussing the CAN Bus in autonomous vehicles.
- Show this [wireframe of a car](https://www.tinkercad.com/things/adX3NKWnNtG-glorious-curcan/edit?sharecode=MVYOMvBuhvksoCXYeCq7BZpgEiGqx4a9Eiq0rYggdns) to describe how the CAN Bus works.

**Explain the goal of the lab**
- Explain what a replay attack is and how students will perform this lab.
- Mention that this lab should only be performed in a simulated environment.

### Step 2: Setup the Lab (20-30 minutes)

- **Creating the environment**
  - Launch VirtualBox
  - Click *Add*, then open the file named "kali-linux-2024.4-virtualbox-amd64-1.16.vbox".
  - Now click *Settings*, go to *Storage*, and under Devices click the icon for *Add Attachment* and select *Optical Drive*.
  - In the next popup menu click *Add* and open the file named "Car_Hacking_Lab.iso".
  - Now select the ISO file and click *Choose*, then click *OK* to close out of final popup.
- **Software setup**
  - Launch the virtual machine by selecting *Start*. Wait for the machine to startup and login with the username "kali" and password "kali"
  - Copy the contents of the ISO file to the desktop.
  - Open a terminal and run ```sudo apt-get update``` then follow the prompts to update the VM.
  - After the first command completes, run ```sudo apt-get install can-utils``` until completion.
  - In the terminal, navigate to the "ICSim" directory by typing ```cd Desktop/Car_Hacking/ICSim```
  - Launch the simulator by typing ```./setup_vcan.sh``` then ```./icsim vcan0```
  - Open a new terminal tab and type ```./controls vcan0```
  - Finally open a third tab and navigate to the "Demo" directory: ```cd ../Demo```

### Step 3: Capture Data (5-10 minutes)

- **CAN Bus Noise**
  - Run the command ```candump vcan0 -l```
  - Wait a few seconds then use CTRL-C to stop the command
  - This will create a new file that recorded all of the commands sent through the CAN Bus network
  - Run ```wc -l candump-2025-01-10_12345.log``` replacing the candump file with the new file on your system.
  - This should display the number of messages sent through the network during the few seconds that were recorded.

- **Car Controls**
  - Open the controller window while keeping the simulator window visible
  - Test out the following controls to see what they change
    - Arrow keys
    - Right Shift + A/B/X/Y
    - Left Shift + A/B/X/Y
    - Left Shift + Right Shift
    - Right Shift + Left Shift

- **Data Capture**
  - Choose a command that you want to capture, such as unlocking all doors.
  - Run ```candump vcan0 -l``` and capture the command, then use CTRL-C to stop the capture.
  - Check the length of the file using ```wc -l {filename}.log```

### Step 4: Replay Attack (15-20 minutes)

The goal of this lab is to find the one packet that will replay the chosen command. The easiest way to do this is to remove packets from the file until only the correct packet remains. There are a few commands that can help with this:

```wc -l {file}```

This command displays the number of packets in a file.

```canplayer -I {file}```

This command replays a file in the simulator. Use this command to check whether the packet for the chosen command exists in your file.

```head -n {size} {file} > {new file}```
```tail -n {size} {file} > {new file}```

These command creates a new file that contains only a portion of the packets from the old file. {size} determines the number of packets that will be copied over. Use head to copy from the start of the file, and tail to copy from the end. 

```cat {file}```

This command will display the contents of a file. Use this once you have found the final packet. 

```echo '{packet}' > {new file}```

This command will create a new file with the contents described in between the quotation marks. 


## Discussion Points
- Conclude the lab with a discussion on the security of a CAN Bus and how replay attacks can be used maliciously.
- Consider how the security of the CAN Bus can be improved through encryption, authorization, and other methods. 

## Expected Learning Outcomes
- Students will understand the basics of how a CAN Bus works.
- Students will learn how a replay attack can be conducted.
- Students will gain experience using the Linux terminal.
- Students will gain experience working with virtual machines.

## Alternative Versions of the Lab
- [Introduction to Car Hacking: The CAN Bus](https://www.offsec.com/blog/introduction-to-car-hacking-the-can-bus/)
- [Car Hacking: Accessing and Exploiting the CAN Bus Protocol](https://digitalcommons.kennesaw.edu/cgi/viewcontent.cgi?article=1045&context=jcerp/)
- [Vehicle Hacking with ICSim - Part 1](https://medium.com/@naoumine/vehicle-hacking-with-icsim-part-1-f4bd632cac9e)
