+++
title = 'Fileshare'
date = 2024-07-29T16:13:17+05:30
draft = false
tags = [""]
Categories = [""]
+++


## Intro
windows file sharing is very important this days especially when you are working in IT company, you need to ask files from your colleague desktop or you need to draw some file from another computer or you may need to share study materials from favourite friends then this one is for you 
\
and important things is that I would mention what ever **errors** I got, those fixes also explained 

lets get started !

## folder 
ok now to share the files first you need to select the file which you want to share, so i am sharing some **sharing** folder which there is a shared.txt file which is my d drive 
![alt text](<Pasted image 20240729095436.png>)


right now i want to share or host the folder called sharing now for that go to the sharing folder 
![](<Pasted image 20240729095601.png>)
go to the 
1. properties 
2. sharing tab 
3. click on share 

![](<Pasted image 20240729095741.png>)
now you would see the the users where who want to access 
![](<Pasted image 20240729095921.png>)

when you click the arrow down button you can see different types of articles 
1. users in you desktop computer 
2. everyone 
3. create a new user 
### concept 
1. first option is the folder which you want to share with  the other user in your computer 
	1. why i need make things to share with other user : 
		well in some cases the company or the other user will restrict the drive access to the other user so that they can maintain their secret folders 
2. everyone is recommended because it will share to everyone not only with the internal user but also private network devices 
3. create new user : you can give the user name which is only device which is connected to the network right 
you know the concept now 

what you want to chose : well i recommend to **share with everyone** for newbie because it will easy to move on with out any errors 

now ok 

go to advance sharing and then click the check box of share this folder 

![](<Pasted image 20240729101831.png>)
now the folder setting is over 

here comes the networking part 
## networking part 
you set the what to share part in this part the you have to tell system to all the access of network so that other can share my file kind of that so first we need to open settings 
here windows 10, 11 are different windows but the settings are same 

here i am showing windows 11 where you may have windows 10 then the window will be control panel and 11 will be default settings window 
right lets jump into 

go to control panel 
![](<Pasted image 20240729124806.png>)

NEXT : network and internet 
![](<Pasted image 20240729124907.png>)
NEXT: network and sharing centre

![](<Pasted image 20240729124930.png>)
NEXT: next change advanced sharing settings

now in windows 11 you may go to the default settings but in 10 still control panel dont panic right 
![](<Pasted image 20240729125107.png>)
now you can see the window like this 
### conceptual things now 
1. public network is where you have the devices want to connect from the outside the network well that's very complicated we need to host the things via services well am not going to that part 
2. private network : now this is the important part because you have the wifi or lan or any network your device and other devices also connected on a network and they are having a ipv4 address well now if we tweaks the settings then what ever you do happen in private network this is the settings probably you are going to use 
3. all network which is both of above 
### settings part 
you can see network discovery and sharing 
only things you need to remember is these two 
#### what is network discovery 
this option is used to show you on network where other will see you on the network like this on the file network as show on below 
![](<Pasted image 20240729130040.png>)

![](<Pasted image 20240729130124.png>)

as shown on the above diagram the what ever the devices is discovery is on then the device will show on the file manager else no 

some time even though you on the settings the device will not discovered do panic still you can connect to the device i will show on the **connection section** 


**right if you need to share the file without error better to turn on netowork discovery and sharing button to ON** 

else better stick with the private network 
and make sure 

password-protected sharing is also enabled because this is kind of best practise to hare files securely 

## connecting 

if your device is visible on the network directory file manager then no need to worry if not 

on the search settings 

![](<Pasted image 20240729130511.png>)
type
```
\\pc_name
```

if you don't know the pc name just go to 
1. windows start 
2. View your PC name
3. on the device name you can find the name of your pc_name

later enter the password and boom 
you will see the what ever files you want to share 

after typing your pc name still it doesn't pop up login id and password 
make sure the above 2 settings configured properly or not 

## turn off sharing
right if you want to turn off the sharing just go to the folder and 
1. properties 
2. sharing tab
3. advance sharing 
4. untick the share this folder 

right this is it now you know the how to share the file from one pc to another pc via lan/wifi/any network 

if anything wrong in this article or feedback go to my social media handles and message me there …. 
I will see you in the next article …peace !