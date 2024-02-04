# Linux Assignment 4

**Q1. Create a directory named "MyFiles" in your home directory. Navigate into this directory and list its contents.**

![Screenshot from 2024-02-02 15-33-14](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/1a964d38-a48b-49f2-870b-34cf50e4b7a5)

**Q2. Copy a file named "document.txt" from your home directory to the "MyFiles" directory. Move the file to a subdirectory named "Documents" within "MyFiles.**

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/949e0e9d-238b-41a9-b5cb-1844e7819b6f)

root@nitesh:/home/MyFiles# mkdir Documents

root@nitesh:/home/MyFiles# ls

Documents  document.txt  hello

root@nitesh:/home/MyFiles# cd Documents/

root@nitesh:/home/MyFiles/Documents# cd ..

root@nitesh:/home/MyFiles# mv document.txt /home/MyFiles/Documents/

root@nitesh:/home/MyFiles# cd MyFiles/

bash: cd: MyFiles/: No such file or directory

root@nitesh:/home/MyFiles# cd Documents/

root@nitesh:/home/MyFiles/Documents# ls

document.txt

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/87049d23-d556-43fc-aeec-3ac40612da64)

**Q3. Create an empty file named "notes.txt" in the "MyFiles" directory. Afterward, delete the file.**

root@nitesh:/home/MyFiles# touch notes.txt

root@nitesh:/home/MyFiles# ls

Documents  hello  notes.txt

root@nitesh:/home/MyFiles# rm notes.txt

root@nitesh:/home/MyFiles# ls

Documents  hello

root@nitesh:/home/MyFiles# 

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/ec68e50d-75eb-4e32-bbf1-85be6233dbfa)

**Q4. Create a hard link named "hardlink.txt" for the file "document.txt" within the "Documents" subdirectory. Also, create a symbolic link named "symlink.txt" in the same location.**

root@nitesh:/home/MyFiles/Documents# ln /home/MyFiles/Documents/document.txt hardlink.txt

root@nitesh:/home/MyFiles/Documents# ls

document.txt  hardlink.txt

root@nitesh:/home/MyFiles/Documents# 

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/ac17bcf9-58e0-466b-8398-81d4f500fb5c)

root@nitesh:/home/MyFiles/Documents# ln -s /home/MyFiles/Documents/document.txt symlink.txt

root@nitesh:/home/MyFiles/Documents# ls -l

total 8

-rw-r--r-- 2 root root 19 Feb  2 19:04 document.txt

-rw-r--r-- 2 root root 19 Feb  2 19:04 hardlink.txt

lrwxrwxrwx 1 root root 36 Feb  3 14:34 symlink.txt -> /home/MyFiles/Documents/document.txt

root@nitesh:/home/MyFiles/Documents# 

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/dcfd14da-fbec-43e6-aaf4-880ebc590cbf)

**Q5. In the "MyFiles" directory, use a single command to list all files that start with the letter "a" and have a ".txt" extension.**

root@nitesh:/home/MyFiles# touch apple.txt alpha.txt mango.txt laptop.txt almond.bak

root@nitesh:/home/MyFiles# ls

almond.bak  alpha.txt  apple.txt  Documents  hello  laptop.txt  mango.txt

root@nitesh:/home/MyFiles# ls a*.txt 

alpha.txt  apple.txt

root@nitesh:/home/MyFiles# 

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/36c96388-cc07-408d-a882-8decb6081c26)

**Q6. Rename all files in the "Documents" subdirectory of "MyFiles" with a ".bak" extension. Ensure the original file names are preserved.**

**Q7. Use a wildcard character to copy all files from the "Documents" subdirectory of "MyFiles" to another directory named "Backup.**

root@nitesh:/home/MyFiles# cp -r Documents/* /home/MyFiles/Backup/

root@nitesh:/home/MyFiles# cd Backup/

root@nitesh:/home/MyFiles/Backup# ls

abcd.bak  ans.tar  Backup  document.txt  fun.txt  hardlink.txt  lenovo.bak  symlink.txt  yellow.bak

root@nitesh:/home/MyFiles/Backup# cd ..

root@nitesh:/home/MyFiles# cd Documents/

root@nitesh:/home/MyFiles/Documents# ls

abcd.bak  ans.tar  Backup  document.txt  fun.txt  hardlink.txt  lenovo.bak  symlink.txt  yellow.bak

