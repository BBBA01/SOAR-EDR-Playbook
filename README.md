# SOAR + EDR Project using Lima Charlie / Tines

# Objective

Utilizing SOAR automation for Endpoint Detection & Response (EDR) to enhance workflow efficiency and automate the isolation of a device across multiple communication channels.

# Tools Used

In this project, I employed a range of sophisticated tools. These included Lima Charlie, a cloud-based EDR solution for creating custom detection and response rules; Tines for SOAR automation playbooks, which I integrated with Slack and Email for automated response capabilities. Additionally, I utilized Microsoft Azure to deploy my Virtual Machine, ensuring a secure environment for testing detections.

# Step 1: Create playbook workflow to brainstorm actions:

In this phase, I used Draw.IO to conceptualize the project’s workflow. It is always advisable to begin with a logical design and clear objectives before starting any project, so you can refer to it as needed to confirm everything is functioning as planned.

![Screenshot 2025-03-06 173757](https://github.com/user-attachments/assets/bfec9490-fc29-4342-8ff2-9076c4d7111f)

# Step 2: Configure and Install Lima Charlie (EDR), create the virtual machine in the cloud resource (Azure), and connect the endpoint to generate events.

In this phase, I set up the Lima Charlie Organization for my project and generated sensors and keys to link my solution to the endpoint. I created the endpoint using Microsoft Azure by initiating a VM that suited my testing requirements for alerts. Subsequently, I connected the endpoint with the Lima Charlie sensor I had crafted and tested the connection by triggering alerts. For this purpose, I employed Lazagne, an open-source password recovery tool, to produce the alerts.



Step 3: Install the LaZagne tool to generate telemetry and establish the detection and response rule.

In this step, I installed LaZagne on the host device in Azure and began generating telemetry using PowerShell to determine the necessary items for event detection and response. I was specifically searching for process IDs created by these tools, so I could use that along with the hash for my detection rule. With these elements, I proceeded to create my custom detection rule as follows:


Step 4: Setup and configure Slack, Tines and test the connections via Lima Charlie and Tines.

In this step, I created my accounts for Slack, Tines and connected them so that we can use the automation workflow for the SOAR component of this project. After connecting them, Tines needed to be connected to Lima Charlie via the API.


Step 5: Utilize SOAR automation through Tines to dispatch a Slack message, transmit an email, and automatically generate a user prompt to decide whether to isolate the machine.

This final step was the final piece to connect everything to allow for fast isolation of a device via many different channels. In this step, I created a workflow as seen above for the SOAR automation of the tasks/steps that take place for an alert. A lot of useful information is fed into the Slack notification, with a direct link to the incident, and the same information is sent via email. In configuring this way, analysts can respond quickly to any threats, and get right to where they need to go to start fighting evil!


After connecting the slack, I generated a bunch of alerts to get this going and start seeing a lot of action:


Each of these alerts would be generated and sent via Slack and via email, providing a fast response and detection time in order to respond to the incident.

Conclusion:

Working on this project was incredibly enjoyable, and it was a fantastic learning experience about SOAR and the use of automation to boost work productivity. SOAR is often hyped as the next big innovation alongside SIEM, and I’ve come to understand that it indeed requires some time to integrate effectively into the system. The initial hours dedicated to setup are a solid investment, as they pay off in the long run by streamlining processes.

Lima Charlie stands out as an excellent EDR solution, boasting sophisticated automation capabilities, customizable detection rules, ultra-light sensors, a comprehensive timeline for pinpointing critical events, a process ID checker, malware analysis tools, and much more. It’s an outstanding choice to kickstart your EDR journey.

Thank you MyDFIR for this project! Loved working on it!
