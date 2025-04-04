# Socials below!

[LinkedIn](https://www.linkedin.com/in/richard-english-iii)

[GitHub](https://github.com/TheCyborgJester)

[Twitter / X](https://x.com/CyborgJesterSEC)

# About me!

I've been diving into the world of cybersecurity since 2019, constantly expanding my knowledge and honing my skills. As a lifelong learner, I enjoy tackling new challenges, whether it's analyzing threats, improving security measures, or exploring the latest developments in the field.

I'm currently seeking a role as a **`SOC Analyst`**, where I can apply my skills in _threat detection_, _incident response_, and _security operations_ to help safeguard organizations. When I’m not hands-on with security tools, I’m staying informed by listening to cybersecurity podcasts like **_`Darknet Diaries`_** and **_`CyberWire Daily`_**, always looking to absorb new insights from industry experts.

Outside of cybersecurity, you'll find me gaming, coding, and always looking for something new to learn. Most importantly, I'm a proud father to a wonderful one-year-old, which keeps me motivated and always striving to be better, both professionally and personally.

## Certifications

**CompTia Security+**

**AZ-900 - Azure Fundamentals**


# Education

**`Western Governors University`** - _Bachelors in Cyber Security and Information Assurance_

_July 2024 - Present_

# Work Experience
**Tek Experts (Now Teknowledge)**

**`Tier 2 Security Compliance and Identity Mangement Engineer`**

_July 2022 - Present_

##### Details
- Collaborate with a team of engineers to troubleshoot and resolve customer issues in Entra ID / Azure
- Specialize in authentication for applications, MFA, Active Directory Federation Services, and device registration issues
- Reviewed logs due to security incidents of customers, recommended Security practices such as Conditional Access Policies
- Used PowerShell to repro issues customers may be experiencing 
- Demonstrated excellent communication skills in dealing with customers and maintaining positive relationships
- Leveraged time management and problem-solving abilities in a fast-paced break-fix environment
- Followed Entra’s Governance, compliance and reporting to identify risks within customer environment 

# Technical Abilities

- Well versed in Windows, Windows Servers and Linux with some Mac Experience
- Strong Reseach and Log Analysis Skills
- Incident Handling
- Microsoft Entra ID / Azure Cloud resources

# Project 1

##### Microsoft Azure SIEM

In my time working for a vendor for Microsoft. It has given me different opportunities to learn all about Microsoft Azure. From the on-premise part of the Sync Engine to everything Device related, how to join to Azure, How to set up Windows Hello for Business (WHFB) etc. I took advantage of the test environment given to me by Microsoft and set up my own Personal SIEM within Azure. 

 [YouTube Project Video](https://www.youtube.com/watch?v=rsWQDXtabsQ)
 


# Project 2

##### National Cyber League Competition

National Cyber League is a National Competition. I am participating with my college, WGU. Its a 4 day long competition with 2 days being individual competition, and 2 days being team competition. We will be competing in a Capture the Flag type of competition. The Competition consists of the following -

* OSINT
* Digital Forensics
* Web Application Exploitation
* Network Traffic Analysis
* Log Analysis
* Scanning & Reconnaissance
* Password Cracking
* Cryptography
* Wireless Access Exploitation
* Enumeration & Exploitation

I am looking forward to taking place in this competiton in April of 2025! 

_This will be updated as I take place with the results I get_


# Python Projects!

## Learning Python for Automated tasks in Cyber Security!

I will continuously add code here as I learn and Make more blocks for automating anything Cyber Security Related! For now, Hello World!


```python

print("Hello World")

```

Code used for Log Analysis in Gym for NCL

```python
# Run pip install pyshark

import pyshark 

# Load the pcap file
pcap_file = "/home/stealthy/Desktop/WireSharks/Candump.pcap" #Change to where you saved it

can = pyshark.FileCapture(pcap_file)

id_list = []

count_id_589 = 0

max_speed = 0.00

# Question 1
for packet in can:
    #print(packet)
    #print("___________________________")
    #print(packet.layers)
    #print("__________________")
    #print(packet.can.field_names)

    #appending ID to empty list

    id_list.append(packet.can.id)

    # Counting IDs for 589
    if packet.can.id == '589':
        count_id_589 += 1
        # Calculating the speed
        packet_speed = 0

        #print(packet.data.field_names)
        # print(packet.data.data_data) # this is the speed value but only interested in first last 2 fields

        # print(packet.data.data_data.split(sep=":"))
        for position, value in enumerate(packet.data.data_data.split(sep=":")):
            #print(f'{position}:{value}')
            if position == 3:
                packet_speed += int(value, 16) << 8 # Converts from hexadecimal to decimal
            if position ==4:
                packet_speed += int(value, 16) # Converts from hexadecimal to decimal
        packet_speed /= 100
        #print(packet_speed)
        if packet_speed > max_speed:
            max_speed = packet_speed


    #break

unique_ids = set(id_list)

# print(id_list)

print(f'Question 1: there are {len(unique_ids)} unique IDs in the pcap file')

print(f'Question 2: ID 589 appears {count_id_589} speed update packets')

print(f'Question 3: The maximum speed is {round(max_speed * 0.6213751, 2)} in mph')

```

