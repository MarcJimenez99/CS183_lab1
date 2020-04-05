# CS183_lab1

## Setting a GRUB Bootloader Password

By creating an encrypted password using `grub2-mkpasswd-pbkdf2` we are able to add it to the custom configuration file.We now are able to hit `e` at the GUB menu to access the GRUB2 line entry. The following image shows the prompt asking us for our encrypted password.

<img src="https://github.com/MarcJimenez99/CS183_lab1/blob/master/lab1pictures/grub%20bootloader%20password.JPG">

## Minimizing services that run at boot time

In order to make our machine more efficient we can customize it to our own specific needs. One way to do this is by changing which services that are run at boot. We can identify which services are running by `systemctl list-units --type service`. Using this list we selected three services to mask which prevents it from being started until it is unmasked. We did this by creating a script known as `lab1.sh`. The following image shows this and gives our explanation of why we chose the services.

<imgsrc="https://github.com/MarcJimenez99/CS183_lab1/blob/master/lab1pictures/lab1.sh.JPG">

After running the script we can see from the command `systemctl list-unit-files --type service | grep mask`, we were successful. 

<imgsrc="https://github.com/MarcJimenez99/CS183_lab1/blob/master/lab1pictures/maskedservices.JPG">

In addition the three chosen services are no longer running when we use the command `systemctl list-unit --type service`.

<imgsrc="https://github.com/MarcJimenez99/CS183_lab1/blob/master/lab1pictures/activeservices.JPG">

## Give an ordinary user privileges to restart the network service

In order to give a user the necessary privileges to restart the network service we must edit the `sudo file`. We do this by logging in as a `root` user and editing the file with the command `visudo`. Next we edit the visudo file to accept our created user `mjime038` when they run the network command. The following photo depicts this:

<imgsrc="https://github.com/MarcJimenez99/CS183_lab1/blob/master/lab1pictures/visudo.JPG">

When our user `mjime038` attempts to run the command it now allows them.

<imgsrc="https://github.com/MarcJimenez99/CS183_lab1/blob/master/lab1pictures/network%20restart.JPG">

It also prevents the user from accessing any other `sudo` command

<imgsrc="https://github.com/MarcJimenez99/CS183_lab1/blob/master/lab1pictures/userSudoCat.JPG">
