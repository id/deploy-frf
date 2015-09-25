# Deploy FriendFeed backup
Launch a $5 instance on DigitalOcean, install required software and configure it to serve your static web sites in a few simple steps

## Disclaimer
Author take no responsibility for loss, inconvenience or injury resulting from following these instructions.
Do this on your own risk.

## How To

- create an account on [DigitalOcean](https://www.digitalocean.com/)
- create your [API Token](https://cloud.digitalocean.com/settings/applications)
- save it somewhere, it's needed for `DO_TOKEN` shell variable (in commands below)
- install [Vagrant](https://www.vagrantup.com/downloads.html)
- run `ssh-keygen` if you don't have your ssh key in ~/.ssh/id_rsa

Now open Terminal and run a few commands:

    vagrant plugin install vagrant-digitalocean
    export DO_TOKEN=xxx
    git clone https://github.com/id/deploy-frf.git
    cd deploy-frf

Copy zip files with your friendfeed archives in this folder and run:

    vagrant up

In the end you should see url which you can paste in your browser.
