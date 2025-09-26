# Task-4---Firewall-Hardening

# 🛡️ Task 4: UFW Firewall Configuration and Hardening

## 🎯 Objective
To configure the Uncomplicated Firewall (UFW) on a Linux system (Linux Mint) to enforce a basic security policy by blocking insecure protocols and documenting the process.

## 🛠️ Tools Used
* **Operating System:** Linux Mint (running on VirtualBox)
* **Firewall Tool:** UFW (Uncomplicated Firewall)

## ⚙️ Commands and Configuration Steps

The following commands were executed in the terminal to set up the firewall:

1.  **Enable the Firewall (Sets Default Policies):**
    ```bash
    sudo ufw enable
    ```
    *Outcome: Firewall activated, setting default policy to DENY incoming and ALLOW outgoing traffic.*

2.  **Add Rule to DENY Inbound Telnet (Insecure Protocol):**
    ```bash
    sudo ufw deny 23/tcp
    ```
    *Requirement met: Blocks inbound traffic on Port 23 (Telnet), which transmits data in plain text.*

3.  **Add Rule to ALLOW Inbound SSH (Management Access):**
    ```bash
    sudo ufw allow 22/tcp
    ```
    *Best Practice: Ensures secure remote management access is possible.*

4.  **Verification (Screenshot Deliverable):**
    ```bash
    sudo ufw status numbered
    ```

## ✅ Deliverable (Firewall Rules Applied)

A screenshot of the verified rules is attached to this repository:
* (`[Name of your screenshot file here, e.g., Screenshot 2025-09-26 120916.png]`)

## 💡 Summary: How a Firewall Filters Traffic

A firewall acts as a digital gatekeeper, controlling the flow of network traffic based on a predefined set of **rules** (an Access Control List).

1.  **Rule Matching:** When a data packet arrives, the firewall inspects its characteristics (Source/Destination IP, Port, and Protocol).
2.  **Order of Precedence:** Rules are read in order. If a packet matches a rule, the firewall takes the specified action (`ALLOW` or `DENY`).
3.  **Default Policy:** If a packet does not match any explicit rule, the firewall applies the **default policy** (which, in UFW's secure configuration, is to **DENY** the traffic).
4.  **Security Impact:** By explicitly DENYING insecure protocols like Telnet (Port 23), the firewall protects the machine from network-based attacks that rely on open, vulnerable ports.
