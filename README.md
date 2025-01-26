Elastic SIEM Home Lab Setup
This guide walks you through setting up an Elastic Stack Security Information and Event Management (SIEM) home lab using the Elastic Cloud portal and a Kali Linux VM. I’m doing this project to support my growth in the cybersecurity space, as I don't yet have hands-on experience in the field but I practice with various home labs to build my skills.

In this lab, you’ll learn how to forward logs from Kali Linux to Elastic SIEM, generate security events, query and analyze logs, create dashboards, and set up alerts. It’s a great way to gain practical experience with security monitoring and incident response.

Prerequisites
Virtualization software (VirtualBox or VMware)
Basic knowledge of Linux and virtualization
Kali Linux VM
Steps
1. Set Up an Elastic Account
Sign up for a free trial at Elastic Cloud
Log in to the Elastic Cloud console and create a deployment with Elasticsearch.
Choose a region and deployment size, and wait for the setup to complete.

2. Set Up the Kali Linux VM
Download Kali Linux from official website.
Install Kali Linux in VirtualBox/VMware.
Log in with the default credentials: username: kali, password: kali.

3. Install the Elastic Agent on Kali
Log in to the Elastic SIEM instance, go to Integrations → Elastic Defend, and install the agent.
Copy the command for Linux and run it in the Kali terminal.
Verify installation with sudo systemctl status elastic-agent.service.

4. Generate Security Events on Kali
Install Nmap (if not pre-installed in Kali):
sudo apt-get install nmap
Run Nmap scans to generate security events:
sudo nmap <vm-ip>
Example scans: nmap -sS <ip address>, nmap -sT <ip address>, nmap -p- <ip address>.

5. Query Security Events in Elastic SIEM
In the Elastic Cloud portal, go to Logs under Observability.
Use search queries to filter logs (e.g., event.action: "nmap_scan" or process.args: "sudo").
View the logs and events from your Kali VM.

6. Create a Dashboard to Visualize Events
Go to Analytics → Dashboards, and create a new dashboard.
Add a new visualization (e.g., Area or Line chart).
Set the Metrics to "Count" and the X-Axis to "Timestamp".

7. Create an Alert for Security Events
Go to Security → Alerts and click Manage rules.
Create a custom rule using a query (e.g., event.action: "nmap_scan").
Set severity, notification options (email, Slack, webhook), and enable the rule.
Conclusion
By following these steps, you will have a home lab where you can generate and analyze security events using Elastic SIEM. This hands-on setup helps you improve your skills in security monitoring and incident response as I continue to build my expertise in the cybersecurity field.

Next Steps
Generate more security events and analyze them in Elastic SIEM.
Explore Elastic SIEM’s additional features such as integrations with cloud providers or syslog.
Experiment with creating more complex queries and visualizations.

Hope you enjoyed this home lab as much as I did :) take advantage of the free trial (15 days) and get as much hands on experiance as you can - happy learning ! 
