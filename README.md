# Linux Basic Command
    NOTE :- 
    (1) IAM TRYING TO MAKE THIS NOTES EASIER TO READ      
    (2) I HAVE JUST GIVEN MOST BASIC AND USED COMMANDS AND
     THERE OUTPUT IS NOT THERE IN THIS FILE/PAGE BUT HOPE YOU WILL LEARN BY YOUR OWN BY USING THESE COMMANDS.
    (3) > (greater than symboll) indicates that this is a new command in the terminal.

open terminal and start your journey in learning the basic of linux i.e., Basic Commands. 
My name is kishan kumar so, user name for my system is kishan

-----------------------------------------------------------

##      # ---> it indicates a root user

ex:- root@KISHAN-WINDOWS-M:/home/kishan#


##      $ ---> it indicates a local user

ex:- kishan@KISHAN-WINDOWS-M:~$

------------------------------------------------------

## Then how to switch from local user to root user

-> by default when we open the terminal we will be local user.

-> so below is the command to switch to root user from local user

    > sudo bash

now, below is the command to exit from from the root user, 

    > exit

---------------------------------------------------------------

# (1) FILE COMMANDS

NOTE:- The term "FOLDER" or "DIRECTORY" are same.

```bash
> ls -al or ll           => Lists files - both regular & hidden files and   their permissions as well.
> ls                     => only files
> ls -a                  => all types of files including hidden file
> pwd                    => Displays the current directory file path
> mkdir ‘directory_name’ => Creates a new directory
> rm file_name           => Removes a file
> rm -f filename         => Forcefully removes a file
> rm -r directory_name   => Removes a directory recursively
> rm -rf directory_name  => Removes a directory forcefully and recursively
> cp file1 file2         => Copies the contents of file1 to file2
> cp -r dir1 dir2        => Recursively Copies dir1 to dir2. dir2 is created IF it does not exist
> mv file1 file2         => Renames file1 to file2
> touch file_name        => Creates a new file
> cat > file_name        => Places standard input into a file
 
```
========================================================================================================================
# (2) Directory traverse
```bash

> cd ..                  => move back to previous directory   
> cd 'directory_name'    => move inside 'directory_name' from current directory
> cd /test    => Change directory to /test directory
```
below are the example for directory traverse perform in git bash of windows10.

[SOME OF THE BASIC COMMANDS OF LINUX CAN BE USED IN GIT ALSO ]

``` bash

>> using "ls" command we checked the folders,files present in linux directory(folder) and we found 2 folders.

            KISHAN@KISHAN-WINDOWS-M MINGW64 ~/Desktop/linux
            $ ls
            folder1/  folder2/

>> using "cd" command along with folder present in current directory we can go/move into that particular folder. Here we moved into "folder2"

            KISHAN@KISHAN-WINDOWS-M MINGW64 ~/Desktop/linux
            $ cd folder2
            
            KISHAN@KISHAN-WINDOWS-M MINGW64 ~/Desktop/linux/folder2
            $ touch readme.md
            
            KISHAN@KISHAN-WINDOWS-M MINGW64 ~/Desktop/linux/folder2
            $ ls
            readme.md
            
            KISHAN@KISHAN-WINDOWS-M MINGW64 ~/Desktop/linux/folder2
            $ cd ..
            
            KISHAN@KISHAN-WINDOWS-M MINGW64 ~/Desktop/linux
            $ ls
            folder1/  folder2/
            
            KISHAN@KISHAN-WINDOWS-M MINGW64 ~/Desktop/linux
            $

```

restart network
```bash
> sudo systemctl restart network
> sudo systemctl restart NetworkManager
```

========================================================================================================================
# (3) vim/vi editor command 

to open vi editor we should give below command with file name, in our case the filename is file1,txt.  

    > vi file1.txt

to enter into edit mode below are the keys to be pressed on the keyboard.

> ===> i,I,a,A,o,O,r,R

to exit from edit mode we press Esc key.
> esc

## NOTATION:-
## (i)  edit mode keys