root@nitesh:/home/MyFiles/Documents# 

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/e662e10f-5390-49de-ba4c-4f061b933392)

***Q8. Execute the ls command to list files in the current directory. Save the output to a file named "file_list.txt." Then, use a pipe to filter the output through grep to display only files with a ".txt" extension.**

root@nitesh:/home/MyFiles/Documents# touch file_list.txt

root@nitesh:/home/MyFiles/Documents# ls > ./file_list.txt

root@nitesh:/home/MyFiles/Documents# cat file_list.txt 

abcd.bak

ans.tar

Backup

document.txt

file_list.txt

fun.txt

hardlink.txt

lenovo.bak

my_notes.txt

symlink.txt

yellow.bak

root@nitesh:/home/MyFiles/Documents# grep '\.txt$' file_list.txt

document.txt

file_list.txt

fun.txt

hardlink.txt

my_notes.txt

symlink.txt

root@nitesh:/home/MyFiles/Documents# 

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/5ed3fff7-9424-4e20-b542-5e723e07777e)

**Q9. Create a new text file named "my_notes.txt" using the touch command. Open the file in the Vim editor, add some text, and save the changes.**

root@nitesh:/home/MyFiles/Documents# touch my_notes.txt

root@nitesh:/home/MyFiles/Documents# vim my_notes.txt 

root@nitesh:/home/MyFiles/Documents# cat my_notes.txt 

hello ,this is question 9

root@nitesh:/home/MyFiles/Documents# 

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/a1495fae-92fe-469d-adce-71d03064e958)

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/f3449e0a-c440-4e9b-b695-86ae76494fa0)

**Q10. Run the date command and store the output in a variable named "current_date." Display the value of the variable and append it to the "my_notes.txt" file.**

root@nitesh:/home/MyFiles/Documents# current_date=$(date)

root@nitesh:/home/MyFiles/Documents# echo "Current Date : $current_date"

Current Date : Friday 02 February 2024 11:43:14 PM IST

root@nitesh:/home/MyFiles/Documents# echo "$current_date" >> my_notes.txt

root@nitesh:/home/MyFiles/Documents# ls

abcd.bak  Backup        file_list.txt  hardlink.txt  my_notes.txt  yellow.bak

ans.tar   document.txt  fun.txt        lenovo.bak    symlink.txt

root@nitesh:/home/MyFiles/Documents# cat my_notes.txt 

hello ,this is question 9

Friday 02 February 2024 11:43:14 PM IST

root@nitesh:/home/MyFiles/Documents# 

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/0618e05d-8e5f-4c65-a78d-9daf388511d0)

**Q11. Edit the Bash startup script (e.g., .bashrc) to set an environment variable named "CUSTOM_PATH" to a specific directory path. Ensure the variable is available in new shell sessions.**

root@nitesh:/home/MyFiles/Documents# vim ~/.bash_profile
root@nitesh:/home/MyFiles/Documents# cat ~/.bash_profile
export CUSTOM_PATH="/home/MyFiles"


root@nitesh:/home/MyFiles/Documents# source ~/.bash_profile

root@nitesh:/home/MyFiles/Documents# echo $CUSTOM_PATH

/home/MyFiles

root@nitesh:/home/MyFiles/Documents# 

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/6d041ead-ca40-4984-84d2-828d80732111)

**Q12. Use the echo command to add a new line of text to the "my_notes.txt" file without overwriting existing content. Verify that the new text is appended.**

root@nitesh:/home/MyFiles/Documents# echo "This is a new line of text." >> my_notes.txt 

root@nitesh:/home/MyFiles/Documents# cat my_notes.txt 

hello ,this is question 9

Friday 02 February 2024 11:43:14 PM IST

This is a new line of text.

root@nitesh:/home/MyFiles/Documents# 

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/b35d4516-db4f-45ba-80d6-b66f229e8984)


**Q13. List all files in the "/etc" directory, filter the output to include only those containing the word "conf," and save the result to a file named "conf_files.txt."**

root@nitesh:/home/MyFiles/Documents# ls /etc | grep "conf" > conf_files.txt

root@nitesh:/home/MyFiles/Documents# cat conf_files.txt 

adduser.conf

apg.conf

appstream.conf

avrdude.conf

brltty.conf

ca-certificates.conf

