## Anonymity on Computer



<br>



#### Covering Entries
###### 1. Cover your camera
###### 2. Cover the microphone/s
###### 3. Remove the GPS card



<br>



### Router Security
###### 1. Disable WPS function
###### 2. Disable Broadcast SSID
###### 3. Set a Secure WPA2 Password
###### 4. Maximum Firewall Security
###### 5. Paid VPN
###### 6. Disable Log's



<br>



### Install some Linux Distro!

###### Linux systems are rarely infected by malware such as viruses, worms etc, thereby making it as a very secure OS. As a normal user, we will never come across a situation where Antivirus software is been sold for Linux. This means, Linux is inherently secure and there are many reasons associated with it.



<br>



### Encrypt your Drive
###### Cryptography deals with the construction and analysis of protocols that prevent third parties from reading private messages. Various aspects of information security , such as confidentiality , integrity and authentication of data are central to cryptography. Applications of cryptography include e-commerce , chip-based payment cards , digital currencies , computer passwords and passworded folders.

###### When installing a linux system, you will always find an option to encrypt the disk on which the operating system will be installed. For maximum security, you should enable this option, thus creating a strong password, with uppercase and lowercase letters, numbers and symbols.



<br>



### Change MAC Address
###### A MAC Address is a number used to uniquely identify your device on the local network segment. The address is (and needs to be) visible to everyone on the network segment, but because of the way network routing works, it is usually not visible to anyone.

`ifconfig`

`ifconfig <network card> down`

`macchanger <network card> --mac=00:11:22:33:44:55` # UNIX MAC Address

`ifconfig <network card> up`



<br>



### Install UFW Firewall

###### UFW, or Uncomplicated Firewall, is an interface to iptables designed to simplify the process of setting up a firewall. UFW is a solid and flexible tool for any kind of user, whether a beginner or a professional.

#### Gather the Binaries
`apt-get install ufw -y`

#### Activate IPv6
`sudo vi /etc/default/ufw`

`# In "IPV6=no" you change for "IPV6=yes"`

#### Configuring Policies
`sudo ufw default deny incoming`

`sudo ufw default allow outgoing`

#### Enable SSH connections
`sudo ufw allow ssh`

`sudo ufw allow 22`

`sudo ufw allow 2222`

#### Enable UFW Firewall
`sudo ufw enable`

`sudo ufw status verbose`



<br>



### Install NoIP Service

###### No-IP provides dynamic DNS services . A basic one is provided free of charge, as long as the user updates his access from time to time, keeping it active. Upgrades to DDNS come with purchases. Dynamic IP addresses are common in residential cable or DSL broadband accounts, and typical DDNS users would be users of these types of Internet connections. The service allows users to create up to three host names in a No-IP domain. Software clients are provided for Windows, OS X and Linux, which allows DDNS to connect to these operating systems. More often, however, routers are used in such DDNS setups.

#### Create Account
###### 1. Go to the NoIP website and create an account
###### 2. Check your email for the verification and click the link.
###### 3. Log out / Log in again and create a userid
###### 4. Create a DynDNS entry

#### Gather the Binaries

`sudo apt-get update`

`sudo apt-get install make gcc g++ zlib1g-dev`

`sudo bash`

`cd /usr/local/src/`

`wget http://www.no-ip.com/client/linux/noip-duc-linux.tar.gz`

`tar xf noip-duc-linux.tar.gz`

`cd noip-2.1.9-1/`

`make install`

`Select your Network Card`

`Set your Login Info`

`noip2`

`exit`

#### Configure NoIP Service

`sudo noip2 -S`

`sudo noip2 -K {process_num}`

`cd ~/src`

`repo=https://gist.github.com/NathanGiesbrecht/da6560f21e55178bcea7fdd9ca2e39b5`

`git clone $repo noip.svc`

`cd ~/src/noip.svc`

`sudo cp noip2.service /etc/systemd/system`

#### Enable NoIP Service

`sudo systemctl enable noip2`

`sudo systemctl start noip2`



<br>



### Install I2P Service

###### I2P is an overlay network and darknet that allows software applications to send and receive messages to others on the network and securely under pseudonyms. Uses include websites, blogs, online sales sites, and file transfer. Since I2P is an anonymous network, it is designed to be used by other software as a communication channel. And so there are a variety of applications available or under development that use I2P internally.

#### Gather the Binaries
`sudo apt-add-repository ppa:i2p-maintainers/i2p`

`sudo apt-get update`

`sudo apt-get install i2p`

`systemctl status i2p.service`

#### Handle hosts file
`sudo systemctl stop lighttpd.service`

`sudo systemctl stop i2p.service`

