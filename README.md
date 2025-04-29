<p align="center">
<img src="https://i.imgur.com/r8S0B8F.png" alt="vpn diagram"/>
</p>

# Azure Virtual Machine and VPN Lab

This tutorial walks you through setting up a virtual machine in Microsoft Azure, testing VPN connections, and observing the changes in IP addresses.

---

## Part 1: Create a Virtual Machine in Azure

1. **Access Your Public IP Address**
   - On your own machine, browse to [WhatIsMyIPAddress](https://whatismyipaddress.com/).
   - Take note of your public IP address and save it in a text file for reference.

2. **Create a Resource Group**
   - Log into your Azure Portal: [Azure Portal](https://portal.azure.com/).
   - Navigate to **Resource Groups** and click **Create**.
   - Provide the following:
     - **Resource Group Name**: `MyAzureVPNLab`
     - **Region**: Select a region near you.
   - Click **Review + Create**, then **Create**.

3. **Create a Virtual Machine**
   - Navigate to **Virtual Machines** in the Azure Portal and click **Create**.
   - Select **Azure Virtual Machine**.
   - Fill out the following:
     - **Name**: `MyWindowsVM`
     - **Region**: Choose a region close to your geographic location or country from your current location.
     - **Image**: Windows 10 22H2.
     - **Size**: Select a size that has at least 2vcpus, and 8GiB memory.
     - **Administrator Username and Password**: Set your credentials.
   - Acknowledge licensing agreement & ensure **Inbound Port Rules** to allow RDP (Remote Desktop Protocol).
   - Click **Review + Create**, then **Create**.

![image](https://github.com/user-attachments/assets/2dc277e6-909b-4d17-ae3b-fee309647c98)

![image](https://github.com/user-attachments/assets/2379a5c4-48ff-4285-a7f6-97522cf6532b)

4. **Log into the Virtual Machine**
   - After the VM is created, navigate to it in the Azure Portal.
   - Copy the **Public IP Address** of your VM.
   - Use Remote Desktop to connect to the VM:
     - **Remote Desktop Address**: Enter the Public IP Address of the VM.
     - **Username and Password**: Use the credentials you created earlier.
   - Once connected, open a web browser on the VM.

![image](https://github.com/user-attachments/assets/424f1f43-73cb-410a-9d58-c19880a82b44)

5. **Check the VM's Public IP Address**
   - In the VM, browse to [WhatIsMyIPAddress](https://whatismyipaddress.com/).
   - Take note of the VM's public IP address and save it in a text file.

---

## Part 2: Sign Up for ProtonVPN and Test the VPN Connection

1. **Sign Up for ProtonVPN**
   - On your actual computer, go to [ProtonVPN Sign-Up](https://account.protonvpn.com/signup?plan=free&language=en).
   - Create a free account.

2. **Download ProtonVPN Client**
   - In your VM, go to [ProtonVPN Download](https://protonvpn.com/download/).
   - Download and install the ProtonVPN client.

3. **Log Into ProtonVPN**
   - Open the ProtonVPN client in the VM.
   - Log in using your ProtonVPN account credentials: [ProtonVPN Login](https://account.protonvpn.com/login).

4. **Connect to a VPN Server**
   - In the ProtonVPN client, choose a VPN server in a area different from your actual computer's location (Proton VPN requires payment to change countries).
   - Connect to the VPN server.

![image](https://github.com/user-attachments/assets/8e65d4af-33c7-499c-a5ec-8b6712993e94)

5. **Check the VPN's Public IP Address**
   - In the VM, browse to [WhatIsMyIPAddress](https://whatismyipaddress.com/).
   - Take note of the new IP address and save it in a text file.

---

## Notes and Observations

- Save all IP addresses and observations in a text file for documentation purposes.
- Compare the behavior of websites and the changes in IP addresses to understand the effects of geographic location and VPN usage.
- From this lab, here are my documented IP addresses & their changes:

Personal Computer

![image](https://github.com/user-attachments/assets/8d0762e5-7338-4e66-a909-3b5f439a4d41)

VM - **Non-VPN**

![image](https://github.com/user-attachments/assets/611b3452-c59e-4d97-94e8-6ef5a2b562c4)

VM - **VPN** 

![image](https://github.com/user-attachments/assets/3ffb46ca-c96a-4e75-9bb1-90e98fa5d476)

---
