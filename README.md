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