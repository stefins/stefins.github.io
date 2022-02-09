---
layout: post
title:  "Running a tor middle relay"
date:   2022-02-04
---

In this tutorial I will show you how to run a tor middle relay inside
a VPS.

1. Get a VPS from any service providers.

2. Launch a Linux machine.

3. Get `tor` from the default package manager
```bash
# Ubuntu
$ apt-get install tor
# Arch
$ pacman -S tor
```
Or you can compile tor from [source](https://gitlab.torproject.org/tpo/core/tor).

4. Edit the `/etc/tor/torrc` file using `$EDITOR`.

5. Add the following lines to that file.
```
Nickname    myNiceRelay  # Change "myNiceRelay" to something you like
ContactInfo mail@example.com # Write your e-mail and be aware it will be published
ORPort      443          # You might use a different port, should you want to
ExitRelay   0               
SocksPort   0
RelayBandwidthRate 100 KBytes  # Throttle traffic to 100KB/s (800Kbps)
RelayBandwidthBurst 200 KBytes # But allow bursts up to 200KB (1600Kb)
```

6. Restart the tor service by running <br/>`systemctl restart tor@default`

Now you are all set as a relay operator! :)

You can monitor the live traffic using `nyx` command line tool.

```bash 
# On Ubuntu
$ apt-get install nyx
# On Arch
$ pacman -S nyx
```

![nyx ui](/assets/nyx-tor.png)

More info 

[lifecycle-of-a-new-relay](https://blog.torproject.org/lifecycle-of-a-new-relay/)