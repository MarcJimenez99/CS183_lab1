# CS183_lab1

## Setting a GRUB Bootloader Password

By creating an encrypted password using `grub2-mkpasswd-pbkdf2` we are able to add it to the custom configuration file.We now are able to hit `e` at the GUB menu to access the GRUB2 line entry. The following image shows the prompt asking us for our encrypted password.

<img src="https://github.com/MarcJimenez99/CS183_lab1/blob/master/lab1pictures/grub%20bootloader%20password.JPG">

## Minimizing services that run at boot time

In order to make our machine more efficient we can customize it to our own specific needs. One way to do this is by changing which services that are run at boot. We can identify which services are running by `systemctl list-units --type service`. Using this list we selected three services to mask which prevents it from being started until it is unmasked. We did this by creating a script known as `lab1.sh`. The following image shows this.

<img src ="https://github.com/MarcJimenez99/CS183_lab1/blob/master/lab1pictures/lab1.sh.JPG">

After running the script we can see from the command `systemctl list-unit-files --type service | grep mask`, we were successful. 

<img src ="https://github.com/MarcJimenez99/CS183_lab1/blob/master/lab1pictures/maskedservices.JPG">

In addition the three chosen services are no longer running when we use the command `systemctl list-unit --type service`.

<img src ="https://github.com/MarcJimenez99/CS183_lab1/blob/master/lab1pictures/activeservices.JPG">