>     i - insert from the current location
>     I - insert from beginning
>     a - append from next charector
>     A - Append from end of the line
>     o - open a new line
>     O - open a new line above
>     r - replace a single charector
>     R - replace continous still esc

------------------
## (ii) save the file 
while exit we press below any 1 keys.

while pressing below key make sure you are out of edit mode.

>     :w - save
>     :q - quit
>     :wq - save & quit
>     :x - save & quit
>     :e! - total undo
>     :wq! - save & quit by force
>     :q! - quit by force
-------------------

## (iii) CUT COPY & PASTE
make sure you type below word outside the edit mode i.e., press "Esc" key then follow below operation

### (i) copy & paste

>     > yw
>     > p
>     > yy
>     > p

"yw" indicate copy the word it will start where the cursor is located in the vi editor.

"yy" indicate copy the entire line

"p" is for pasting the word or line which is copied, make sure your cursor is in right position where you wanted to paste.

We can also use number to copy the word and number of lines.
if your cursor is in middle of word then from that character it will copy based on number you given.  

>     > 6yw 
>     > p
>     > 9yy 
>     > p

### (ii) cut & paste

while pressing below key make sure you are out of edit mode.

    
>     > dw
>     > p
>     > dd
>     > p

"dw" indicate cut the word it will start where the cursor 
is located in the vi editor.

"dd" indicate cut the entire line

"p" is for pasting the word or line which is cutted, make 
sure your cursor is in right position where you wanted to 
paste.

We can also use number to cut the word and number of lines.
if your cursor is in middle of word then from that 
character it will cut based on number you given.  

>     > 7dw 
>     > p
>     > 5dd 
>     > p
-----
## (iv) CURSOR MOVEMENT.
 while pressing below key make sure you are out of edit mode.

>     h - left movement 
>     l - right movement
>     j - down
>     k - up
> ------------------------------------
>     x - del key
>     X - Backspace key

----
## (v) set
while pressing below key make sure you are out of edit mode.
>      :set nu
>      :set showmode
>      ===========================
>      :number  --> jump to that line
>      /word    -->highlight all word and use "n" & "N" to jump between words
>             n -> top to bottom
>             N -> bottom to top
  
 
==================================================================================================================================
# (4) inode number

## hardlink

## softlink/shorcut
1. file shortcut
>     cd
>     ln -s demo/file1.txt shortcutfile1.txt
>     ll
>     cat >> shortcutfile1.txt
>     ll -i demo/
>     cat shortcutfile1.txt

2. folder shortcut
>     cd
>     ln -s demo shdemo
>     ll -i
>     cd shdemo/
>     ll -i

=================================================================================================================================================
# (5) absolute path and relative path

(i) absolute path

when we give entire file path for specifying file or folder we use absolute path.

it can be used in copy,paste, and other command of terminal .

        > cd
        > cd /home/user/demo/
        > /usr/bin/cd /home/user/demo/

(ii) relative path

it is used when we want to enter to next folder from current folder

    > cd
    > cd demo/

(iii) extra commands

    > which cd
    > which ls
    > echo $PATH

# (5) IO REDIRECTORS
1. STDIN    < << <<< 
2. stdout   > >>
3. STDERR   2> 2>> 2>&

(i) STDIN

    > cat < file1
    

    > cat > file2 << eol
    > hi 
    > i am 
    > typing
    > eol
    

    > cat <<< hello
    > echo hello
 
(ii) STDOUT

     > cat > file1
     > cat >> file2
     > ll > file1
     > sudo /bin/ls -l >/dev/tty4
     > tty
     > cat
     > cat>file1
     > cat file1
     > cat file1>file2
     > cat file2
     > cat file1>/dev/null