`sudo chown i2psvc:www-data ~i2psvc/i2p-config/eepsite/docroot/hosts.txt`

`sudo ln -s ~i2psvc/i2p-config/eepsite/docroot/hosts.txt ~www-data/html/hosts.txt`

#### Start Service
`sudo systemctl start lighttpd.service`

`sudo systemctl start i2p.service`



<br>



### Install TOR Network

###### Tor Network is a service that provides a browser, bridges, and proxies for users to access the Internet with as much privacy as possible. Tor routes traffic through multiple servers and encrypts it every step of the way. The Tor Network is a decentralized service, meaning that the Tor Network can be operated by entities with diverse interests and assumptions of trust... and is thus an open source service.

#### Install Tor Service
`sudo apt-get install tor`

#### Install Tor Browser
`sudo apt-get install torbrowser-launcher`

#### Start Tor Service
`sudo service tor start`



<br>



### Configure Tor Browser

#### Settings

###### 1. Go to "about:preferences#search" and select 'DuckDuckGoOnion' in the 'Default Search Engine'

###### 2. Go to "about:preferences#privacy" and select the 'Always' option in 'Onion services'

###### 3. Still in "about:preferences#privacy" go to 'Permissions' and in each of the options go to 'Settings...' and select 'Block new requests asking to...'

###### 4. Also in "about:preferences#privacy" scroll down to 'Security' and select the 'Safer' option, because the 'Safest' option has some incompatibilities with some sites, because the option disables JavaScript on all sites, and also disables some Fonts, icons, math symbols and images that are required.

###### 5. To end up in "about:preferences#privacy" go to 'Deceptive Content and Dangerous Software Protection' and enable the options 'Block Dangerous and Deceptive Content' , 'Block Dangerous downloads' and 'Warn you about Unindeseed and Uncommonmon Software'

#### Install Extensions
###### Privacy Badger - https://addons.mozilla.org/en-US/firefox/addon/privacy-badger17/
###### uBlock Origin - https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/
###### NoScript Security Suite - https://addons.mozilla.org/en-US/firefox/addon/noscript/
###### HTTPS Everywhere - https://addons.mozilla.org/en-US/firefox/addon/https-everywhere/
###### User-Agent Switcher and Manager - https://addons.mozilla.org/en-US/firefox/addon/user-agent-string-switcher/
###### ClearURLs - https://addons.mozilla.org/en-US/firefox/addon/clearurls/
###### Don't track me Google - https://addons.mozilla.org/en-US/firefox/addon/dont-track-me-google1/
###### Disable WebRTC - https://addons.mozilla.org/en-US/firefox/addon/happy-bonobo-disable-webrtc/
###### LastPass Password Manager - https://addons.mozilla.org/en-US/firefox/addon/lastpass-password-manager/



<br>



### Install Anonsurf VPN

###### This script is designed to provide users with system-wide anonymization. In simpler words, anything you do while Anonsurf is started on your system would be almost untraceable. Anonsurf not only routes all your traffic through Tor, but also allows you to start i2p services and clean up any traces left on the user's disk. Anonsurf also deletes all dangerous applications by virtue of the Pandora bomb.

#### Gather the Binaries
`git clone https://github.com/Und3rf10w/kali-anonsurf.git`

#### Install the Binaries
`chmod +x *`

`sudo bash ./installer.sh`

#### Start Anonsurf
`anonsurf start` # Only turn Anonsurf on after you open Tor Browser... unfortunately with Anonsurf turned on afterwards you will not be able to connect to Tor Browser.

#### View all Commands
`anonsurf`



<br>



### Passwords

###### 1. Always create different passwords for different sites

###### 2. Always create passwords with +8 characters, these are uppercase, lowercase, numeric and symbols

###### 3. Use a good Password Manager like "LastPass Password Manager" or "Bitwarden - Free Password Manager"



<br>



### Create a Encrypted Folder
#### Gather the Binaries
`sudo add-apt-repository ppa:gencfsm `

#### Install Binaries
`sudo apt update`

`sudo apt install gnome-encfs-manager`

#### Create a Folder
`gnome-encfs-manager create_stash <Directory to Encrypt> <Mount directory>`

##### Example:
`gnome-encfs-manager create_stash /home/username/.Encrypt /home/username/Encrypt`

#### Unmount Folder
`gnome-encfs-manager unmount <Mount directory>` # A folder becomes Invisible

#### Mount Folder
`gnome-encfs-manager mount <Mount directory>` # A folder becomes Visible



<br>



### Create a Encrypted Notes
#### Gather the Binaries
`sudo add-apt-repository ppa:nilarimogard/webupd8`


#### Install Binaries
`sudo apt-get update`

