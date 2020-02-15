# Ubuntu: React Native Environment
Step by step to install and configure react native, android emulator and genymotion on Ubuntu.
#### This guide use Ubuntu 18.04.

## Dependencies
    NodeJS, JDK, Android SDK and Genymotion

#### Install cURL
    $ sudo apt-get install curl

#### Install NodeJS
    $ curl -sL https://deb.nodesource.com/setup_10.x | sudo bash -
    $ sudo apt install nodejs

#### Install React Native CLI
    $ sudo npm install -g react-native-cli 

#### Install JDK 8
    $ sudo add-apt-repository ppa:openjdk-r/ppa
    $ sudo apt-get update
    $ sudo apt-get install openjdk-8-jdk
 
Check the main version of JDK.
    $ sudo update-alternatives --config java

#### Libs 32bits
    $ sudo apt-get install gcc-multilib lib32z1 lib32stdc++6

## Path Environment
#### Create on home directory a new folder to setup Android SDK: Android/Sdk

Download SDK: [Android SDK]: https://developer.android.com/studio/#downloads, choose the "Command line tools only".
Extract the content to Android/Sdk folder.

#### Add this lines on the ~/.bash_profile, ~/.profile, ~/.zshrc or ~/.bashrc
    export ANDROID_HOME=~/Android/Sdk
    export PATH=$PATH:$ANDROID_HOME/tools
    export PATH=$PATH:$ANDROID_HOME/platform-tools
    
Open terminal and execute this command:
    
    source <file-you-setup-path-enviroment> 
    source ~/.bashrc

#### Configure android SDK
    $ ~/Android/Sdk/tools/bin/sdkmanager "platform-tools" "platforms;android-27" "build-tools;27.0.3"

# Genymotion
#### Install Virtualbox
    $ sudo apt-get install virtualbox

#### Install Genymotion
Download [Genymotion]: https://www.genymotion.com/fun-zone/ and click on button “Download Genymotion Personal Edition”. Execute this command in folder you download the file.

    $ chmod +x genymotion-2.2.2_x64.bin
    $ ./genymotion-2.2.2_x64.bin
    cd /home/$USER/genymotion/
    $ ./genymotion
Now Follow this step: Genymotion>Settings>Account sign in your account, after that choose ADB>Use Custom Android SDK, browse to the folder where you extracted the SDK and click Choose. Install an Android Emulador version you like.

#### ADB Connect
    $ adb connect EMULADOR_IP:5555
    $ adb devices
