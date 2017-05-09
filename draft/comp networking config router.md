# comp networking
> Thu, 13 Apr 2017 at 9:30:10 MYT


```
enable
config t # start configuration
int g0/0 # configure interface "g0/0"

# add ip 10.1.10.1 with subnet 255.255.255.248 above interface (g0/0)
ip add 10.1.10.1 255.255.255.248

no shut # exit and enable config

# go to next config :)
```
