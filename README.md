# RaspberryPIFlows
### Send a picture to raspi pi to pc

# install nodejs and npm

 sudo apt-get install -y nodejs
## Check node verison
 node -v<br/>
 sudo npm install npm --global<br/>
 npm install node-red<br/>
go to browser<br/>
localhost:1880/red<br/>

 npm install node-red-contrib-camerapi

# Set up Camera
sudo raspi-config



## Mac Setup
### Homebrew
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
### install node
brew install node

###  Update homebrew
brew update
##= Upgrade node

brew upgrade node

### Check installed

npm -v<br/>
node -v

### Install node red

sudo npm install -g node-red

### Start node red

node-red<br/>
Then view the the node red front end <br/>
localhost:1880/red

# Using Digital Ocean

Create an account with Digital ocean<br>
Create a new Droplet <br>
Add Nodejs to your droplet <br>
Select Your local country servers and allow private networking<br>
Once the droplet is created, login the access panel using the password sent to your email<br>
Create a new password, you can then use this to SSH from your terminal into your droplet<br>
ssh root@<ip address> <br>
download node-red <br>
npm install -g node-red <br>
 download PM2 or forever, which is a packet manager
npm install PM2 -g <br>
 or
 npm install forever -g <br>
 
