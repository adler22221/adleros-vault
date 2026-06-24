#_GTD_0_inbox

Created on: [[20230304]]
Who's involved: 
About what: 

My note: 

Author: Ramesh Lingappan
Source: 
https://itnext.io/how-i-turned-my-old-macbook-pro-into-a-home-server-to-run-network-wide-ad-blocker-475120852402
Retrieved 

> Hello there, here I am in the New year (I can still say that right?) with a new addiction, Self Hosting. I have been following the self-hosted community in Reddit for a while now, and I always wanted…

# How I turned my old MacBook Pro into a Home Server to run network-wide Ad Blocker
![](https://miro.medium.com/v2/resize:fit:980/1*yOrT0zXsX3-vwX9KHc2row.jpeg)

Image from Pixabay

Hello there, here I am in the New year (I can still say that right?) with a new addiction, Self Hosting. I have been following the self-hosted community in Reddit for a while now, and I always wanted to have my own server to play around with, run some programs, break some stuff and perhaps some automation to make life a little better.

At the start of this year, out of nowhere, I got a spark to try it out, after all, I am a developer and interested in these kinds of stuff.

Okay, I got the interest checked, what about the hardware? How about a [Raspberry Pi](https://www.raspberrypi.org/)?

![](https://miro.medium.com/v2/resize:fit:980/1*9g2ZIHNAObPUEE9AyQ9LmA.jpeg)

Yes, this credit card-shaped thing is actually a computer capable of running several applications and it is one of the highly recommended hardware for DIY projects/learning/small servers.

Am very tempted to buy one of these, the latest Raspberry Pi 4 model has, a Quad-core 1.5GHz CPU and 2/4/8 GB of SDRAM. That should be a lot for starters or home servers.

I was on the verge of buying one of these, but then I remembered I got a very old Macbook Pro (early 2011) laying around somewhere doing nothing but collecting dust, interesting!💡. So can we turn this into a Home Server? and thus the quest beings…

## What do I have?

Let's look at what this mac has,

## Hardware

My old mac has a

-   2.0GHz quad-core Intel Core i7 processor, which should be more than enough for my use case.
-   it has already been upgraded to 16GB DDR3 RAM
-   I have already replaced the default HDD with 250GB SSD as the boot volume

Also, this mac has an optical drive (yea remember it?) which has no use nowadays. So I have removed the optical drive and replaced it with a 1TB HDD (2.5 inches) with the help of an HDD Caddy (it's cheap).  
For more storage, I can always make use of the External Hard drives connected via the USB.

Overall this machine is packed with some hardware to handle some load.

## Software

For the OS the best practice would be to replace macOS with some Linux distribution which is perfect for a server (you don't need any GUI). But I kept the existing macOS because this is still an experiment, am not sure if I will be using this setup for a long time (if so then I will switch OS) plus I use another Mac for work, so the compatibility for connections and Screen sharing is built-in.

Currently its running macOS High Sierra (that's the last supported OS for this mac)

## Becoming a Server

A server should be running all the time without sleep or interruption because other devices will depend on it and clearly, Macbook pro is not designed to be Server (why will it be!). Mac will put the system to sleep when the lid is closed or after some time depending on the configuration, this is obviously good for using it has a laptop which helps to save energy. But for a server, we don't want any of that optimization, so we need to do some tweaking ⚙️.

## Do Not Sleep 😴

First, I have disabled system sleep in Energy Saver settings.  
It's in `System Preferences > Energy Saver` , under both _Battery_ & _Power Adapter_ Tab

-   Set `Computer Sleep` to never
-   Enabled `Wake for network access`
-   Enabled `Put hard disks to sleep when possible`

![](https://miro.medium.com/v2/resize:fit:938/1*h8x99JPAmNBI67jOymAfFg.png)

This is not enough, when the lid is closed, mac will still automatically go to sleep. I have tried several suggested solutions to prevent it, one that is free and worked well for me is [Amphetamine](https://apps.apple.com/us/app/amphetamine/id937984704). This app prevents mac from going to sleep and offer several customizations.

![](https://miro.medium.com/v2/resize:fit:431/1*ySodKq5C5tdtXfjzLFpJGA.png)

We can create a session with an indefinite time period, meaning the system will not go to sleep indefinitely, which is exactly what I want. Also, I have enabled this application to start at the system launch. So even after an unexpected restart, the system will continue running.

Plus I have turned off Bluetooth and other unnecessary services & notifications. With this and a power source plugged in, this mac should be running forever.

## Network

The mac did not become a server yet, I need to connect to this machine remotely from other devices (in the same network only), currently am not planning to expose this server to the outside world. So this server should be accessible only from within the same network.

For better connection speed, I have disabled WiFi and connected this mac to my network via LAN cable (yes it has LAN Port, no need for an adapter, how cool is that).

_How do I identify this machine in the network?_  
By its IP address, each machine will have an internal IP address assigned by the router (DHCP server) as soon as the machine is connected to the network.  
One problem is, by default the assigned IP address is not static, meaning it can change after something.

I want my server’s IP address to be static so that all devices can reliably talk to the server. I can do this in `System Preferences > Network > Advanced`under `TCP/IP` settings,

-   changed the `Configure IPv4`option to `Using DHCP with manual address`
-   under `IPv4 Address` , we can set the desired IP address for the server or keep using the already assigned one.

![](https://miro.medium.com/v2/resize:fit:938/1*-9UxVSLiFjptCSzmVzQQyg.png)

So my server will now have a static IP address which is`192.168.1.10` (it's internal only)

## Sharing

Also, I need to enable a few options to access this machine remotely, it's under `System Preferences > Sharing` ,

-   I have changed my computer name to `Home Server` (to easily recognise it)
-   Enabled `Screen Sharing` , `File Sharing` and `Remote Login`

![](https://miro.medium.com/v2/resize:fit:934/1*gHEFBgAArmYQnjbagXF80w.png)

With this, I can remotely access this mac via SSH, remotely access the UI via the Screen Sharing app (from another Mac) and access files via SMB connections.

Let's test it out, from my other mac, I can already see my server name under the network tab ✔️️,

![](https://miro.medium.com/v2/resize:fit:764/1*-Zf3sxuzP6HmaVNz1v5kFQ.png)

When I click HomeServer, I will be prompted with a login screen, where I can type the username and password for that machine (same as the one I used to log in to that normally)

Alternatively, you can log in via SSH,

```
ssh {username}@{server-ip-address}eg: ssh admin@192.168.1.10
```

Now my mac has become a Server that I can use and play with remotely 🎉🎉🎉

## Warning ⚠️

There is one issue that I did not address in this post, which is several people has raised concern regarding using a laptop as a server because of its battery. The reason being leaving the laptop connected to the charger 24x7 is bad for the battery. Few people reported that their battery is swollen after several days (it could be a serious hazard).

If you are trying this, beware of this concern. One suggestion is to remove the battery from the laptop and use it via a power adapter. But I like to keep the battery as a backup power so in case of power failure or if I accidentally switched off the power socket, the server will still run for a while.  
**So I have implemented an automation solution to fix this problem, I will create a separate post (it's a lengthy one) with the details.**

## Sandboxing

Still, reading? you are awesome! 🔥

Now that I have my own server, I can start installing services & programs in it, but before that, I wanted to make sure I dont mess with system files or do something that causes system corruption/failure, also I want something, where I can easily clean up if I dont want a program anymore.

What do we have for that? Say hello to [Docker](https://www.docker.com/products/docker-desktop)

> Docker is a set of platform as a service products that use OS-level virtualization to deliver software in packages called containers. Containers are isolated from one another and bundle their own software, libraries, and configuration files; they can communicate with each other through well-defined channels

With docker, we can safely deploy an application and easily destroy it without leaving a trace in our server.

The easiest way to install Docker on Mac is by using the [Docker Desktop](https://www.docker.com/products/docker-desktop) app. I have installed Docker Desktop on the mac server. Also in the settings, enabled start docker on system launch.

Under `Resources`, we can configure CPUs, Memory and Storage for the VM. Also in `File Sharing` section, we can specify what folders are exposed to the VM, this way we can control by default what files are accessible by the applications running inside the docker.

![](https://miro.medium.com/v2/resize:fit:980/1*NvQ3QPyITkdyBGwAk7isSw.png)

Once I apply the changes, docker will restart and start running. Via SSH from a remote machine, I can check if docker is running by executing any docker command, eg: `docker ps` (which lists all running containers).

Let's run a simple Nginx webserver to test if everything is working fine.

```
docker run --rm --name my-nginx -p 80:80 -d nginx 
```

This command will deploy a docker container named _my-nginx_ using the latest _nginx_ docker image and expose the service on the host machine in port `80` and also on a few other ports.

Now from the other machine, when I open the browser and type

```
http://{server-ip}:80
```

I can able to see the Nginx welcome page.

## Network-wide Adblocker

Now I have the server and sandbox environment ready, waiting for some work. What shall I install first?🤔. The self-hosted community has an awesome list of open-source software that we can self-host and am overwhelmed by the size of this list.

Take a look yourself,

The first thing I wanted to try is a network-wide ad blocker to block annoying ads and also protect my devices in the network from malicious/malware/phishing websites.

Following are the two most recommended open-source software for ad blocking,

-   [PiHole](https://pi-hole.net/)
-   [AdGuard Home](https://adguard.com/en/adguard-home/overview.html)

I have tried both of them, though I really like PiHole I decided to use AdGuard Home because I like the clean UI and ease of configuration.

I can easily install this application using docker-compose and the YAML definition looks like this,

Then deployed using the following command,

```
docker-compose up -d
```

the `-d` flag will start the containers in the background and leave them running. We can check the container status using `docker ps` command and here is the output,

```
CONTAINER ID   IMAGE                        COMMAND                  CREATED         STATUS         PORTS                                                                                                                                                                                                                           NAMES5e80d27a243d   adguard/adguardhome:latest   "/opt/adguardhome/Ad…"   8 seconds ago   Up 7 seconds   67-68/udp.....0.0.0.0:82->80/tcp   adguardhome
```

The Adguard Home service is running on port `80` , but for the first time, we need to access it via port `3000` to do some initial setup.

In a browser, I navigate to`http://{server-ip}:3000` , and can see the Adguard Home welcome screen,

![](https://miro.medium.com/v2/resize:fit:980/1*I-7HmB5ql78RUUAV1jYuLw.png)

Adguard welcome screen

In the next few setups, I need to configure what port the Adguard Home should run, set up username & password, etc. Once the setup is done I can visit the Adguard Home dashboard via `http://{server-ip}:80` .

First I have changed the DNS server for my network to use Cloudflare DNS servers `1.1.1.2` & `1.0.0.2` (these are other variants of the popular `[1.1.1.1](https://one.one.one.one/)` DNS) which will also block malware websites.

We can do that under `Settings -> DNS Settings` ,

![](https://miro.medium.com/v2/resize:fit:980/1*zVACaQadsXmKcUZeKTddrg.png)

Second, we can customize the Blocklist, by default Adguard Home will have a default list, but we can change or extend that under `Filters -> DNS Blocklists` ,

![](https://miro.medium.com/v2/resize:fit:980/1*k0pUO-Kf2WchjfRH_UKtDQ.png)

One can find several of these blacklists on this website, [https://firebog.net](https://firebog.net/). With that, Adguard Home is ready now.

Finally, I need to do one more setup, which is to instruct individual devices in my network to use my mac server as the DNS server. I can do that in two ways,

-   By updating the DNS server configuration in my router, so that all devices will automatically use the IP address mentioned in the router
-   By manually updating DNS configuration in all the devices.

I did the first one, which is the easier route to force all the devices in my network to use my Mac Server IP as the DNS server.

The exact process varies depending on the type of router one have, for my router, it was straight forward and my DNS configuration looks like this,

![](https://miro.medium.com/v2/resize:fit:980/1*357rQyhA3F-u_zOVP8OaSg.png)

`192.168.1.10` is my mac server IP address, notice in the _DNS server 2_ I have mentioned `1.1.1.2` ? This is because if my mac server dies for some reason, then the whole internet won't work for any of the devices in my network (yea that's a lot), so I have configured a secondary DNS to prevent this issue for now. (there are other solutions like running a secondary Adguard server). What this means is some traffic will skip the Adguard server but that is fine for now.

Alternatively, one can always update individual devices DNS configuration, like for Mac, we can do it `System Preferences -> Network -> Advanced -> DNS`

![](https://miro.medium.com/v2/resize:fit:980/1*7fsuI8Tqc0E7SSW2ycV0Lw.png)

That's it. Now Adguard Home will automatically block ads and malware sites in my network. I can see some cool statistics in the Adguard Home dashboard, this is mine,

![](https://miro.medium.com/v2/resize:fit:980/1*M0SWtJw9Q90eBKacADfU0A.png)

20% of my network traffic is now blocked, that's a lot! 🍾. Here are my top blocked domains,

![](https://miro.medium.com/v2/resize:fit:980/1*rMjM5JSlWKlCudRd6zP5bA.png)

## Conclusion

It was a fun experiment to run my own server, there is a lot of learning involved and definitely, a lot of responsibility and work, but I like how it turned out so far. This is just a start, and I will be exploring more possibilities of Self Hosting. To be continued….
