# Week 9 Project: Honeypot
Codepath Week 9 Assignment

## Configuration & Deployment

I use vultr.com to create a linux VM running Ubuntu 14.04. The server was a basic VM, 1 core virtual processor, 512 MB RAM, 20 GB solid state storage. The initial configuration changes I made were to change the root password to something more manageable for the assignment, install Git, and install OpenSSH so I could stop using a browser window console to configure the server.

Once I SSH'd in, I installed MHN from the specified repo, Hurricane Labs, which failed numerous times. I then tried the version from Threatstream, and was able to get MHN installed. 

After MHN was running, I created a second VM on vultr.com, using the same settings as the first. I used the Deploy tab in the MHN interface to generate an installation script for a Dionaea honeypot sensor, per the assignment instructions. When I tried to install Dionaea on the new honeypot VM, it failed twice with the message "add-apt-repository: command not found." A quick Google led me to the conclusion that I needed to install software-properties-common. Once I did, the installation finished easily. The sensor showed up three times in MHN, because of the failed installs. I cleared out the first two so that I was left with the one working copy of the sensor in MHN.

Attacks began to flow in immediately.

## Attack Data

I was using a Windows PC for this assignment, so I needed to download PSCP from PuTTY's website to remotely connect to my MHN server and download the session.json file as directed by the assignment. The data in the short time my honeypot was up, as reported by MHN is below. I have uploaded the session.json file to this repo as well.

### Attack Stats
#### Attacks in the last 24 hours:
807
#### TOP 5 Attacker IPs:
46.166.142.136 (90 attacks)
185.107.80.31 (37 attacks)
62.210.141.119 (17 attacks)
45.77.45.97 (11 attacks)
119.28.16.71 (10 attacks)
#### TOP 5 Attacked ports:
445 (601 times)
5060 (153 times)
139 (12 times)
3389 (6 times)
80 (5 times)
#### TOP 5 Honey Pots:
dionaea (807 attacks)