ca-certificates.conf.dpkg-old

dconf

debconf.conf

deluser.conf

e2scrub.conf

fprintd.conf

fuse.conf

gai.conf

hdparm.conf

host.conf

insserv.conf.d

kernel-img.conf

kerneloops.conf

ld.so.conf

ld.so.conf.d

libao.conf

libaudit.conf

logrotate.conf

manpath.config

mke2fs.conf

netconfig

nftables.conf

nsswitch.conf

pam.conf

pnm2ppa.conf

resolv.conf

rsyslog.conf

rygel.conf

sensors3.conf

sudo.conf

sudo_logsrvd.conf

swtpm-localca.conf

swtpm_setup.conf

sysctl.conf

ucf.conf

usb_modeswitch.conf

xattr.conf

root@nitesh:/home/MyFiles/Documents# 

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/80335095-1ce5-4c8e-83c4-ad39292ab1ba)

**Q14. Open the "my_notes.txt" file in Vim. Use Vim's search and replace functionality to replace all occurrences of the word "important" with "critical." Save the changes.**

root@nitesh:/home/MyFiles/Documents# cat my_notes.txt 

hello ,this is question 9

Friday 02 February 2024 11:43:14 PM IST

This is a new line of text.

It is crucial to highlight the important aspects of the project during the presentation.

Understanding the important principles of time management can greatly enhance productivity.

Clear communication is an important factor in fostering strong relationships within a team.

Environmental conservation is an important responsibility that requires collective effort.

Recognizing the important role of education in personal growth is key to lifelong learning.

root@nitesh:/home/MyFiles/Documents# 

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/457074d5-4f98-4479-88fa-2ad328fa84a8)

:%s/important/critical/g

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/d1a3e14d-d59e-4e26-9c46-0c42bbc9902e)

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/279f6b24-d8b0-49f5-846d-07146ee7631d)

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/0f399291-de75-4c0e-b6de-a29306069533)


**Q15. Create a new user account named "john_doe." Set the user's home directory to "/home/john_doe" and assign the user to the "users" group.**

root@nitesh:/home/MyFiles/Documents# useradd -m -d /home/john_doe -g users john_doe

root@nitesh:/home/MyFiles/Documents# passwd john_doe

New password: 

BAD PASSWORD: The password is a palindrome

Retype new password: 

Sorry, passwords do not match.

New password: 

BAD PASSWORD: The password is shorter than 8 characters

Retype new password: 

passwd: password updated successfully

root@nitesh:/home/MyFiles/Documents# 

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/745ddd8a-2d97-42aa-ae4f-f2fc484662c1)

root@nitesh:/home/MyFiles/Documents# cat /etc/passwd

root:x:0:0:root:/root:/bin/bash

john_doe:x:1002:100::/home/john_doe:/bin/sh

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/d0e7ad89-19b3-4bd9-934a-f8ca0b1f6f80)

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/9159be3a-c770-4eda-97d2-c46ca55d4e84)

**Q16. Add the user "john_doe" to the sudoers file, allowing them superuser privileges. Confirm that "john_doe" can execute commands with sudo.**

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/66f9730e-1d99-4ce0-9889-aaf889270548)

nitesh@nitesh:~$ su john_doe

Password: 

$ 

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/065cfead-130e-4da9-bdd7-2d126b192f78)


**Q17. Modify the user account "john_doe" to change the default shell to "/bin/bash" and set the account's expiration date to one month from today.**

**Q18. Create a new group named "development_team." Add "john_doe" to this group and verify the group's existence.**

**Q19. Remove "john_doe" from the "users" group and add them to the "development_team" group. Confirm the changes.**

**Q20. Delete the user account "john_doe" and ensure that their home directory is also removed.**

**Q21. Delete the group "development_team" and ensure that all users previously belonging to the group are appropriately handled.**

**Q22. Implement a password policy that requires users to change their passwords every 90 days. Apply this policy to all existing and new user accounts.**

**Q23. Manually lock the user account "john_doe." Attempt to log in as "john_doe" to confirm that the account is locked. Then, unlock the account.**

**Q24. Use the id command to display detailed information about the "john_doe" user, including user ID, group ID, and supplementary groups.**

**Q25. Configure the password aging for the user "john_doe" to enforce a maximum password age of 60 days. Confirm that the changes take effect.**
