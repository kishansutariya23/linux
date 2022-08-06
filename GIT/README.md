# GIT commands

- To check the version of the git in local system

    >    $ git --version

- Now open the folder which you want to track changes or want to upload in GITHUB and copy the path of that folder then paste in place of PATH(see the command below) in terminal/cmd promt/gitbash as mention below.

    - NOTE:- Make sure you place it in double quotes as terminal will give you error incase of space present in folder name like --> folder name = kishan kumar 
    
        >$ cd PATH 

        example:- 

        > $ cd "C:\D drive\Website\kishansutariya23.github.io"

- Now to make the present directory/folder as git specific folder we have to initialize git in it.

    > $ git init

- Now configure your git with your user name 
     - Below code will give user name if already you configured 
        > $ git config --global user.name  
    - If not configured then use below code  
         - Make sure you give your user name in double quotes in place of kishansutariya23  
        > $ git config --global user.name "kishansutariya23"  

- Now configure email ID because in future we need to give password/auth.. only  when we try to push our code in GITHUB.  
 
    >$ git config --global user.email "kishansutariya7533@gmail.com" 

 
NOW make changes like placing some content(folder/files) in this directory which you want to upload in github.

- Below cmd is used most for tracking the changes 
    - You will get red colored file/folder indicating that they are yet to stage.
    - Green colored file/folder indicated they have been commited.
    >$ git status
- When ever you want to add file in github you have to make them place in stagging area.

    - dot(.) in below command indicates all files/folder  
    >$ git add .
- After adding you can see the status of file in git lifecycle you will be surprised that they are in 
    >$ git commit -m "init commit"

- Check the branch with below cmd
    
    You will gind out that you are on master branch [*master] 
    
    star * indicate the your current branch as in future you might create more number of branch and by looking * you will get to know your branch status.  
    >$ git branch    
    - Below is cmd to change the branch name to main as in github default branch will be main branch.
        >$ git branch -M main   

- Now add the all file in your github by below command.
    - first time while you upload you are supposed to give password of your github account and go auth..
    - in place of LINK you are supposed to place the empty director/repository of github where you want to place your files/code/folder.

   >$ git remote add origin ***LINK***
- Below is the last command to push your entire folder #current_folder where git is initialized.
  >$ git push -u origin main
 --------------

 
=====================Hurry You have successfully pushed your folder into github and go to github repository and refresh the page and you will see all files over there==================


----------

>$ git restore file_name   
##### if you think that changes made to file were not goood and you have NOT commited then you will get your file back.

###### you worked more on fileas and done commit ALSO.
###### as you have already pushed the file in github, now we no need to give our entire url for pushing our content/files/folder. Just give -v  

>$ git remote -v 

>$ git push origin main


###### if you want to track entire commit and upload again from new system then clone is the best option

>$ git clone ****paste_the_link_from_github_clone_tab***

====


$
$
$
$
$
$
$
$
$
$
$
$
$