(iii) STDERR
 
    find / -name passwd
    find / -name passwd 2> permission_denied
    ls
    cat permission_denied
    cat > file1 2> errout
    caat > file1 2> errout
    cat errout
    cat > file1 2>> errout
    ccat > file1 2>> errout
    catt > file1 2>> errout
    cat > file1 2>> errout
    catt > file1 2>> errout
    cat file1
    cat errout
    catt > file1 2>&
    catt > file1 2>&1
    cat file1
    cat > file1 2>&1
    cat file1
    ccat > file1 2>&1
    cat file1
    ccat >> file1 2>&1
    cat >> file1 2>&1
    cat file1
    cat >> file1 2>/dev/null
    ccat >> file1 2>/dev/null
    cat file1
 
# (6) | ; tee commands

    > cat color |sort
    > cat color |sort|uniq
    > cat color |sort|uniq|wc -l
    > mkdir -p fold1;cd fold1;mkdir -p fold2;cd fold2;touch file1; 
    > cd ../..;ls -lRt

    >  mkdir -p fold1;cd fold1;mkdir -p fold2;cd fold2;touch file1;cd ../..;    
    > ls -lRt
    > mkdir -p fold1;cd fold1;mkdir -p fold2;cd fold2;touch file1;cd ../..;
    > ls -lRt|tee file123


# (7) GREP
    > grep root /etc/passwd
    > grep root /etc/group
    > grep ^root /etc/passwd
    > cat > color1
        red blue green orange yellow
        yellow blue green orange red
        Red blue yellow green orange
        Ornage yellow blue green
    > grep red color1
    > grep ^red color1
    > grep ^Red color1
    > grep orange color1
    > grep orange$ color1
    > grep -i red color1
    > grep -i ^red color1

# (8) cut & paste
    > cat /etc/passwd
    > cut -d ":" -f1 /etc/passwd
    > cut -d ":" -f2 /etc/passwd
    > cut -d ":" -f3 /etc/passwd
    > cut -d ":" -f4 /etc/passwd
    > cut -d ":" -f5 /etc/passwd
    > cut -d ":" -f6 /etc/passwd
    > cut -d ":" -f7 /etc/passwd
    > cat > passwd1
         user group userid password
         hari admin 101 hari
         vasu user 102 vasu
         siva user 103 siva
    > cut -d " " -f1 passwd1
    > cut -d " " -f2 passwd1
    > cut -d " " -f1 passwd1|tee f1
    > cut -d " " -f2 passwd1|tee f2
    > cut -d " " -f3 passwd1|tee f3
    > cut -d " " -f4 passwd1|tee f4
    > cat f1 f2 f2 f4
    > paste f1 f2 f3 f4
    > paste f4 f1 f2 f3
    > paste -d "+" f2 f1 f4 f3
    > paste -d "+" f2 f1 f4 f3|tee newpasswd1
    > cat newpasswd1
    > cut -d "+" -f1 newpasswd1

# (9) head tail more less

    > head /etc/passwd
    > tail /etc/passwd
    > more /etc/passwd
    > less /etc/passwd

head will give first 10 lines of a file
tail will give last 10 lines of a file

    q to quit
    : number  --> go to that line
    /Word     --> type "n" top to bottom movement
                       "N" left to right movement

# (10) sed

 iam working on this command
======================================

# (11) USER MANAGEMENT
(i) User creation

     > sudo adduser nikki
for verify wether user is created or not  go with below commands

    > tail -1 /etc/passwd
    > grep nikki /etc/passwd

password setting

>     sudo passwd nikki
>    


(i) user creation

      > sudo adduser nuser1
      > tail -1 /etc/passwd
      > grep nuser1 /etc/passwd
      > tail -1 /etc/group
      > sudo tail -1 /etc/shadow
      > sudo passwd nuser1
      > sudo adduser -s /bin/csh nuser2
      > sudo tail -1 /etc/passwd
      > sudo mkdir /home1
      > ls -ld /home1 /home
      > sudo adduser -u 2001 -g wheel -d /home1/nuser3 -m -c "developer" -s /bin/csh nuser3
      > tail -1 /etc/passwd
      > sudo passwd nuser3
      > su - nuser3
 -----------------------------------------------
      > sudo mkdir /basehome
      > sudo useradd -d /basehome/nuser5 -m nuser5
      > grep nuser5 /etc/passwd
      > sudo passwd nuser5
      > su - nuser5
