# RaspberryPIFlows
### Send a picture to raspi pi to pc

# install nodejs and npm

 sudo apt-get install -y nodejs
## Check node verison
 node -v
 sudo npm install npm --global
 npm install node-red
go to browser
localhost:1880/red

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

npm -v
node -v

### Install node red

sudo npm install -g node-red

### Start node red

node-red
Then view the the node red front end localhost:1880/red