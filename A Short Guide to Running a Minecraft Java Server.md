*For Naomi*
# Intro
Running a server isn't that hard. But it's made super confusing and people are gatekeep-y for no good reason. I'm going to write a short, concise-ish, step-by-step guide on how to run your own server from nothing but an install of Minecraft: Java Edition. I'll also include a few helpful troubleshooting tips, as well as guidance on how to install some mods. Take it bit by bit, little by little -- don't overwhelm yourself if you don't get it in the first hour. Slow and steady wins the race. Hope this helps!
# Table of Contents
[[#Server Setup]]
[[#Server Configuration]]
[[#Joining the Server]]
[[#Troubleshooting]]
# Server Setup
It should be mentioned that only the host (you, Naomi) has to perform these steps. Once you've set up your server, anyone else will be able to join super easily (I'll include those steps, too).
## Downloading the Server
First, go to this website: https://www.minecraft.net/en-us/download/server

Click the link to download the server software. It should be pretty quick and show up in your Downloads folder as `server.jar`:
![[Pasted image 20260930193903.png]]
If you try double-clicking this file like you would any other, you'll get an error. Don't worry, this is normal! Computers are dumb and we need to tell them how to read certain filetypes. The next section is going to step you through installing Java onto your computer in order to run the server.
## Downloading Java
What you're going to do next is go to this website: https://learn.microsoft.com/en-us/java/openjdk/download and click to download the file highlighted in this image:
![[Pasted image 20260930231550.png|585]]
The version number might be slightly different, but don't fret! Just look for the most recent version (closest to the top of the page, biggest number after "OpenJDK") and click the `exe` version. This download should also be pretty quick. Then, double click to open the file from your downloads:
![[Pasted image 20260930231831.png]]
You might run into this dialogue box. If you do, click "Install for all users (recommended)". It honestly doesn't make too much of a difference since you're the only user on your computer!
![[Pasted image 20260930231904.png]]
The OpenJDK Setup Wizard will then open. Click "Next," then "I accept the agreement" and "Next." It will then prompt you to "Select Destination Location." Just hit "Next," it doesn't *really* matter where this is. For reference, though, mine looks like this:
![[Pasted image 20260930232135.png|371]]
On the next page, it's going to ask you to "Select Additional Tasks." Make sure these three options are checked, the last one doesn't really matter. If your screen doesn't look like this, let me know and we can troubleshoot!
![[Pasted image 20260930232932.png|378]]
After that just hit "Install" and wait for it to install, it should take less than a minute. Click "Finish" and you've successfully downloaded Java!
## Starting the Server the First Time
First, we're going to make sure our Java installation worked as expected. Hit your Windows key and type "Command Prompt." Right click it and hit "Run as administrator" then "Yes." It should look something like this once you're done:
![[Pasted image 20260930234436.png|612]]
You're then going to type the command and hit Enter:
```
java --version
```
*(Hint: you can copy/paste the commands I write by clicking the little square on the right side of this box and pasting it into your terminal with Crtl+V)*

When you do, the output should look like this (or similar):
![[Pasted image 20260930234542.png|626]]
If you see this, your Java is installed correctly! If not, that's okay, just let me know and we can troubleshoot it.

Now go to your Desktop and create a new folder. You can do this by right-clicking, hovering over "New", and clicking "Folder." Name it something cool like "Naomi's Cool Minecraft Server" (that's what mine is gonna be called for the rest of this tutorial). 

Open up the folder by double clicking it. Then, open your Downloads with another window. You can do that by right-clicking Downloads from your server folder on File Explorer and clicking "Open in new window":
![[Pasted image 20261002194902.png]]
From here you can simply drag and drop the `server.jar` file from your Downloads into your new folder! It should look like this:
![[Pasted image 20261002194959.png]]
Once you've made this folder and moved the server into it, go back to the Command Prompt. Here, you're going to type (or copy/paste):
```
cd 
```
It's *very* important that you include the space (hard to see here) *after* `cd`! Then, you're going to click and drag the folder *from* your desktop *to* anywhere on the Command Prompt and drop it. When you do, the "path" pointing to where the folder lives on your computer should automatically pop up. Then hit Enter and your Command Prompt should look something like this:
![[Pasted image 20261002194504.png]]
Great! You've just **c**hanged **d**irectories (`cd`'d) into your new folder! Pretty cool, huh?

The next bit is easy! A bunch of text will appear on your **console** (Command Prompt, I'll be calling it the console for brevity) after this next step, but don't worry -- this is to be expected. Copy/paste the following command into the Command Prompt:
```
java -jar server.jar
```
When you do, the console will spit out a bunch of garbage you don't really care about. It should look something like the photo below. The **most important thing to look for** here is the *very last line* that should say something like:
```
[ServerMain/INFO]: You need to agree to the EULA in order to run the server. Go to eula.txt for more info.
```
![[Pasted image 20261002202324.png]]

Cool! Now go back to the folder that has your server. You'll notice there are a bunch of new files that weren't in there before:
![[Pasted image 20261002202514.png]]

Right click on the one called `eula` or `eula.txt` and go to "Open with" and click "Notepad":
![[Pasted image 20261002202603.png|481]]

The file should open and only be three lines long. Erase the word `false` and write the word `true`, then save the file (Ctrl+S or File > Save). It should look like this:
![[Pasted image 20261002202742.png]]

It's safe to close this file now, we don't need to use it anymore. We're almost done! Now, go back to the console (Command Prompt). You're going to run the same command you did earlier and hit Enter:
```
java -jar server.jar
```
*(Hint: if you hit up on your arrow keys while in the console, it'll automatically type for you the last command you entered!)*

You might be met with a Windows Defender pop-up when you do this. Don't worry, your computer will be okay! Just click the top box and unclick the bottom box like this and hit "Allow access":
![[Pasted image 20261002203112.png|560]]

***HELL FUCKING YEAH!!!!!*** You just started up a Minecraft Server for the very first time!!! That wile screen that says Minecraft server in the corner?? THAT'S ALL YOU!!! I'm so proud of you dude, that was not easy! Stand up, take a stretch break, get something to drink or maybe a quick smoke before you continue.
# Server Configuration
If you're immediately moving on from [[#Server Setup]], don't forget to close (hit X) on the server window we created. Don't worry, you won't lose your progress -- we'll get it back soon enough!
## Startup Script
So, this was a lot. The Command Prompt stuff, the file management... it's not simple. Or straightforward. Or easy to memorize. So, we're going to make a small file to help us with that! Our goal: to make a file that we can double click to start the server. First, we're going to open the folder with your server stuff from your Desktop (Naomi's Cool Minecraft Server). Then right click, hover over "New," and click "Text Document." Call it something random, this file doesn't really matter. You could even leave it as "New Text Document."
![[Pasted image 20261002221630.png]]

Open the file with Notepad like we did the `eula` file and copy/paste the following text:
```
@ECHO OFF
java -Xms1024M -Xmx2048M -jar server.jar
pause
```
Then, click "File," then "Save As" (or Ctrl+Shift+S). At the bottom, name the file `start.bat` like this and click "Save":
![[Pasted image 20261002223200.png]]

Close this window. Then, double click `start` or `start.bat` (for me it's just `start`) to run it. When you do, the console (Command Prompt) will open, run the command to start the server, and pull it up for you. It's like magic!
## Adding People to your Server
Of course, the whole reason to set up this server is to play with your friends. So let's make sure they can join in! We're going to build what's called a *whitelist* -- basically, a list of users we know are safe to access the server (e.g. people that won't grief you and ruin your beautiful world). If you're only adding a handful of people, the following is the most straightforward way (in my opinion) to accomplish this.

First, if it's not already open, use your `start` or `start.bat` file to start the server. After it starts up (give it a second until it stops sending you messages and the white window pops up), click on the console (Command Prompt). Then, ask your friend for their Minecraft username (see [[#Getting a Minecraft Username]] \[<-- click\] for more guidance on this) and copy/paste the following command into the console:
```
/whitelist add username
```
Instead of `username`, you'll write the name of your friend. For example, if the username is `naomi_coolguy`, I would type: `/whitelist add naomi_coolguy`. When you do that, the console will look like this:
![[addinguser.png]]
Don't forget to add yourself to the whitelist. You do want to play on your own server, after all! If you want to learn more about whitelists and how to be more granular with your configuration, check out the official [Minecraft Wiki on Whitelists](https://minecraft.wiki/w/Tutorial:Setting_up_a_Java_Edition_server#Whitelist).
### Getting a Minecraft Username
Click here to go back to the section on [[#Adding People to your Server]] when you're done!
#### Minecraft Launcher
If you're not sure how to find your Minecraft username, you can easily find it by doing the following. Open your Minecraft Launcher, then hit "SETTINGS" in the bottom left-hand corner. Then, at the top, click "Accounts." This should pull up the following page. I have anonymized my account (totally not because my account name and username are embarrassing), but it should show your account name on top and username on the bottom. If you're confused by which is which, your account name should also be in the top left-hand corner of this screen:
![[minecraftusername 1.png|297]]
#### Minecraft: Java Edition
If you're unsure of the previous method or the Launcher has changed (as it is known to happen), you can always find your username in the actual game. To do this open the Launcher and start Minecraft: Java Edition. On the starting page, click on the "Friends" menu:
![[Pasted image 20261002230138.png]]
You might have to accept some legal thingy, but then you'll get to this screen with your username:
![[usernameingame.png]]
# Joining the Server
Wow, look how far we've come. It's almost time to open up your first vanilla Minecraft: Java Edition server. For this first-time setup, we're going to make this server a Local Area Network (LAN) server. What this means is that only people directly connected to your Wi-Fi will be able to join your server. Unfortunately, you will not be able to play with people that are not directly inside your home connected to your same network. Eventually I will add a section to enable this called "Port Forwarding," but that's much more involved and won't get you playing tonight. Let's make a LAN party!
## Joining via LAN
To join the server via LAN, all you need is one thing -- your computer's IP address. Since we've already been messing around in the console (Command Prompt) a bit in this guide, let's learn a new command! Open the console, type the following command, and hit Enter:
```
ipconfig
```
The console should output the following. Take note of the information here; possibly jot it down somewhere you'll remember or make a text file with it so you don't forget it:
![[ipaddress.png|606]]

Now, start up the server by double-clicking your `start.bat` file. Once that's up, open your Minecraft Launcher and start Minecraft: Java Edition. On the title screen, click on "Multiplayer." There might be more legal stuff, but eventually you'll get to a screen titled "Play Multiplayer." At the bottom center of the screen, there will be a button that says "Direct Connection." Click it, and type your IPv4 Address in the box that says "Server Address." It should look like this:
![[Pasted image 20261003001744.png]]
When you're done typing the Server Address, click "Join Server."

![[Pasted image 20261003002136.png]]
***WOOOOOOOO YEAAAAAAAAAAHHHHHH*** \[hacker voice] I'M FUCKING IN BABY!!!!!
That should honestly be it! As long as the server is running on your computer, you and whoever else is on your whitelist and on your network will be able to play as much Minecraft online as you'd like -- completely for free, without ads or needing to pay for Realms!
# Troubleshooting
TODO
## Java Installation
TODO
## Server Initialization
TODO
## Startup Script
TODO