`sudo apt install encryptpad encryptcli`

#### Start EncryptPad
`encryptpad`



<br>



### Create a new Online Identity
###### Deleting your information and creating false ones will anonymize your personal data (name, age, gender) and you will be able to create a new "Person" online, so that you can hide who you really are

#### Delete your Information of Google
###### 1. https://myaccount.google.com/deleteservices

###### 2. https://myactivity.google.com/item

###### 3. https://myaccount.google.com/permissions?continue=https%3A%2F%2Fmyaccount.google.com%2Fsecurity

###### 4. https://myaccount.google.com/deleteaccount

#### Delete your Information of Facebook
###### 1. https://m.facebook.com/off_facebook_activity/

###### 2. https://www.facebook.com/help/delete_account/


#### Create a Fake ID

###### Fake ID - https://datafakegenerator.com/generador.php

###### Buy a FAKE National Identity Card, for Online Shopping ONLY - http://lqcjo7esbfog5t4r4gyy7jurpzf6cavpfmc4vkal4k2g4ie66ao5mryd.onion/

###### Onion ProtonMail - https://protonmailrmez3lotccipshtkleegetolb73fuirgj7r4o4vfu7ozyd.onion/

###### Google Account - https://accounts.google.com/signup/v2/webcreateaccount?continue=https%3A%2F%2Faccounts.google.com%2F%3Fhl%3Den-EN&hl=en_EN&dsh=S671161644%3A1648763270630717&biz=false&flowName=GlifWebSignIn&flowEntry=SignUp

###### Onion Facebook - https://www.facebookwkhpilnemxj7asaniu7vnjjbiltxjqhye3mhbshg7kx5tfyd.onion/



<br>



### Create a CryptoWallet

##### Cryptocurrencies

###### A cryptocurrency is a medium of exchange, which can be centralized or decentralized that uses blockchain technology and cryptography to ensure the validity of transactions and the creation of new units of the currency.


##### BlockChain
###### Blockchain is a distributed ledger technology that aims at decentralization as a security measure. It is a distributed and shared database that has the function of creating a global index for all transactions that occur in a given market. It works like a ledger, but in a public, shared, and universal way, which creates consensus and trust in direct communication between two parties, that is, without the intermediation of third parties such as the government.


##### Bitcoin

###### Bitcoin allows financial transactions without intermediaries, but verified by all users of the network, which are recorded in a blockchain. Bitcoin is a decentralized network, that is, a structure without a central managing entity, which makes it impossible for any financial or governmental authority to manipulate the issuance and value of the cryptocurrency or to induce inflation by producing more money.


##### Ethereum

###### Ethereum is a decentralized platform capable of running smart contracts and decentralized applications using blockchain technology. These are applications that run exactly as programmed without any possibility of censorship, fraud, or interference from third parties, because the contract is immutable.



#### Install Dependencies
`https://download.electrum.org/4.2.1/Electrum-4.2.1.tar.gz`

#### Install python-pip
`sudo apt-get install python3 && sudo apt-get install python2`

`sudo apt-get install python3-setuptools python3-pip`

`python3 -m pip install --user Electrum-4.2.1.tar.gz`

#### Download Package
`tar -xvf Electrum-4.2.1.tar.gz`

`cd Electrum-4.2.1/`

`python3 -m pip install setup.py`

`chmod +x ./run_electrum`

#### Start CryptoWallet
`./run_electrum`

#### Creating a Account
###### 1. Select where you want to have your Wallet
###### 2. Set a Password
###### 3. Select the 'Wallet with two-factor authentication' option
###### 4. Select the 'Create a new seed' option
###### 5. Select the 'Segwit' option
###### 6. Guarde a sua semente num sitio SEGURO.
###### 7. Paste the Seed
###### 8. Set a Password
###### 9. Confirm Password
###### 10. Select the 'Encrypt wallet file' option
###### 11. Enter your Email Address
###### 12. Install Google Authenticator on your Smartphone
###### 13. Follow the instructions
###### 14. Click on '+' button
###### 15. Click in 'Scan barcode'
###### 16. Scan the QR Code of the Wallet 
###### 17. Paste the 6-num. Code in Wallet

#### Buy Bitcoin
###### 1. Go to "https://bitcoin.org/en/buy"
###### 1. Set the Amount
###### 3. Enter your Wallet Address 
###### 4. Enter your Email Address 
###### 5. Enter the Verification Code in your Email-Box
###### 6. Select Select the Check Boxes you want
###### 7. Set your FAKE Informations
###### 8. Upload your FAKE National Identify Card
###### 9. Select the Payment Method
###### 10. Follow the rest of the instructions.