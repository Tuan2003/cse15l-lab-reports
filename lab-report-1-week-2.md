# Week 2 Lab Report

Welcome 15L students! You will be learning how to log in remotely to your course specified **ieng6** account. This account will allow you to access the UCSD linux computers remotely from anywhere as long as you have an internet connection. 

***

## Installing Visual Studio Code: 
1. Click on this link to access the website to download [Visual Studio Code](https://code.visualstudio.com)

2. You should be able to see this screen when you click on the hyperlink. ![Image]/Images/(vscodedownloadpage.png)

3. The big blue button may show up as something different depending on the device you are using. Don't be discouraged if you see something different. 

4. Click on the blue button that shows "Download Mac Universal." This may show up as "Download Windows User Installer" or even "Download Linux .deb" 

5. Go through the installation process and you should see this once it is fully installed and loaded up. ![Image](/Images/vscodeloaded.png)

***

## Connecting Remotely

1. Individuals using a Windows based machine should install [OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse) Follow the instructions on this page to install OpenSSH on your device. MacOS and Linux users do not need to go through this step as SSH should be already installed on your device. 
2. Navigate over to this [link](https://sdacs.ucsd.edu/~icc/index.php) to find your UCSD course-specific account for CSE 15L type in your username and password used to access your student account and you should be able to see your course provided account beginning with 
> cs15lsp22 

3. Open Visual Studio Code and go to the top of the navigation. ![Image](/Images/navigation_tab.png)

4. Click on Terminal -> New Terminal to create a new terminal. You can also use press Control + Shift + ` to create a new terminal using your keyboard.

5. Type in the line below but replace the 'xxx' with the letters following 'cs15lsp22' with the letters provided with your course specific account.

> ssh cs15lsp22xxx@ieng6.ucsd.edu

6. Once you enter in this line you should be prompted with a password and this password is the password that you use to login to your student account. Don't worry, the password is hidden for security purposes. 

7. When you successfully log in you should see the following show up in your terminal. ![Image](/Images/loggedintocs15l.png)

***

## Running Commands

### There are many things you can do with SSH, you can even run these commands on your own local computer. Provided below are some commands that you can try at your own convienience, try to figure out what these commands do on your local computer vs. on the remote computer. 

1. ```cd ~```
2. `cd `
3. `ls -lat`
4. `ls -a`
5. `cp`

Provided below are some more ssh commands you can use.

![Image](/Images/sshcommands.png)


*** 
## Moving files using SCP

### We will be moving a file from your local machine to the remote machine via the command line *scp*.

1. Let's get started by creating a file that we want to copy over to the remote machine. Try creating a java file *HelloWorld.java* that prints to the console

``` Hello World! ```

![Image](/Images/HelloWorld.png)

2. Use the line provided below to remotely transfer your *HelloWorld.java* class to your remote machine. Replace xxx with the letters provided to your own account. You should be prompted to type in your password again so provide that in order to transfer the file. 

```ssh HelloWorld.java cs15lsp22xxx@ieng6.ucsd.edu:~/```

3. Once you are logged in and the file has transferred over try running

```javac HelloWorld.java```

Then, 

```java HelloWorld```

4. If the following works then you have successfully transferred a file from your local machine to the remote machine. 

***

## Setting up an SSH Key

### You may have realized that it has gotten annoying always being prompted to type in your password every time you try to log into the remote machine. We will make this process a lot more easier and quicker by setting up an SSH key, which won't require the use of you (the user) from having to type in a password every time when you want to log into the remote machine. 

1. Open up a new terminal in Visual Studio Code or using your computer terminal type in the command line below in order to see the following pop up. **Do not add a passphrase.**

```ssh-keygen ```

![Image](/Images/sshkeygen.png)

> The C:\User\<username>/.ssh/id_rsa directory may be different depending on the device you are using. 

2. Next step in this process is to copy our public key onto the remote machine. 

```
$ ssh cs15lxxx@ieng6.ucsd.edu
Password: 

Logged into server

$ mkdir .ssh

exit

Back onto the local machine

$scp C:\Users\<username>/.ssh/id_rsa.pub. cs15lsp22xxx@ieng6.ucsd.edu:~/.ssh/authorized_keys


```

3. Once you have done this you should be able to log onto the remote machine/server without needing to type in a password every time. 

***

## Optimizing Remote Running

1. Now that you've fully setup and made the process of logging onto the server a lot more easier, now we can try things like:

![Image](/Images/sshcmdline1.png)

Or even,

![Image](/Images/sshcmdline2.png)

2. These commands will be ran when you are connected to the remote machine. You are not limited to these commands for SSH so let you imagination run wild. 





