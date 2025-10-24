# Configuring-Firewall-In-Windows

# Configuring Firewall in Windows

**Objective:**  
To install and configure IIS on Windows Server 2022, create a custom website on a specified port, and implement Windows Firewall rules to control and secure network access.

---

## Step 1: Install IIS (Internet Information Services)
1. Open **Server Manager** → click **Add roles and features**.
2. Choose **Role-based or feature-based installation** → click **Next**.
3. Select **Web Server (IIS)** → **Add Features** → continue through setup → **Install**.
4. When installation completes, click **Close**.

*IIS successfully installed.*

---

## Step 2: Create Website and Change Port
1. Open **IIS Manager** from Tools.
2. Right-click **Sites** → **Add Website...**
3. Site name: `CustomWeb`
4. Physical path: `C:\inetpub\wwwroot`
5. Port: `8080`
6. Click **OK**
7. Remove **Default Web Site**

*Website created on port 8080.*

---

## Step 3: Configure Firewall Rule
1. Open **Windows Defender Firewall with Advanced Security**.
2. Choose **Inbound Rules** → **New Rule**.
3. Select **Port** → **TCP** → Specific local port: `8080`.
4. Choose **Allow the connection** → check all boxes → **Finish**.

*Firewall configured to allow external access to port 8080.*

---

## Verification from Kali Linux

nmap -p 8080 <Windows-VM-IP>



<img width="3716" height="1850" alt="Screenshot 2025-10-23 at 8 31 55 PM" src="https://github.com/user-attachments/assets/68f1ffb1-3d13-46bd-9463-cacb702c1a43" />
<img width="3712" height="1847" alt="Screenshot 2025-10-23 at 8 28 33 PM" src="https://github.com/user-attachments/assets/99e7fea2-3e4c-4098-90e5-f1a9388a176e" />

## What I Learned
- Installed and configured IIS on Windows Server 2022  
- Created and hosted a website on a custom port (8080)  
- Set up Windows Firewall rules to allow specific inbound traffic  
- Verified connectivity using `nmap` from Kali Linux  
- Understood how port management and firewall configurations impact network security
