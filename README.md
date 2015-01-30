# Nscan
Nscan is a fast Network scanner optimized for internet-wide scanning purposes. It has it's own tiny TCP/IP stack and uses Raw sockets for sending TCP SYN probes. It doesn't need to set SYN Cookies so it doesn't wastes time checking if received packets is a result of it's own scan, that makes Nscan faster than other similar scanners.

Nscan has a cool feature which allow you to extend your scan by chaining found ip:port to another scripts where it might checks for vulnerabilities, exploit targets, check for Proxies/VPNs... 

# Getting Nscan to work

Installing Nscan on Debian/Ubuntu boxes:
```
$ git clone https://github.com/OffensivePython/Nscan
$ cd Nscan/nscan
$ chmod +x nscan.py
```

Check if nscan executes
```
$ ./nscan.py
Usage: 
nscan.py x.x.x.x/x [options]
nscan.py iface load/unload : Load/Unload Nscan interface alias
nscan.py resume filename.conf: resume previous scan


Options:
  -h, --help            show this help message and exit
  -p PORTS, --port=PORTS
                        Port(s) number (e.g. -p21-25,80)
  -t THREADS, --threads=THREADS
                        Threads used to send packets (default=1)
  --import=IMPORTS      Nscan scripts to import (e.g.
                        --import=ssh_key:22+check_proxy:80-85,8080)
  -b, --banner          Fetch banners
  -n COUNT              Number of results to get
  -o FILE, --output=FILE
                        Output file
  -c N,T, --cooldown=N,T
                        Every N (int) packets sent sleep P (float)
                        (Default=1000,1)
```
