# Deploy FriendFeed backup

## How To

### Create account on digitalocean.com
And create API Token here: https://cloud.digitalocean.com/settings/applications
Put this in ~/.bashrc:

    export DO_API_TOKEN=<token>

### Install software

    sudo pip install --upgrade ansible
    git clone https://github.com/id/deploy-frf.git
    cd deploy-frf

Make sure you have ssh key, otherwise run `ssh-keygen` and follow the instructions.

### Deploying
Copy frf archive to this directory and name it frf.zip.
Set frf_backup_name variable to the name of the directory inside frf.zip.
Then run ansible and let it do the job.

    ansible-playbook -i hosts playbook.yml -e frf_backup_name=dyachkoff

