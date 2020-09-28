# Communication with the Raspberry Pi through SSH (Secure Shell)

References:

- https://www.raspberrypi.org/documentation/remote-access/ssh/
- https://magpi.raspberrypi.org/articles/ssh-remote-control-raspberry-pi
- https://www.simplified.guide/ssh/copy-file

## 1 Figure out your IP adress

Simply write 

```shell
ifconfig
```
into the terminal of your raspberry pi. You will need the ip adress to establish a SSH connection.

![](images/SSH2.png)

You may also see your IP in your start screen. 

![](images/SSH1.png)

The IP here in our VM is 192.168.226.255. If this does not work you can also try to use the adress you get from

```shell
hostname -I
```

Here we got 192.168.0.57

## 2 Enable a SSH connection in your Raspberry Pi

Click on the Raspberry Pi icon on the menu. Then go to ``` Preferences > Raspberry Pi Configuration```

![](images/SSH3.png)

Go to ``` Interfaces > SSH ```. Click on enabled and we're set. 

![](images/SSH4.png)

Now go back to your computer/host machine, open up the terminal and write the command

```
ssh raspberrypi_user@ip_adress
``` 

so, in our case we'd write

```
ssh pi@192.168.0.57
``` 

since I got the adress from the hostname command. When prompted to answer write *yes* and you'll have acess to your raspberry from your host machine:

![](images/SSH5.png)

## 3 Openning existing files

To check out the stuff we can do with SSH let's make a quick test. Go to your homefolder in the raspberry pi/virtual machine and create a text file called *ssh_hello_world*, either graphically or through the terminal. 

![](images/SSH_Test1.png)

Now, we can use the text editor *nano* to open this text file. Just write:

```
nano ./ssh_hello_world
```

And we're done! Now just edit the file however your wish.

![](images/SSH_Test2.png)

## 4 Sharing and copying files

Here we'll show how to send files from your host machine to your raspberry pi. First of all, create a folder on your home directory (in the host machine), called *PiShare*. You can write

```(shell)
mkdir PiShare
``` 

Do the same for the Raspberry Pi, you can create a folder called *PiShareReceive* for example. Now, create a text file called *SSH_Test* in the folder *PiShare* and write something on it. We'll try to open this file in the Raspberry Pi. To do that, use the *scp* command

```
scp PiShare/SSH_Test pi@192.168.0.57:PiShareReceiver
``` 

![](images/SSH_Test3.png)

in general what you do is

```
scp local_folder/local file remote_user@remote_adress:remote_folder
``` 

you can also do the same from the remote to the local! After the end of the process you will see the copied file in the remote location:

![](images/SSH_Test4.png)
