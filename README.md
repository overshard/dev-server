# dev-server

I use this playbook to get my personal development server up and running.

## oneliner

To get this running on a fresh Ubuntu server:

    apt update && apt install --yes ansible && ansible-pull --url https://github.com/overshard/dev-server/ && reboot

## variables

If your name is not isaac and you want to use this you may want to change the
variable `isaac` at the top of the `playbook.yml` file to your name.

## post-install

Once the playbook completes and the server restarts you can login with your
user. You will then need to add any ssh keys to your .ssh folder and login to
your Heroku account with `heroku login --interactive`.

    scp .ssh/id_rsa .ssh/id_rsa.pub isaac@{{ server_ip }}:~/.ssh/
    ssh -t isaac@{{ server_ip }} heroku login --interactive
