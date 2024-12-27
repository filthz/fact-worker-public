miner for the fact0rn blockchain.

see https://www.fact0rn.io/ for blockchain details.

Miner requires a username / password pair. Join discord: [[[https://discord.gg/EmGrDnbH](https://discord.gg/JU7Gzc587w)] and send <b>Förster</b> (Bot) a DM. It will guide you through the registration. You need a fact0rn wallet address prior to the registration.


<h2>How many workers should I connect?</h2>
If you have more than 30 CPU and a 4000 series GPU it makes sense to run a full cluster instead of single workers. In this case send a DM to fact-dog-millionaire on the discord server (or any other developers that are online)

<h2>Min specs?</h2> 
AMD: recommended 5000x and up (including all epycs)<br/>
Intel: Xeon starting with 2,7 GHz and Core-I starting with 11000er Series 

<h2>Installation:</h2>
sudo su

create a folder where you want to keep the miner.
go into that folder and execute (replace USERNAME / PASSWORD with your credentials):
Make sure to copy / paste the whole line

wget -O setup_worker.sh https://github.com/filthz/fact-worker-public/releases/download/base_files/setup_worker.sh && sh setup_worker.sh USERNAME PASSWORD

this will install docker and the miner. the miner will start automatically.
miner logs will be stored in logs/worker.log 

When installing on multiple machines: <b>do not</b> copy files from one machine to other. Instead execute the installation script on each, otherwise there will be issues.

<h2>Update from a previous version</h2>
go into the worker folder and execute:

wget -O update_worker.sh https://github.com/filthz/fact-worker-public/releases/download/base_files/update_worker.sh && bash update_worker.sh 

your worker will be updated to the most recent version and restarted.

<h2>Troubleshooting:</h2>
If you get the "cannot connect to the docker daemon" error. Try running this command and retry installation:

systemctl start docker
