# A-Simple-Elastic-SIEM-Lab-PROJECT
# A Simple Elastic SIEM Lab

In this project, I set up a home lab for Elastic Stack Security Information and Event Management (SIEM) using the Elastic Web portal and a Kali Linux VM. The lab involves generating security events, configuring an agent to forward logs to the SIEM, analyzing the logs, and creating visualizations and alerts. Below are the steps I followed:

## Prerequisites
- VirtualBox or VMware
- Basic knowledge of Linux and virtualization software

## Steps

### 1. Set Up an Elastic Account
1. Sign up for a free Elastic Cloud trial at [Elastic Cloud Registration](https://cloud.elastic.co/registration).
2. Log in to the Elastic Cloud console and start your free trial.
3. Create a deployment with Elasticsearch, choose your region and size, and wait for the deployment to complete.

### 2. Install Kali Linux VM
1. Download the Kali Linux VM from [Kali's official website](https://www.kali.org/get-kali/#kali-virtual-machines).
2. Import the VM into VirtualBox or VMware and complete the installation.
3. Log in with default credentials (username: `kali`, password: `kali`).

### 3. Configure Elastic Agent
1. In the Elastic SIEM interface, navigate to Integrations > Elastic Defend.
2. Install the Elastic Defend integration and copy the command to install the agent on the Kali VM.
3. Run the command in the Kali terminal and verify the agent installation with:
   ```bash
   sudo systemctl status elastic-agent.service
   ```

### 4. Generate Security Events
1. Use Nmap to generate security events:
   ```bash
   sudo nmap <vm-ip>
   sudo nmap -sS <ip-address>
   sudo nmap -p- <ip-address>
   ```
2. These scans simulate security events, like open port detection.

### 5. Query Security Events
1. In Elastic SIEM, go to Observability > Logs.
2. Search for events using queries like:
   ```text
   event.action: "nmap_scan" OR process.args: "sudo"
   ```

### 6. Create a Dashboard
1. Navigate to Analytics > Dashboards and click “Create dashboard.”
2. Add visualizations such as line or area charts to analyze event counts over time.

### 7. Set Up Alerts
1. In Security > Alerts, click “Manage rules” and create a new custom query rule for Nmap scans.
2. Configure the rule to trigger alerts and specify notification actions (e.g., email or Slack).

## Results
I successfully:
- Monitored and analyzed logs from the Kali VM.
- Created dashboards to visualize event patterns.
- Configured alerts to detect and respond to security incidents.

This lab enhanced my skills in security monitoring and incident response, showcasing practical experience with Elastic SIEM that I can discuss in interviews.

