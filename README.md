# -Firewall-Configuration-Testing-Windows-Linux
![images window](https://github.com/user-attachments/assets/c2d19adb-0484-493c-a42c-9cf418778ad7)


1. Windows Firewall

1. What is Windows Firewall?
Windows Defender Firewall controls how your computer handles incoming (inbound) and outgoing (outbound) network traffic based on rules you define.

2. Adding an Inbound Rule for Ports 22 and 23
Open Firewall Settings

         Press Windows + R, type wf.msc, and press Enter.
 (Or search for "Windows Defender Firewall with Advanced Security" in the Start menu.)

Select Inbound Rules

In the left panel, click Inbound Rules.

Create a New Rule

In the right panel, click New Rule....

Choose Rule Type

Select Port → Click Next.

Select Protocol and Ports

Choose TCP.

In “Specific local ports” type:

    22, 23
→ Click Next.

Select Action

Choose Allow the connection (or Block the connection if testing) → Click Next.

Choose Profile

Select when the rule applies (Domain, Private, Public) → Click Next.

Name the Rule

Example: Allow SSH & Telnet → Click Finish.

3. Adding an Outbound Rule for Ports 22 and 23
In the left panel, click Outbound Rules.

Repeat steps 3–8 from above.

4. Testing the Rules
Use another device to try connecting:

       Port 22 → via SSH client.

       Port 23 → via Telnet client.

If the rule is set to Allow, the connection should succeed.

If set to Block, the connection should fail.

### **2**  Linux Firewall – Configuring & Testing Ports 22 and 23 (Terminal Method)

![N1-0702-Configuring-Firewalls-for-Linux-blog-image-r6p4rdkq991d5206cfq1hj1poignymzrqdc8nrj0c2](https://github.com/user-attachments/assets/2c58a4cd-ccb8-4f1c-a876-dfbfc85a3c8c)

1. Using UFW (Ubuntu/Debian)
Check if UFW is installed & enabled


       sudo ufw status
If inactive, enable it:

    sudo ufw enable
Allow Ports 22 and 23

    sudo ufw allow 22/tcp
    sudo ufw allow 23/tcp
    Block Ports 22 and 23

    sudo ufw deny 22/tcp
    sudo ufw deny 23/tcp
Delete Rules

    sudo ufw delete allow 22/tcp
    sudo ufw delete allow 23/tcp
View Current Rules

    sudo ufw status verbose


