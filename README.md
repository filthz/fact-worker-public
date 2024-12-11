miner for the fact0rn blockchain.

see https://www.fact0rn.io/ for blockchain details.

Miner requires a username / password pair. Join discord: https://discord.gg/EmGrDnbH and ask for credentials. Team staff will contact you.
 

<h2>Installation:</h2>
sudo su

create a folder where you want to keep the miner.
go into that folder and execute (replace USERNAME / PASSWORD with your credentials):
Make sure to copy / paste the whole line (including 1.0 in the end)

wget https://github.com/filthz/fact-worker-public/releases/download/1.0/setup_worker.sh && sh setup_worker.sh USERNAME PASSWORD 1.0

this will install docker and the miner. the miner will start automatically.
miner logs will be stored in logs/worker.log 

<h2>Troubleshooting:</h2>
If you get the "cannot connect to the docker daemon" error. Try running this command and retry installation:

systemctl start docker
