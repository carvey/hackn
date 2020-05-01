# hackn
Resources being developed on the way to passing OSCP

These are a collection of helper scritps to automate repetitive tasks I have to go through when doing HTB or PWK machines.

## Scirpt Descriptions:

### rscan
Shortcuts for printing, running, and copying common scan commands such as nmap, gobuster, wfuzz.
```
kali@kali:~/hackn$ rscan
USAGE: rscan [ target ip/hostname ] [ scanning action ] [ optional action ]

kali@kali:~/hackn$ rscan -h
USAGE: rscan [ target ip/hostname ] [ scanning action ] [ optional action ]

Scripts to run include:
    nmap -> Do a full nmap scan of the designated host
    dirs -> Use gobuster to run a directory scan of the designated webserver
    subdomains -> Use wfuzz to run a subdomain scan. Note: You need to have a domain name for this! Don't just use with -r without checking the Host header!

Optional actions include:
    -r to run the command
    -c to copy the command to your clipboard
    Blank values will print out your command

Examples:
# to print out the full nmap command
rscan 10.10.10.13 nmap

# to run gobuster
rscan 10.10.10.13 dirs -r

# to copy wfuzz command to clipboard
rscan 10.10.10.13 dirs -c

# to scan for subdomains
rscan cronos.htb subdomains -r
```

### smbcrawl
Recursively downloads all files from an smb share.


### qscan 
Very short and quick netcat scan of a machine to determine within a few seconds what common ports are open. This is ran before nmap to get started on enumeration while nmap scans. 
```
kali@kali:~/hackn$ qscan
USAGE: qscan [ target hostname/ip ]

kali@kali:~/hackn$ qscan -h
USAGE: qscan [ target hostname/ip ]

Examples:
qscan 10.10.10.13
qscan cronos.htb
```
