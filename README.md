## //------------- Top 5 Group Policy (GPO) – AD DS Server ----------------//

1. Map Network Drive to Domain PC using GPO

Step 1: Folder Sharing on Server
go file explorer  
go your drive like:- D drive  # 🔐 Top 5 Group Policy Objects (GPO) – Active Directory Domain Services (AD DS)

This repository demonstrates the **Top 5 commonly used Group Policy Objects (GPOs)** in a real-world **Active Directory Domain Services (AD DS)** environment.  
These policies are widely used by **IT Support Engineers, System Administrators, and Network Engineers**.

---

## 📌 Project Overview

The project covers practical GPO implementations such as:
- Network drive mapping
- User restriction policies
- Desktop management
- Security hardening using Group Policy

---

## 1️⃣ Map Network Drive to Domain PC Using GPO

### Step 1: Share Folder on Server
- Open **File Explorer** on the server
- Go to the required drive (e.g. `D:`)
- Right-click → **Properties**
- Go to **Sharing → Advanced Sharing**
- Enable **Share this folder**
- Click **Permissions**
- Allow **Full Control**
- Click **Apply → OK**



## Copy network sharing path  
win-62QTLAIRTKE\kurre  

## 🧩 Step 2: Create a New Group Policy Object (GPO)

- Open **Server Manager**
- Go to **Tools → Group Policy Management**
- Navigate to:
  Domains → kurrecomputers.local

- Right-click the required **Organizational Unit (OU)** (e.g. `Raipur`)
- Click **Create a GPO in this domain**
- Name the GPO (e.g. `Policy`)

---

## 🧩 Step 3: Configure Drive Mapping Using GPO

- Right-click the created GPO → **Edit**
- Navigate to:
User Configuration
→ Preferences
→ Windows Settings
→ Drive Maps 
- Right-click → **New → Mapped Drive**

### Drive Mapping Configuration

Action : Create
Location : \10.0.0.1\kurre
Drive Letter : D

- Enable **Show this drive**
- Enable **Show all drives**
- Click **Apply → OK**

✅ The network drive will be mapped automatically on Domain systems.

---

## 2️⃣ Block Control Panel Using GPO

- Right-click the required **GPO** (e.g. `Policy`)  
- Navigate to:
User Configuration
→ Policies
→ Administrative Templates
→ Control Panel
- Open **Prohibit access to Control Panel and PC settings**
- Set to **Enabled**
- Click **Apply → OK**

---

## 3️⃣ Set Fixed Desktop Wallpaper Using GPO

### Step 1: Prepare Wallpaper
- Copy the wallpaper image to a shared folder on the server
- Provide **Read permission** to domain users

### Step 2: Configure GPO
- Right-click the required **GPO** (e.g. `Policy`)  
- Navigate to:

User Configuration
→ Policies
→ Administrative Templates
→ Desktop
→ Desktop
- Open **Desktop Wallpaper**
- Set to **Enabled**

Wallpaper path example:

paste wallpaper path like:-  
\\10.0.0.1\kurre\wallpaper.jpg  

- Click **Apply → OK** 

## 4️⃣ Hide / Remove Recycle Bin Icon from Desktop

This Group Policy setting is used to **hide or remove the Recycle Bin icon** from user desktops in an Active Directory environment.

### Steps to Configure

- Right-click the required **GPO** (e.g. `Policy`)  
- Click **Edit**
- Navigate to:
User Configuration
→ Policies
→ Administrative Templates
→ Desktop

- Double-click **Remove Recycle Bin icon from desktop**
- Set the policy to **Enabled**
- Click **Apply → OK**

✅ The Recycle Bin icon will be removed from the desktop for all users to whom this GPO is applied.

## 5️⃣ Block USB / Removable Storage Access

This policy is used to **block all USB and removable storage devices** on Domain computers for security purposes.

### Steps to Configure

- Right-click the required **GPO** (e.g. `Policy`) → **Edit**
- Navigate to:
Computer Configuration
→ Policies
→ Administrative Templates
→ System
→ Removable Storage Access
- Open **All Removable Storage Classes: Deny all access**
- Set the policy to **Enabled**
- Click **Apply → OK**

---

## 🔄 Apply Group Policy on Domain System

After completing all configurations:

- Go to the client PC
- Press **Windows + R**
- Type: gpupdate
- Press **Enter**

✅ USB / removable storage access will be blocked on the Domain system.