================================================

sed - sequence editor
======
    > cat myunix
          unix is great os. unix is opensource. unix is free os.
          learn operating system.
          unix linux which one you choose.
          unix is easy to learn.unix is a multiuser os.Learn unix .unix is a powerful.

    > sed 's/unix/Linux/' myunix
    > sed 's/unix/Linux/1' myunix
    > sed 's/unix/Linux/2' myunix
    > sed 's/unix/Linux/g' myunix

(ii) usermod

    > grep nuser5 /etc/passwd
    > sudo usermod -s /bin/csh nuser5
    > grep nuser5 /etc/passwd
    > sudo usermod -u 4004 nuser5
    > grep nuser5 /etc/passwd
    > sudo usermod -L  nuser5
    > sudo grep nuser /etc/shadow
    > sudo usermod -U  nuser5
    > sudo grep nuser /etc/shadow

(iii) userdel

    > ls -l /home
    > ls -l /home1
    > ls -l /basehome/
    > sudo userdel nuser5
    > grep nuser5 /etc/passwd
    > grep nuser5 /etc/group
    > sudo grep nuser5 /etc/shadow
    > ls -l /basehome/
    > sudo userdel -r nuser4
    > grep nuser4 /etc/passwd
    > grep nuser4 /etc/group
    > sudo grep nuser4 /etc/shadow
    > ls -l /home1
    > sudo userdel -r nuser3
    > sudo userdel -r nuser2
    > sudo userdel -r nuser1
    > sudo userdel -r nuser
    > ls -l /home
(iv groupadmin

    > groupadd gp1
    > groupadd -g 4001 gp2
    > groupmod -g 4002 gp1
    > groupmod -n newgp1 gp1
    > groupdel gp1
    > groupdel gp2


=======================================================================================

# Introduction to networking

OSI Layers
7 layermodel
------------
     application
     presentation
     session
     trasport
     network
     datalink
     physical
=================

cisco 4 layer
-----------------
     IP address
     A - 0 - 126 (127 - loopback)
     B - 128 - 191
     C - 192 - 223
     ----------unicast - one to one - computers needs


     D -224 - 239
     ----------multicast - one to many


     E - 240 - 255
     ----------boradcast - one to all

## subnet mask
-----------
FLSM:- FULL LENGTH SUBNET MASK

    A 1.0.0.1 - 126.255.255.255 / 255.0.0.0 (/8)
    B 128.0.0.1 - 191.255.255.255 / 255.255.0.0 (/16)
    C 192.0.0.1 - 223.255.255.255 / 255.255.255 (/24)
 
CIDR - Classless inter domain routing 

VLSM - Variable length subnet mask

## subnetting / supernetting

subnetting - deviding the existing subnet into smaller groups

supernetting - add subnets to make a bigger group

### netwroking commands

     > ip a
     > ip addr
     > ifconfig 
     > ifcongig -a
     > ifconfig enp0s3
     > ifconfig lo    (loopback)
     > ifconfig enp0s8
     > ifconfig lo|grep inet|grep -v inet6
     > ifconfig enp0s3|grep inet|grep -v inet6|awk '{print $2}'
     > ifconfig enp0s8|grep inet|grep -v inet6|awk '{print $2}'

 mac address enp0s8

-   > ifconfig enp0s8|grep ether|awk '{print$2}'

host name

    > hostname
    > hostnamectl
to change hostname
    > sudo hostnamectl set-hostname centos1.example.com


type bash so the update take place immidiate
    > bash
    > hostname
    > hostnamectl


#local dns

    > hostname -i
    > vi /etc/hosts
    > bash
    > sudo vi /etc/hosts
>           add in last line
>           G
>           o
>           192.168.225.3   centos1.example.com     centos1
           



    > cat /etc/hosts
        192.168.225.3   centos1.example.com     centos1

..

    > ping centos1
    > ping centos1.example.com
    > hostname
    > hostname -i  




# Thank you
