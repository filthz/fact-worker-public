<h1>Voodoo Pool Miner for the fact0rn blockchain</h1>

<hr/>

Pool url: https://fact0rn.wtf <br/>
Project url: https://www.fact0rn.io/ 

Discord: https://discord.com/invite/JU7Gzc587w<br/>
Telegram: https://t.me/+T_c_2LLqHBthOTEy

A great explanatory video made by <b>madelectronengineeringrick</b>
can be found here https://www.youtube.com/watch?v=pXboUJ72a_M

Miner requires a username / password pair. Join discord: https://discord.com/invite/JU7Gzc587w and send <b>Förster</b> (Bot) a DM. It will guide you through the registration. You need a fact0rn wallet address prior to the registration.

<h2>How many workers should I connect?</h2>
Keep in mind that each worker requires around 5 Mbit upload bandwidth. 

<h2>Min specs?</h2> 
16 GB RAM (32 GB on a EPYC)<br/>
AMD: recommended 5000x and up (including all epycs)<br/>
Intel: Xeon scalable 1 or newer and Core-I starting with 11000er Series <br/>
Each worker will consume ~5Mbit upload

<h2>Installation:</h2>
<code>sudo su</code><br/>

create a folder where you want to keep the miner.
go into that folder and execute (replace USERNAME / PASSWORD with your credentials):
Make sure to copy / paste the whole line

<code>wget -O setup_worker.sh https://github.com/filthz/fact-worker-public/releases/download/base_files/setup_worker.sh && sh setup_worker.sh USERNAME PASSWORD</code>

this will install docker and the miner. the miner will start automatically.
miner logs will be stored in logs/worker.log 

When installing on multiple machines: <b>do not</b> copy files from one machine to other. Instead execute the installation script on each, otherwise there will be issues.

<h2>Mining in windows:</h2>
Install WSL as described here https://learn.microsoft.com/de-de/windows/wsl/install <br/>
Then follow the setup steps above

<h2>Update from a previous version</h2>
go into the worker folder and execute:

<code>wget -O update_worker.sh https://github.com/filthz/fact-worker-public/releases/download/base_files/update_worker.sh && bash update_worker.sh</code>

your worker will be updated to the most recent version and restarted.

<h2>Troubleshooting:</h2>
If HiveOS complains (and reboots) because of high LA, disable the watchdog:<br/>
<code>systemctl stop hive-watchdog && systemctl disable hive-watchdog</code><br/><br/>

If you get the "cannot connect to the docker daemon" error (especially common on HiveOS). Try running this commands and retry installation:<br/>

<code>sudo apt-get install -y iptables arptables ebtables
sudo update-alternatives --set iptables /usr/sbin/iptables-legacy
sudo update-alternatives --set ip6tables /usr/sbin/ip6tables-legacy
systemctl enable --now docker
systemctl restart docker
</code>

<h2>Stopping and removing the container</h2>
<code>sudo docker stop $(sudo docker ps -aq -f name=fact-worker); sudo docker rm $(sudo docker ps -aq -f name=fact-worker)</code>
