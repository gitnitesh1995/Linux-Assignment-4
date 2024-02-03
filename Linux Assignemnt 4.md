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

**Q. 10Run the date command and store the output in a variable named "current_date." Display the value of the variable and append it to the "my_notes.txt" file.**

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


