miner for the fact0rn blockchain.

see https://www.fact0rn.io/ for blockchain details.

Miner requires a username / password pair. Join discord: https://discord.gg/EmGrDnbH and ask for credentials. Team staff will contact you.
 

<h2>Installation:</h2>
sudo su

create a folder where you want to keep the miner.
go into that folder and execute (replace USERNAME / PASSWORD with your credentials):
Make sure to copy / paste the whole line

wget -O setup_worker.sh https://github.com/filthz/fact-worker-public/releases/download/base_files/setup_worker.sh && sh set
up_worker.sh USERNAME PASSWORD

this will install docker and the miner. the miner will start automatically.
miner logs will be stored in logs/worker.log 

<h2>Update from a previous version</h2>
go into the worker folder and execute:

wget -O update_worker.sh https://github.com/filthz/fact-worker-public/releases/download/base_files/update_worker.sh && sh update_worker.sh 

your worker will be updated to the most recent version and restarted.

<h2>Troubleshooting:</h2>
If you get the "cannot connect to the docker daemon" error. Try running this command and retry installation:

systemctl start docker
