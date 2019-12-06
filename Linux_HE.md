# HowTo open a Tunnel in Linux with Hurricane Electric

## Step 1: login and tunnel setup
Go to the site https://tunnelbroker.net/ - automatic! 
Register yourself and login
Go on _Create Regular Tunnel_ in _User Funcionts_ (one account can open up to 5 tunnels)
Fill the fields...
You need to know your public ip (just ask "what is my ip" to your search engine). You have also to select the HE endpoint. Usually is a good idea to choose a near one couse you want small latency, you can __ping__ the endpoint from your machine to find it.

This is the easy part...

## Step 2: LinuxBox

Step one gave you some script like this one: 

`ip tunnel add he-ipv6 mode sit remote xxx.xxx.xxx.xxx local yyy.yyy.yyy.yyy ttl 255`

`ip link set he-ipv6 up`

`ip addr add 2001:470:gggg:ggg::2/64 dev he-ipv6`

`ip route add ::/0 dev he-ipv6`

Remote depend on what you select in step 1, local is the local ip of your machine (if you are behind NAT, is the private ip of your machine). You can find it with `ip address` command.

