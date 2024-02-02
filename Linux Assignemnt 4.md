**Create a directory named "MyFiles" in your home directory. Navigate into this directory and list its contents.**

![Screenshot from 2024-02-02 15-33-14](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/1a964d38-a48b-49f2-870b-34cf50e4b7a5)

**Copy a file named "document.txt" from your home directory to the "MyFiles" directory. Move the file to a subdirectory named "Documents" within "MyFiles.**

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

**Create an empty file named "notes.txt" in the "MyFiles" directory. Afterward, delete the file.**

root@nitesh:/home/MyFiles# touch notes.txt
root@nitesh:/home/MyFiles# ls
Documents  hello  notes.txt
root@nitesh:/home/MyFiles# rm notes.txt
root@nitesh:/home/MyFiles# ls
Documents  hello
root@nitesh:/home/MyFiles# 

![image](https://github.com/gitnitesh1995/Linux-Assignment-4/assets/61899084/ec68e50d-75eb-4e32-bbf1-85be6233dbfa)
