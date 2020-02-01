# BUILDING A MOBILE APP WITH CORDOVA

## Table of contents
* Installing Cordova
* Creating a project in Cordova
* Installing Cordova to our created project
* Installing Android Studio 
* Migrating your native built app to cordova
* Setting up your android phone

## Installing Cordova
Firstly, create your project folder and open it in Vs Code, then
Open your Bash terminal in Vs Code
Type this code 

```npm
$  npm install cordova
$ ./node_modules/.bin/cordova

```
Note: If your code doesn't work, and your terminal is not a Bash terminal,
then follow this steps to add a Bash terminal. Click this in Vs code

* Click file -> preference -> settings
* seach for the word Terminal in the search bar
* Under Terminal > integrated > Automation shell : Linux, click the link Edit in settings.json
Enter this code below in your json file and save it

```
"terminal.integrated.shell.windows": "C:\\Program Files\\Git\\bin\\bash.exe"
```
Then refresh your Vscode or re-open it and repeat the below command

```
$ ./node_modules/.bin/cordova
```
## Creating a project in Cordova
> Enter this code below to create a project called e.g demoApp
Note: Below demoApp is the project name. You can change it to your project name
app is the domain name and acme is the subdomain name. You can replace them with 
your domain and subdomain names.

```
$ ./node_modules/.bin/cordova create demoApp app.acme.game.demoApp
```
## Installing Cordova to our created project
To install cordova on our created project, you have to be in the directory of
the created project.
On your terminal, type this code to change directory to e.g demoApp

```
$ cd ./demoApp
```
Then type this command to install cordova on the project
and also connect your android phone to your computer with a usb cable,
then type these commands.

```npm
$ npm install cordova
$ ./node_modules/.bin/cordova platform
$ ./node_modules/.bin/cordova platform add android
$ ./node_modules/.bin/cordova run android --device
```
Note: If you get error messages from typing the above codes, then
follow these steps to add these requirements

## PREREQUIST
* Java en LTS(long term support) ... to be downloaded
* JDK ... to be downloaded
* Android Studio ... to be downloaded
* Gradle
* SDK (which is a display component)

Download and install these softwares from
* [Java LTS](https://java.com/en/download/)
* [JDK](https://www.oracle.com/technetwork/java/javase/downloads/index.html)
* [Android Studio](https://developer.android.com/studio/)

### Setting up Android Studio
* Open Android studio and click on Tools > SDK Manager > SDK Tools, Make sure
that Android SDK Platform-Tools is selected or update it if it shows update.

Note:  Follow this instruction below to accept android stdio licence

* C > Users > Administrator > Appdata > local > Android > Sdk > tools > bin
While you're in the bin folder, right-click on an empty space and select a terminal.
Note: If you don't see the Appdata folder in Administrator folder, then click at the 
top of the file explorer window or click on View and select Hidden items to display hidden
items.

Enter this command in terminal:

```
sdkmanager --licenses
```
Note, you can open a terminal in the bin folder by also doing this below,
> click on the below link to highlight it.  
C > Users > Administrator > Appdata > local > Android > Sdk > tools > bin
Then over-write it by typing cmd over it and press enter. it will open a terminal
Enter the command:
```
sdkmanager --licenses
```
Important: select Yes for all licences information

* After accepting the license agreement, re-run this code in Vs Code

```
$ ./node_modules/.bin/cordova run android --device
```
### Solving Gradle not found problem
Search the location of gradle on your system 

* C > users > admin > gradle > wrapper > dists > gradle > gradlefolder > bin > gradle
Note: The gradlefolder on the link above could be any folder with numbers attached to it.
While the last gradle in the link should be a blank white file.

* Copy the address of the gradle file
* search for environment variable with windows search bar.
* On system variable tab, click new and paste your gradle address in the second box
* Re-open your project terminal and type

```
$ ./node_modules/.bin/cordova run android --device
```
Once you get LAUNCH SUCCESS or NO DEVICE FOUND message then it's well configured.

###  Migrating your native built app to cordova

After the successful installation above, we migrate our project as follows

* Rename the index.html file of your cordova project to cordova.html or you delete it
* Copy the dist and index.html of your native application and paste it in the www folder
of your cordova project.
* If you have files in the assets folder of your native app, then copy them to assets of cordova
* In webpack.config.js file, make this change
baseDir: ["./www"]
path_dirname + "/www/dist"
* In config.xml file, change the widget Id to match your project name. Then delete unneccessary
informations like description, ios platform, tel, mail except if you need them
* In package.json file, change main to index.js. Then add the following to the file

" device ": " cordova run android --device"
Then type in terminal

```
npm run device
```

Note: If it shows cordova error, then install cordova with the command

```
./node_modules/.bin/cordova platform add android
```

#### Necessary Native to Cordova folders that you need to have in your project
* hooks
* node_modules
* platforms
* plugins
* src
* www
* .babelrc ... this is copied from your native built app into cordova project
* config.xml
* package.json ... this is copied from your native built app into cordova project
* webpack.config ... this is copied from your native built app into cordova project

Note: After migrating your files, type

```npm
$ npm install
$ npm start
```
### SETTING UP YOUR ANANDROID PHONE
Note that the locations for this setup varies according to phones.
Just try get the location of the build number of your phone. You
can search your phone model on google to get location of its build number

* settings > about phone > build number
* Tap 7 times on build number to enter developer mode
* Also click on developer options
* activate usb debugging
* Then connect your phone with usb cable to your laptop
* Click the green play button at the top of Android studio to get connected 

ENJOY THE DETAILED SETUP



