# Create a Remote BitTorrent Sync Server

__This one-line installer makes it easy to set up BitTorrent Sync on a remote CentOS server.__


### Requirements

This script has been tested on a __CentOS 6.5 x64__ droplet on [DigitalOcean](https://www.digitalocean.com/?refcode=ae33c2146dbb). The assumption is that you have just set up a __brand new__ CentOS 6.5 x64 instance that will be dedicated to running BitTorrent Sync. _Running this script on a server that you are already using for other purposes could lead to various problems._


### Install

Once you have your new server's IP address and root password, `ssh` to your server. Then copy and paste the `curl` command below.

```
curl -L https://raw.githubusercontent.com/iseem/btsyncbox/master/Makefile > Makefile && make
```

The script will take a few minutes to run. If all goes well, your `ssh` connection will be terminated and you will see something like this:

```
The system is going down for reboot NOW!
Connection to XXX.XXX.XXX.XXX closed by remote host.
```

If you get an error that says `-bash: make: command not found`, then run `yum -y install make`. Once `make` is installed, re-run the `curl` command above.





### What's next?

__Open you favorite web browser__ and head over to port 8888 on your server. If your server's IP address was `222.222.222.222` then you'd enter `222.222.222.222:8888` in your browser's address bar. _You should see a BitTorrent Sync page._

#### Create a Password!
The first thing to do is create a __username__ and __password__ for the BTSync web UI by going to _Preferences > Authorization_. After you create your password you'll be asked to log in. __If your credentials appear not to work__, quit and restart your browser (this happens to me every time). After that you should be good to go. _Happy syncing!_

