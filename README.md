# RaspberryPIFlows
### Send a picture to raspi pi to pc

# install nodejs and npm
```
 sudo apt-get install -y nodejs
```
## Check node verison
``` 
node -v
sudo npm install npm --global
npm install node-red
```
go to browser<br/>
localhost:1880<br/>
```
 npm install node-red-contrib-camerapi
```
# Set up Camera
sudo raspi-config



## Mac Setup
### Homebrew
```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
### install node
```
brew install node
```
###  Update homebrew
```
brew update
```
### Upgrade node
```
brew upgrade node
```
### Check installed
```
npm -v
node -v
```
### Install node red
```
sudo npm install -g node-red
```
### Start node red
```
node-red
```
Then view the the node red front end in your browser <br/>
localhost:1880

# Using Digital Ocean

Create an account with Digital ocean<br>
Create a new Droplet <br>
Add Nodejs to your droplet <br>
Select Your local country servers and allow private networking<br>
Once the droplet is created, login the access panel using the password sent to your email<br>
Create a new password, you can then use this to SSH from your terminal into your droplet<br>
```
ssh root@<ip address>
```
download node-red <br>
```
npm install -g node-red 
```
download PM2 or forever, which is a packet manager
```
npm install PM2 -g 
```
or
```
npm install forever -g 
``` 
This will allow node-red to run in the background so it is always running. <br>
First we need to sort out authentication and port number so we can view the front end! <br>
Enter your node red folder
``` 
cd ~/.node-red
```
Next create a secure env file
```
nano .env
```
Once open write 
```
PORT=80
```
Then press ctrl + x , save the changes with Y then Enter and your enviroment will now run on PORT 80.

* Note if this doesn't work

``` 
nano settings.js
```
Change 
```
uiPort : process.env.PORT || 1880
```
To this 

```
uiPort : process.env.PORT || 80
```
Then press ctrl + x , save the changes with Y then Enter and your enviroment will now run on PORT 80.

## Authentication 


go into the settings.js file using

```
nano settings.js
```
Now this bit is difficult, you need to search for this code which will be commented out
```javascript
adminAuth: {
    type: "credentials",
    users: [{
        username: "admin",
        password: "$2a$08$zZWtXTja0fB1pzD4sHCMyOCMYz2Z6dNbM6tl8sJogENOMcxWV9DN.",
        permissions: "*"
    }]
}
```
![Image](https://github.com/SamuelDBines/RaspberryPIFlows/blob/master/images/auth-comment.png "Image 1")
Once uncommented you then need to save, this authentics admin with an unknown password. Thats not useful to use though.
So we download the node-red-admin package from NPM
```
npm install node-red-admin -g

```

Then run the command

```
node-red-admin hash-pw
``` 
![Image](https://github.com/SamuelDBines/RaspberryPIFlows/blob/master/images/hash-pass.png "Image 1")
Copy the hash password and replace it on the code your have uncommented in the settings.js file
```javascript
adminAuth: {
    type: "credentials",
    users: [{
        username: "admin",
        password: "replace - with - your - hash",
        permissions: "*"
    }]
}
```
Save this and run node-red you should now be able to log in on node-red flow at your ipaddress given by digital ocean.<br>
Now lets make sure that the node red enviroment never stops using PM2<br>

Start forever
```
pm2 start /usr/bin/node-red
```
Stop process
```
pm2 start /usr/bin/node-red
```
There is more [Here](https://gist.github.com/anmolnagpal/e1396bf7f0fc46bb5bde4146cd80c1f4)



Your done, node-red is setup and authenticated on http port
