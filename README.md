# SIEM Homelab Project

A hands-on SIEM lab built with Microsoft Sentinel to monitor and detect security threats.

## 🔧 **Tools Used**
- **SIEM:** Microsoft Sentinel
- **Data Sources:** Windows Event Logs
- **Detection Rules:** Custom KQL

## 🚀 **Features**
- Real-time alerting for brute-force attacks, malware C2 traffic, etc.
- Dashboards for threat visualization.
- Automated responses (e.g., block IPs via firewall).

## 📸 **Screenshots**
| Alert Type          | Dashboard View       |
|---------------------|----------------------|
| ![Brute-Force Alert](/brute-force.png) | ![Attacks Dashboard](/dashboard.png) |

## 🛠️ **Setup Guide**
For the purpose of this project, we'll utilised the free USD $200 Microsoft Azure credit provided by Microsoft, as demonstrated below:

**Part 1. Setup Azure Subscription**

Create Free Azure Subscription: https://azure.microsoft.com/en-us/pricing/purchase-options/azure-account

**Part 2. Create a Virual Machine (Honey Pot)**

Go to: https://portal.azure.com and search for virtual machines

Create a new Windows 10 virtual machine (select an appropriate size). Take note of the username and password set during the VM creation process. Remember to shut down the VM once you complete the project to avoid incurring charges after your free credit is exhausted.

Go to the Network Security Group (NSG) for your virtual machine and create a new rule that allows all inbound traffic

Log into your virtual machine and turn off the windows firewall (start -> wf.msc -> properties -> all off)

**Part 3. Logging into the VM and inspecting logs**

Fail 3 logins using “admin” (or some other username different to the one set during the VM creation process)

Login to your virtual machine using the right credential (username and password) set during the VM creation process

Open up Event Viewer (run -> eventvwr) and inspect the security logs

Filter for event ID 4625, you should see the 3 failed logins for "admin” (or the one used during the 3 failed login attempts) 

Next, let's create a central log repository called "LAW" where all logs will be ingested


   
