
# Nova-Tech-Day-3
Built a highly available and scalable web application architecture for NovaTech using EC2, Application Load Balancer (ALB), Auto Scaling Groups (ASG), IAM, AMI, Launch Templates, and CloudWatch monitoring.

This project simulates a real-world SaaS company infrastructure capable of handling traffic spikes, distributing traffic efficiently, and improving fault tolerance using AWS high availability services.
# Problem Statement

NovaTech’s SaaS application started receiving increased traffic after launching new dashboards and analytics services.

The existing single EC2 server architecture caused:

single point of failure
downtime risks
no automatic scaling
uneven traffic handling
limited operational visibility
inability to handle traffic spikes efficiently

# Architecture

Users → Application Load Balancer → Auto Scaling Group → EC2 Web Servers

<img width="1091" height="531" alt="day 3" src="https://github.com/user-attachments/assets/a58f3a60-2c2b-435b-b343-3638954a446b" />



# Aws Services Used
IAM
EC2
Application Load Balancer (ALB)
Auto Scaling Groups (ASG)
Launch Templates
AMI
CloudWatch
Security Groups

# Solution

Implemented a highly available AWS infrastructure using:

EC2 web servers
Application Load Balancer
Auto Scaling Groups
Multi-AZ deployment
CloudWatch monitoring

This architecture automatically distributes traffic and scales infrastructure dynamically during high load conditions.

# Step 1:

Launched an EC2 instance using Amazon Linux 2023 and configured inbound rules for SSH, HTTP, and HTTPS traffic.

<img width="1527" height="708" alt="Screenshot 2026-05-23 134752" src="https://github.com/user-attachments/assets/1d68a941-a478-42c7-b5b3-8e183b935019" />

<img width="1893" height="750" alt="Screenshot 2026-05-23 134931" src="https://github.com/user-attachments/assets/218d3f6e-bf10-4485-b87e-ad2953e6443f" />

# Step 2:

Connected to the EC2 instance using SSH and installed Nginx web server.

<img width="1912" height="971" alt="Screenshot 2026-05-23 124918" src="https://github.com/user-attachments/assets/be7e6d69-3816-4250-a5a0-41bfe3b2c8e1" />

<img width="1919" height="328" alt="Screenshot 2026-05-23 124946" src="https://github.com/user-attachments/assets/40221948-eca3-49e1-b648-8fffd185864b" />

<img width="1915" height="583" alt="Screenshot 2026-05-23 125131" src="https://github.com/user-attachments/assets/5bd4157f-5e16-4104-9909-07e4c4b96247" />

# Step 3:

Deployed the NovaTech SaaS website files into the EC2 web server
<img width="1481" height="460" alt="Screenshot 2026-05-23 130145" src="https://github.com/user-attachments/assets/9e04a129-fa49-48e9-bcf8-954ed2d237c9" />

<img width="1264" height="162" alt="Screenshot 2026-05-23 130136" src="https://github.com/user-attachments/assets/4e1c72a8-3537-44f0-ab11-98683c710a97" />

<img width="1916" height="957" alt="Screenshot 2026-05-23 130120" src="https://github.com/user-attachments/assets/d202340d-b007-4ce7-9dd7-aa81b10b0449" />

# Step 4:
Created an AMI from the configured EC2 instance to use as a reusable machine image for Auto Scaling.

<img width="1910" height="906" alt="Screenshot 2026-05-23 130611" src="https://github.com/user-attachments/assets/b012a28d-3e34-41de-800c-472c96bab199" />

# Step 5:
Created a Launch Template using the NovaTech AMI, instance type, security groups, and key pair configuration.
<img width="1919" height="904" alt="Screenshot 2026-05-23 130630" src="https://github.com/user-attachments/assets/72814c2e-d5e8-405c-9a4c-24f7c87ce6b8" />

<img width="1897" height="762" alt="Screenshot 2026-05-23 131130" src="https://github.com/user-attachments/assets/ce9f122b-d10d-4d1d-9e1c-e40f6f801382" />

<img width="1916" height="898" alt="Screenshot 2026-05-23 131254" src="https://github.com/user-attachments/assets/18e103cb-0e9e-40c5-af96-61b383cdf69b" />

# Step 6:
Created a Target Group and registered the EC2 instance for load balancing.
<img width="1911" height="904" alt="Screenshot 2026-05-23 135942" src="https://github.com/user-attachments/assets/f9aacf47-b02e-4547-96cf-db729ef1c8cd" />

<img width="1613" height="540" alt="Screenshot 2026-05-23 140051" src="https://github.com/user-attachments/assets/f2c1d960-c8c0-432f-b110-c5a382345399" />

# Step 7:
Created an internet-facing Application Load Balancer and attached it to the Target Group.
<img width="1914" height="630" alt="Screenshot 2026-05-23 140258" src="https://github.com/user-attachments/assets/cc293816-683b-40c1-99e5-b1f194183a02" />

# Step 8:
Verified the NovaTech application was successfully accessible through the ALB DNS endpoint.
<img width="1910" height="956" alt="Screenshot 2026-05-23 141119" src="https://github.com/user-attachments/assets/264acca3-bd81-4c9a-a47a-48c8d21afc68" />

# Step 9:
Created an Auto Scaling Group using the Launch Template and attached it to the Load Balancer Target Group.
<img width="1919" height="913" alt="Screenshot 2026-05-23 141415" src="https://github.com/user-attachments/assets/82eb099d-c72a-46a6-829b-4a4f03312278" />

# Outcome

Successfully deployed a production-style highly available web application architecture using AWS EC2, ALB, and Auto Scaling Groups.

The infrastructure can now:

distribute traffic
recover from instance failures
scale automatically during traffic spikes
improve application availability

