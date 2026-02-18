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

chown -> Change file owner

chown user file.txt
chown user:group file.txt
chown :group file.txt
chown -R user:group folder/

Used to change ownership of files and directories.
Usually requires sudo.

cat -> Display file content

cat file.txt
cat file1.txt file2.txt
cat > newfile.txt
cat >> file.txt
cat a.txt b.txt > all.txt
cat -n file.txt

Used to view, create, and combine files.

cp -> Copy files and directories

cp source.txt dest.txt
cp file.txt /home/user/Desktop/
cp -r folder /home/user/Desktop/
cp -i file.txt dest.txt
cp -v file.txt dest.txt

Used to copy files and folders.

dd -> Low level disk copy tool

dd if=input of=output
sudo dd if=ubuntu.iso of=/dev/sdb bs=4M status=progress
sudo dd if=/dev/sda of=backup.img
dd if=/dev/zero of=test.img bs=1M count=100

Used for disk imaging and ISO writing.

chmod -> Change file permissions

chmod 755 file.sh
chmod u+x script.sh
chmod g+w file.txt
chmod o-r file.txt
chmod -R 755 folder/

755 = rwx r-x r-x
644 = rw- r-- r--
777 = rwx rwx rwx

Used to modify file and directory permissions.

mv -> Move or rename files and directories

mv file.txt /home/user/Desktop/
mv oldname.txt newname.txt
mv folder /home/user/Documents/
mv -i file.txt destination/
mv -v file.txt destination/

Used to move or rename files and folders.

rm -> Remove files and directories

rm file.txt
rm -r foldername
rm -f file.txt
rm -rf foldername
rm -i file.txt

Used to delete files and folders.

grep -> Search text inside files

grep "word" file.txt
grep -R "word" /path/
grep -i "word" file.txt
grep -n "word" file.txt
grep -v "word" file.txt

Used to find specific text inside files.

## Regex (Regular Expressions)

.    -> Any single character
[]   -> Any one specified character
[^ ] -> Not specified character
*    -> Zero or more of previous character
^    -> Start of line
$    -> End of line

## Extended Regex (use grep -E)

+    -> One or more of previous
?    -> Optional (0 or 1)
{}   -> Exact or range repetition
|    -> OR operator
()   -> Grouping

## Examples

grep "h.t" file.txt
grep "^root" file.txt
grep "bash$" file.txt
grep -E "cat|dog" file.txt
grep -E "o{2,4}" file.txt

## shutdown

shutdown now        -> Shutdown immediately
shutdown +10        -> Shutdown after 10 minutes
shutdown 23:30      -> Shutdown at specific time
shutdown -r now     -> Reboot system
shutdown -c         -> Cancel shutdown

## date

date                -> Show current date and time
date "+%d-%m-%Y"    -> Show date format
date "+%H:%M:%S"    -> Show time format
sudo date -s "YYYY-MM-DD HH:MM:SS" -> Set date and time

## iwconfig

iwconfig              -> List wireless interfaces
iwconfig wlan0        -> Show wlan0 interface info

## ifconfig

ifconfig              -> List network interfaces
ifconfig eth0         -> Show eth0 interface
sudo ifconfig eth0 up -> Enable interface
sudo ifconfig eth0 down -> Disable interface
sudo ifconfig eth0 192.168.1.10 -> Assign IP

## ping

ping google.com       -> Ping domain
ping 8.8.8.8          -> Ping IP address
ping -c 4 google.com  -> Send 4 packets

## ps -> Process Status

ps              -> Show current shell processes
ps aux          -> Show all running processes
ps -ef          -> Full format process list
ps -p 1234      -> Show specific PID
ps aux | grep ssh -> Search process

Important fields:
USER -> Process owner
PID  -> Process ID
%CPU -> CPU usage
%MEM -> Memory usage
COMMAND -> Executed command

TTY  -> Terminal associated with the process
?    -> No terminal (background/system process)

TIME -> Total CPU time used by the process

CMD  -> Command that started the process

## dpkg

sudo dpkg -i package.deb   -> Install .deb package
dpkg -l                    -> List installed packages

## apt-cache

apt-cache search package   -> Search for package

## apt-get

sudo apt-get update        -> Update package list
sudo apt-get install pkg   -> Install package
sudo apt-get upgrade       -> Upgrade installed packages

Used for package management in Debian/Ubuntu systems.

## dpkg

sudo dpkg -i package.deb      -> Install .deb package
dpkg -l                       -> List installed packages

## apt-cache

apt-cache search package      -> Search for package

## apt-get

sudo apt-get update           -> Update package list
sudo apt-get install pkg      -> Install package
sudo apt-get upgrade          -> Upgrade installed packages
sudo apt-get remove pkg       -> Remove package (keep config files)
sudo apt-get purge pkg        -> Remove package completely (including config)
sudo apt-get autoremove       -> Remove unused dependencies

Used for package management in Debian/Ubuntu systems.

## passwd -> Change user password

passwd                     -> Change your own password
sudo passwd username       -> Change another user's password
sudo passwd -l username    -> Lock user account
sudo passwd -u username    -> Unlock user account
chage -l username          -> Show password aging info

## vi / vim

vi file.txt -> Opens file in vi editor

MODES

ESC -> Switch to Command Mode (control mode)

Insert Mode Commands:
i   -> Insert before cursor
a   -> Insert after cursor
I   -> Insert at beginning of line
A   -> Insert at end of line
o   -> Open new line below
O   -> Open new line above

:   -> Enter Ex Mode (used for save/quit commands)

MOVEMENT

h -> Move left
j -> Move down
k -> Move up
l -> Move right

w -> Move to next word
b -> Move to previous word

^ -> Move to beginning of line
$ -> Move to end of line

gg -> Go to top of file
G  -> Go to end of file
5G -> Go to line 5

DELETE

dd   -> Delete current line
3dd  -> Delete 3 lines
dw   -> Delete one word
d3w  -> Delete 3 words

CHANGE (Delete + Insert)

cc   -> Change entire line
cw   -> Change one word
c3w  -> Change 3 words

YANK (COPY)

yy   -> Copy current line
3yy  -> Copy 3 lines
yw   -> Copy one word

PUT (PASTE)

p -> Paste after cursor
P -> Paste before cursor

SEARCH

/word -> Search forward
n     -> Next match
N     -> Previous match
?word -> Search backward

SAVE & QUIT

:w   -> Save file
:q   -> Quit (if no changes)
:wq  -> Save and quit
:q!  -> Quit without saving
ZZ   -> Save and quit (command mode)

VI COMMAND STRUCTURE (VERY IMPORTANT)

[action][count][motion]

This is the core logic of vi.

Examples:

d3w  -> Delete 3 words
3dd  -> Delete 3 lines
5h   -> Move 5 characters left
3yy  -> Copy 3 lines
c2w  -> Change 2 words

Explanation:

action  -> What to do (d=delete, c=change, y=copy)
count   -> How many times
motion  -> Where / how far (w=word, h=left, etc.)

Formula:
action + number + movement
