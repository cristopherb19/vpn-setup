<p align="center">
<img src="https://i.imgur.com/r8S0B8F.png" alt="vpn diagram"/>
</p>

# Azure Virtual Machine and VPN Lab

This tutorial walks you through setting up a virtual machine in Microsoft Azure, testing VPN connections, and observing the changes in IP addresses.

---

## Part 1: Create a Virtual Machine in Azure

1. **Access Your Public IP Address**
   - On your own machine, browse to [WhatIsMyIPAddress](https://whatismyipaddress.com/).
   - Take note of your public IP address and save it for reference.
<img src="https://imgur.com/Hkv4zDC.png" alt="vpn diagram"/>

2. **Create a Resource Group**
   - Log into your Azure Portal: [Azure Portal](https://portal.azure.com/).
   - Navigate to **Resource Groups** and click **Create**.
   - Provide the following:
     - **Resource Group Name**: `vpn-test`
     - **Region**: Select your region of choice.
   - Click **Review + Create**, then **Create**.

3. **Create a Virtual Machine**
   - Navigate to **Virtual Machines** in the Azure Portal and click **Create**.
   - Select **Azure Virtual Machine**.
   - Fill out the following:
     - **Name**: `vpn-test-win-10`
     - **Region**: Choose previously selected region from step 2.
     - **Image**: Windows 10 22H2.
     - **Size**: Select a size that has at least 2vcpus, and 8GiB memory.
     - **Administrator Username and Password**: Set your credentials.
   - Acknowledge licensing agreement & ensure **Inbound Port Rules** to allow RDP (Remote Desktop Protocol).
   - Click **Review + Create**, then **Create**.

<img src="https://imgur.com/Rdml4vh.png" alt="vpn diagram"/>

4. **Log into the Virtual Machine**
   - After the VM is created, navigate to it in the Azure Portal.
   - Copy the **Public IP Address** of your VM.
   - Use Remote Desktop to connect to the VM:
     - **Remote Desktop Address**: Enter the Public IP Address of the VM.
     - **Username and Password**: Use the credentials you created earlier.
   - Once connected, open a web browser on the VM.

<img src="https://imgur.com/J41tyz0.png" alt="vpn diagram"/>
<img src="https://imgur.com/KRfxLKo.png" alt="vpn diagram"/>
<img src="https://imgur.com/PvguEHI.png" alt="vpn diagram"/>

5. **Check the VM's Public IP Address**
   - In the VM, browse to [WhatIsMyIPAddress](https://whatismyipaddress.com/).
   - Take note of the VM's public IP address and save it for reference.
<img src="https://imgur.com/75wY3dn.png" alt="vpn diagram"/>
---

## Part 2: Sign Up for ProtonVPN and Test the VPN Connection

1. **Sign Up for ProtonVPN**
   - On your actual computer, go to [ProtonVPN Sign-Up](https://account.protonvpn.com/signup?plan=free&language=en).
   - Create a free account.

2. **Download ProtonVPN Client**
   - In your VM, go to [ProtonVPN Download](https://protonvpn.com/download/).
   - Download and install the ProtonVPN client.
<img src="https://imgur.com/r5XVjrL.png" alt="vpn diagram"/>
<img src="https://imgur.com/9K5Rjho.png" alt="vpn diagram"/>

3. **Log Into ProtonVPN**
   - Open the ProtonVPN client in the VM.
   - Log in using your ProtonVPN account credentials: [ProtonVPN Login](https://account.protonvpn.com/login)
<img src="https://imgur.com/YKwzp9Z.png" alt="vpn diagram"/>

4. **Connect to a VPN Server**
   - In the ProtonVPN client, choose a VPN server in a area different from your actual computer's location (Proton VPN requires payment to change countries).
   - Connect to the VPN server.

<img src="https://imgur.com/SPROTJt.png" alt="vpn diagram"/>

5. **Check the VPN's Public IP Address**
   - In the VM, browse to [WhatIsMyIPAddress](https://whatismyipaddress.com/).
   - Take note of the new IP address and save it for reference.
<img src="https://imgur.com/BuDgmQh.png" alt="vpn diagram"/>
   

---

## Notes and Observations

- Compare the behavior of websites and the changes in IP addresses to understand the effects of geographic location and VPN usage.
- From this lab, here are my documented IP addresses & their changes:

Personal Computer

<img src="https://imgur.com/Hkv4zDC.png" alt="vpn diagram"/>

VM - **Non-VPN**

<img src="https://imgur.com/75wY3dn.png" alt="vpn diagram"/>

VM - **VPN** 

<img src="https://imgur.com/BuDgmQh.png" alt="vpn diagram"/>

---

## Conclusion
Congragulations on successfully completing the vpn-setup lab!

- VPNs can securely link two computers or networks across the internet.
- This allows the two networks to send encapsulated and encrypted data to eachother.
- You will likely use a VPN to connect to resources at work from your home.
