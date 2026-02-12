# Cybersecurity Learning Notes 🛡️

This repository contains my personal notes, labs, and exercises while learning cybersecurity.

## 🎯 Goals
- Build strong fundamentals in Blue Team & Defensive Security
- Practice labs on TryHackMe & similar platforms
- Learn basic Red Team concepts (recon, scanning, exploitation)
- Prepare for internship and future cybersecurity roles

## 📚 Platforms I Use
- TryHackMe
- YouTube
- Online courses & blogs

## 📂 Folder Structure

blue-team/
red-team/
networking/
linux/
windows/
notes/



# Linux Basics

---

## 📁 Directory Listing

ls                -> Lists files in current directory  
ls -l             -> Detailed list  
ls -r -l          -> Reverse + detailed list  
ls -lt            -> Sort by time  
ls -S             -> Sort by size  
ls -l /var/log    -> Lists logs directory  

---

## 📍 Navigation

pwd               -> Shows current path  
cd                -> Change directory  
cd ..             -> Go up one directory  

---

## 📝 Text & Output

echo              -> Prints text to terminal  
cat               -> Displays file content  

---

## 🔎 Searching

find              -> Search for files  
grep              -> Search inside files  
grep -R           -> Recursive search inside files  

---

## 👤 User & Privileges

whoami            -> Shows current user  
su                -> Switch user  
sudo              -> Run command as administrator  

---

## ⚙️ Command Operators

&                 -> Run command in background  
&&                -> Run second command if first succeeds  
>                 -> Redirect output (overwrite)  
>>                -> Redirect output (append)  

---

## 🔐 File Permissions

Example:

-rw-r--r--

### First Character

-   File  
d   Directory  
l   Link  

### Permission Groups

rw-   -> Owner  
r--   -> Group  
r--   -> Others  

### Permission Letters

r -> Read  
w -> Write  
x -> Execute  
- -> No permission  

---

## 📄 File Information (ls -l)

Hard Link Count  
User Owner  
Group Owner  
File Size  
Timestamp  
File Name  

