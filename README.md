# Create a Remote BitTorrent Sync Server

This one-line installer makes it easy to set up BitTorrent Sync on a remote CentOS server.


### Server Requirements

This script was written for CentOS and has been tested on a __CentOS 6.5 x64__ droplet on [DigitalOcean](https://www.digitalocean.com/?refcode=ae33c2146dbb). The assumption is that you have just set up a __brand new__ CentOS 6.5 x64 instance that will be dedicated to running BitTorrent Sync. Running this script on a server that you are already using for other purposes could lead to various problems.


### Install

Once you have your server's IP address and root password, `ssh` to your server. Then copy and paste the `curl` command below. The `make` file expects to run as root on a brand spanking new server.

```
curl -L https://raw.githubusercontent.com/iseem/btsyncbox/master/Makefile > Makefile && make
```

The script will take a few minutes to run. It will __update__ your server via __yum__, set up the __iptables__ firewall with ports open for __ssh__ and __BitTorrent Sync__ only,  and will install __fail2ban__ to help with security. Then it will install and configure __btsync__. If all goes well, your __ssh__ connection will be terminated and you will see something like this:

```
The system is going down for reboot NOW!
Connection to XXX.XXX.XXX.XXX closed by remote host.
```

_NOTE: If you get an error that says `-bash: make: command not found`, you'll need to [install make first](https://github.com/iseem/btsyncbox#make-is-not-installed), and then re-run the `curl` command above._

#### What Next?

If you've come this far then your BTSync server should be ready to go! __Open you favorite web browser__ and head over to port 8888 on your server, e.g. if your server's IP address is `222.222.222.222` then you'd enter `222.222.222.222:8888` in your browser's address bar. __You should see a BitTorrent Sync page...__

#### Create a Password!
The first thing to do is create a __username__ and __password__ for the web UI by going to _Preferences > Authorization_. After you create your password you'll be asked to log in. __If your credentials appear not to work__, quit and restart your browser (this happens to me every time). After that you should be good to go.



### Troubleshooting 
##### Make is not installed
If you get an error that says `-bash: make: command not found`, you'll need to install `make`:

```
yum -y install make
```
Once `make` is installed, return to the [Install section above](https://github.com/iseem/btsyncbox#install).



