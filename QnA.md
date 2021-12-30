### Q1. What is a GNU project?
> GNU project was found by Richards Stallman in 1978 at MIT. It was a mass collaborative initiative for the development of free softwares.

- Core idea of GNU is to create free operating system where anyone who wishes to `copy, run, modify, study, distribute, improve` the software.
- This is comes under terms and condition of GNU GPL(General Public Licence) for copying, modifying and distributing free software.
- It was started to create a `Unix-like OS` created with source code that could be copied, modified, and redistributed.

### Q2. What is the difference between Linux & Unix?
| Linux                                                        | Unix                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| Linux is open source and is developed by Linux community of developers. | Unix was developed by AT&T Bell labs and is not open source. |
| Linux is free to use.                                        | Unix is licensed OS.                                         |
| Linux is just the kernel.                                    | Unix is a complete package of Operating system.              |
| Supported file systems are Ext2, Ext3, Ext4, Jfs, ReiserFS, Xfs, Btrfs, FAT, FAT32, NTFS. | Supported file systems are s, gpfs, hfs, hfs+, ufs, xfs, zfs. |
| Linux is used in wide varieties from desktop, servers, smartphones to mainframes. | Unix is mostly used on servers, workstations or PCs.         |
| Distros are Ubuntu, Debian GNU, Arch Linux, etc.             | SunOS, Solaris, SCO UNIX, AIX, HP/UX, ULTRIX etc.            |

### Q3. What do you mean by Integrity check of BIOS? Mention firmwares other than BIOS.
BIOS (Basic I/O System) is a firmware used to perform hardware initiallization during booting process and provides runtime services for operating systems. The main purpose of the BIOS is to perform system integrity checks, find the boot loader program and pass the control to that program. BIOS is an OS independent, special piece if firmware which runs from ROM(Read Only Memory).

The system integrity check performed by BIOS is called POST(Power On Self Test). This is a very brief test on CPU, memory and storage devices to verify that the system is in a boot-able state.

### Q4. What is a UEFI?
UEFI stands for `Unified Extensible Firmware Interface`. It does the same job as a BIOS, but with one basic difference: it stores all data about initialization and startup in an .efi file, instead of storing it on the firmware. UEFI comes with many improvements from the traditional BIOS firmware. 

### Q5. What is the difference between BIOS & UEFI?
* UEFI supports drive sizes upto 9 zettabytes, whereas BIOS only supports 2.2 terabytes.
 * UEFI has discrete driver support, while BIOS has drive support stored in its ROM, so updating BIOS firmware is a bit difficult.
 * UEFI offers security like "Secure Boot", which prevents the computer from booting from unauthorized/unsigned applications. This helps in preventing rootkits, but also hampers dual-booting, as it treats other OS as unsigned applications.
 * UEFI runs in 32bit or 64bit mode, whereas BIOS runs in 16bit mode. So UEFI  is able to provide a GUI (navigation with mouse) as opposed to BIOS which allows navigation only using the keyboard.

### Q6. When should you go for Ubuntu?
Ubuntu Linux is the most popular open source operating system. There are many reasons to use Ubuntu Linux that make it a worthy Linux distro. 
1. Ubuntu is user-friendly.
2. Ubuntu is free.
3. It’s secure. Say no to anti-virus.
4. Low system requirements.
5. It’s open source.
6. Improved compatibility, included drivers.
7. Free Apps

### Q7. List various linux distributions & their usecases.
1. `Debian ` : Bug Tracking, penetration testing, Network scanning
2. `CentOs ` : Rich base for open source communities
3. `Ubuntu ` : For personal computers & servers
4. `Fedora ` : Vast Software availability, Rapid release of softwares, excellent snap support

### Q8. What does a systemd.unit(5) means?
The number basically corresponds to the section of the manual page. 
| Number - | Meaning                                                      |
| -------- | ------------------------------------------------------------ |
| 1        | General Commands                                             |
| 2        | System Calls                                                 |
| 3        | Library functions, covering in particular the C standard library |
| 4        | Special files (usually devices, those found in /dev) and drivers |
| 5        | File formats and conventions                                 |
| 6        | Games and screensavers                                       |
| 7        | Miscellanea                                                  |
| 8        | System administration commands and daemons                   |

### Q9. What are getty commands and uname command?
**Getty** -  `getty` short for “get tty” is a Unix program running on a host computer that manages physical or virtual terminals to allow multi-user access. Linux provides virtual terminal(tty) which is similar to the regular Linux terminal. agetty command opens a virtual terminal(tty port), prompts for a login name and invokes the /bin/login command. `agetty` is a Linux version of getty.

**uname** - It prints system's information

### Usage

1. To print all information

```
uname -a
```

1. To print kernel name

```
uname -s
```

1. To print kernel release

```
uname -r
```

1. To print operating system

```
uname -o
```

### 

### Q10. What is squashfs file system?
Squashfs is a compressed read-only file system for Linux. Squashfs compresses files, inodes and directories, and supports block sizes from 4 KiB up to 1 MiB for greater compression. A squashfs file system consists of a maximum of nine parts, packed together on a byte alignment. It uses zlib, lz4, lzo, or xz compression to compress files, inodes and directories. 

### Q11. What are /dev/loop and /dev/tty ?
`/dev` is the location of special or device files. It is a very interesting directory that highlights one important aspect of the Linux filesystem - everything is a file or a directory.
`/dev/tty` stands for the controlling terminal (if any) for the current process (the process that uses "/dev/tty" in a command). To find out which tty's are attached to which processes use the "ps -a" command at the shell prompt (command line).

### Q12. What are Linux Signals?
* A **signal** is an event generated by the UNIX and Linux systems in response to some condition. Upon receipt of a signal, a process may take action.

  A **signal** is just like an interrupt; when it is generated at the user level, a call is made to the kernel of the OS, which then acts accordingly.

  There are two types of signals:

  - **Maskable:** signals which can be changed or ignored by the user. `e.g. Ctrl+C`.
  - **Non-maskable:** signals which cannot be changed or ignored by the user. These typically occur when the user is signaled for non-recoverable hardware errors. `Ctrl+Z`

### Q13. What is the purpose of creating and using hidden files.
Files that exist on a computer, but don't appear when listing or exploring, are called hidden files. A hidden file is primarily used to help prevent important data from being accidentally deleted. Hidden files are often known as a dot file. And we can also delete that file. 
For listing dot file :     `ls -ld .*` 

### Q14. How ext4fs is faster/better?
Ext4 introduces a lot of improvements in the ways storage blocks are allocated before writing them to disk, which can significantly increase both read and write performance.

It supports **Delayed Allocation**

For example

> when a process is writing continually to a file that grows, successive write()s allocate blocks for the data, but they don't know if the file will keep growing. Delayed allocation, on the other hand, does not allocate the blocks immediately when the process write()s, rather, it delays the allocation of the blocks while the file is kept in cache, until it is really going to be written to the disk. This gives the block allocator the opportunity to optimize the allocation in situations where the old system couldn't.

### Q15. What is swap & swap memory?
Swap space is parallel space within the RAM. When there is no enough RAM space available, linux kernel takes some of the information from RAM and writes it to the swap space on the hard drive. This process is swapping process.This way, your linux system can release some RAM space and doesn't crash due to lack of memory.

#### Two Swap options that we can use in linux

1. Swap partition
2. Swap file

| Swap Partition                                            | Swap File                                                |
| --------------------------------------------------------- | -------------------------------------------------------- |
| Part of your hard drive                                   | A file alternate to partition                            |
| Once configured, it is not easy to change                 | You can modify the size of the swap file anytime, easily |
| Created at the time of installing your Linux distribution | Can be created after the installation.                   |

### How to check swap space

**Check swap size**

```
free -h
```

**Check swap partition size, swap type with mount point**

```
swapon
```

### Q16. How to mount a file system?
To mount a file system in a given location (mount point), use the mount command in the following form: 
`mount [OPTION...] DEVICE_NAME DIRECTORY` 
For example, to mount the /dev/sdb1 file system to the /mnt/media directory we will use:
`sudo mount /dev/sdb1 /mnt/media`

### Q17. Mention a ZFS use case.
The `Zettabyte File System `(ZFS) is an advanced file system created by sun microsystems. Zfs use virtual storage pools known as storage pools that can deal with storage & management of large amounts of data. It is designed to ensure that no data cannot be lost due to physical errors or misprocessing by hardware or OS.

### Q18. How to check the port number of a process?
### Using netstat command

```
sudo netstat -tulpn | grep LISTEN
```

where,

- `-t` : All TCP ports
- `-u` : All UDP ports
- `-l` : display listening server
- `-p` : show PID & name
- `-n` : Don't resolves names & show ip `localhost` -> `127.0.0.1`

### Q19. What is unix time sharing (UTS)?
Unix is a time sharing OS as its environment provides multiprogramming & multitasking. It allows a large number of users to interact concurrently. It also brought down the cost of computing capabilities.

### Q20. What are control groups?
Cgroups are a facility built into the kernel that allow the administrator to set resource utilization limits on any process on the system. In general, cgroups control:

- The number of CPU shares per process.
- The limits on memory per process.
- Block Device I/O per process.
- Which network packets are identified as the same type so that another application can enforce network traffic rules.

**Cgroups have four main features closely related to each other that make them very important in a modern system**

1. Resource Limiting
2. Prioritizing
3. Accounting
4. Process control

### Q21. What is the difference between sbin & usr/sbin?
Both are the directories. It contains root binaries which are executable commands to perform particular tasks. Since they are root binaries, they require root privileges to run.
`/sbin` is a symbolic link to `/usr/sbin`.

### Q22. Examples of awk, grep and sed.
 The grep stands for ` “global regular expression print,” ` processes text line by line, and prints any lines which match a specified pattern.
 Syntax: 
 ` $ grep [options] pattern [files]` 
   demo.txt file:

```this is Sneha
this is Joe
this is David.
this is Chris.
this is Lily.
```
* `grep -c "this" demo.txt`

```4 ```



* `grep -l "Lily" *` 
```
demo.txt
```



* `grep -w "Joe" demo.txt`

```this is Naincy.
this is Joe.
```



* `grep -o "Chris" demo.txt`

```Sneha
Chris
```
 The `awk` can be used as a field extractor (like cut command), a basic calculator, and as a pattern matcher (like grep command) and It allows the user to use variables, numeric functions, string functions, and logical operators.
* `awk '/David/{print}' demo.txt`

```this is David```

* `awk '{print $1,$2}' demo.txt`
```this is
this is
this is
this is
this is
```

* `awk '{print NR,$0}' demo.txt`
```1 this is Sneha.
1 this is Joe
2 this is David
3 this is Chris
4 this is Lily
```
 sed is a `stream editor`. A stream editor is used to perform basic text transformations on an input stream (a file or input from a pipeline). It can perform lots of operations on file like, searching, find and replace, insertion or deletion.
* `sed 's/this/it/' demo.txt`
``` it  is Sneha.
it is Joe
it is David
it is Chris
it is Lily
```



* `sed 's/is/it/2' demo.txt`
```this  is  Sneha
this is Joe
this it David
this is Chris
this is Lily
```



* `sed 's/is/it/g' demo.txt`
```thit it Sneha.
this it Joe
this it David
this it Chris
this it Lily
```
### Q23. How many tables are there in iptables?
Iptable is the built-in linux firewall which includes some conditions, known as rules, according to which the traffic is allowed on the machine. It monitors the incoming and outgoing traffic and filter it according to the specified rules. \
IPTables has the following 5 tables: 

   1. `Filter Table` : This is the default table (if no -t option is passed). It contains the built-in chains INPUT (for packets destined to local sockets), FORWARD (for packets being routed through the box), and OUTPUT (for locally-generated packets).
   2. `NAT table` : This table is consulted when a packet that creates a new connection is encountered. It consists of four built-ins:
      - **PREROUTING** for altering packets as soon as they come in
      - **INPUT** for altering packets destined for local sockets
      - **OUTPUT** for altering locally-generated packets before routing
      - **POSTROUTING** for altering packets as they are about to go out
   3. `Mangle Table` : This table is used for specialized packet alteration.
   4. `Raw Table` : This table is used mainly for configuring exemptions from connection tracking in combination with the NOTRACK target. It registers at the netfilter hooks with higher priority and is thus called before ip_conntrack, or any other IP tables. It provides the following built-in chains:
      - **PREROUTING** for packets arriving via any network interface
      - **OUTPUT** for packets generated by local processes
   5. `Security Table` : This table is used for Mandatory Access Control (MAC) networking rules, such as those enabled by the SECMARK and CONNSECMARK targets. Mandatory Access Control is implemented by Linux Security Modules such as SELinux. The security table is called after the filter table, allowing any Discretionary Access Control (DAC) rules in the filter table to take effect before MAC rules.

### Q24. What is prot, opt, in, out, source & destination?
- `prot` : It denotes the protocol, for instance, tcp, udp.
- `opt` : Special options for that specific rule.
- `in` : Name of input interface via which the packet is received
- `out` : Name of output interface via which the packet will be send
- `source` : Source IP address or Domain Name
- `destination` : Destination IP address or Domain Name

### Q25. Why rules are added to the top?
Rules added to top are on high priority. Suppose if same rules with same criteria is added in INPUT chain with different targets. The one which is above will get high priority and below one will get low priority. Firewall will follow the high priority rule.

### Q26. What type of rules we can add to the iptables?
The iptables rules can be specified with 3 blocks, which are used for specific purpose (called `Chains`):

- **INPUT** : All packets destined for the host computer.
- **OUTPUT** : All packets originating from the host computer.
- **FORWARD** : All packets neither destined for nor originating from the host computer, but passing through (routed by) the host computer.

We can perform different actions on different rules:

- **ACCEPT** : Accepts the packages
- **DROP** : Deny the packages silently
- **REJECT** : Rejects ackages and informs or print messages.

### Q27. Can we block a website by its domain name only?
 Yes we can block a website by its domain name only by 
  ```
  $ sudo iptables -I INPUT -t filter -s www.facebook.com -j DROP
  ```

### Q28. How can we persist rules in iptables?
Persisting rules in iptables mean to store the rules in `/etc/iptables/rules.v4` or `/etc/iptables/rules.v6` such that they do not get deleted on reboot. The iptables-persistent package should be pre installed.

 ### Q29. How can we save rules in iptables?
  The generic method of saving iptables rules is to use the command iptables-save, which writes to stdout.
   ` $ iptables-save > /etc/network/iptables.rules`

 ### Q30.  What is the difference between ufw & iptables.

| iptables                                                     | ufw                                                          |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| iptables is a CLI tool that allows admins to configure specific rules that will enforce Linux kernel to perform actions such as accept, drop, reject, modify network packets. | UFW - Uncomplicated Firewall. It is also a firewall configuration tool implemented on top of iptables and developed to ease iptables firewall configuration. |
| To use IPtables you need to understand TCP/IP connections, more complicated protocols and it can still be complicated. | UFW provides a basic default firewall and allows you to easily turn on and off basic services. It provides a user friendly way to create an IPv4 or IPv6 host-based firewall. UFW is not as flexible but is easier to configure for common scenarios. |


### Q31. What are public & private keys?
| Public keys                                                  | Private keys                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| A public key that is copied to the SSH server. Once an SSH server receives a public key from a user and considers the key trustworthy, the server marks the key as authorized in its authorized_keys file. Such keys are called authorized keys. Now the user with private key for this corresponding public key can connect to the server. | A private key that remains only with the user. The possession of this key is proof of the user's identity. Only a user in possession of a private key that corresponds to the public key at the server will be able to authenticate successfully. The private keys need to be stored and handled carefully, and no copies of the private key should be distributed. The private keys used for user authentication are called identity keys. |


### Q32. How does ssh work?
SSH stands for `Secure Shell`. It is a communication protocol, which helps us in communication with other devices over a network, just like HTTP does. The difference main difference is It is known for sending encrypted data over the network so that it can be prevented from unauthorized access. It runs on port number 22 by default. SSH first ensures the authenticity of the client and then build a pipeline between the SSH client and the server. Data transmitted through this pipeline is encrypted by using the concept of Asymmetric Data Encryption.

### Q33. What is the difference between HTTP & HTTPS.
| HTTP                                         | HTTPS                                         |
| -------------------------------------------- | --------------------------------------------- |
| HTTP stands for HyperText Transfer Protocol. | HTTPS for HyperText Transfer Protocol Secure. |
| In HTTP, URL begins with “http://”.          | In HTTPs, URL starts with “https://”.         |
| HTTP uses port number 80 for communication.  | HTTPs uses 443 port number for communication. |
| HTTP is considered to be insecure.           | HTTPs is considered as secure.                |
| HTTP works at Application Layer.             | HTTPS works at Transport Layer.               |
| In HTTP, Encryption is absent.               | Encryption is present in HTTPS.               |

### Q34. What is SSL?
SSL stands for `Secure Sockets Layer` and, in short, it's the standard technology for keeping an internet connection secure and safeguarding any sensitive data that is being sent between two systems, preventing criminals from reading and modifying any information transferred, including potential personal details. SSL certificates are what enable websites to move from HTTP to HTTPS, which is more secure. An SSL certificate is a data file hosted in a website's origin server. SSL certificates make SSL/TLS encryption possible, and they contain the website's public key and the website's identity, along with related information.

### Q35. What is the difference between apt update & apt upgrade.
| apt update                                                   | apt upgrade                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| apt update is used to download package information from all configured sources. | apt upgrade is the command used to download and apply any available updates to your packages in a safe manner by not removing packages that are previously installed in a given Linux system |

### Q36. What do repositories contain in a Linux system?
A Linux repository is a storage location from which your system retrieves and installs OS updates and applications. Each repository is a collection of software hosted on a remote server and intended to be used for installing and updating software packages on Linux systems. When you run commands such as “sudo apt update” or “sudo apt upgrade”, you may be pulling package information and package updates from a number of repositories.

### Q37. What are the package managers used in Linux?
Package Manager is used to automating the process of installing, upgrading, configuring, and removing programs. There are many Package Manager today for Unix/Linux-based systems. Package Managers are available in different languages like python, ruby, etc.
![pkg1 (1)_page-0001](https://user-images.githubusercontent.com/87004609/138551497-1399544b-d4a0-4af7-b425-d41e5636bb3d.jpg)

### Q38. What does the number represent after the file permissions?
It simply dentoes the number of files in the directory. If its is a file, the number shows 1.

 ### Q39. What is the difference between apt and apt-get?
With apt, we get all the necessary tools in one place. The main aim of apt is to provide an efficient way of handling package. It has fewer but sufficient command options but in a more organized way. On top of that, it enables a few options by default that is actually helpful for the end users.

 ### Q40. How can I give access to someone to my AWS instance?
 1. Connect to your Linux instance using SSH. 
2. Use the adduser command to add a new user account to an EC2 instance (replace new_user with the new account name). The following example creates an associated group, home directory, and an entry in the /etc/passwd file of the instance.
`$ sudo adduser new_user`
3. Change the security context to the new_user account so that folders and files you create have the correct permissions:
`$ sudo su - new_user`
4. Create a .ssh directory in the new_user home directory:
`$ mkdir .ssh`
5. Use the chmod command to change the .ssh directory's permissions to 700. Changing the permissions restricts access so that only the new_user can read, write, or open the .ssh directory.
`chmod 700 .ssh`
6. Use the touch command to create the authorized_keys file in the .ssh directory:
`$ touch .ssh/authorized_keys`
7. Use the chmod command to change the .ssh/authorized_keys file permissions to 600. Changing the file permissions restricts read or write access to the new_user.
`$ chmod 600 .ssh/authorized_keys`

### Q41. What are daemon applications?
A daemon (also known as background processes) is a [Linux] program that runs in the background. Almost all daemons have names that end with the letter "d". For example, [httpd] the daemon that handles the Apache server, or, [sshd] which handles [SSH] remote access connections. Linux often start daemons at boot time. Shell scripts stored in [/etc/init.d] directory are used to start and stop daemons.

### Q42. What does a ".d" represent after a filename?
"d" stands for directory and such a directory is a collection of configuration files which are often fragments that are included in the main configuration file. The point is to compartmentalize configuration concerns to increase maintainability.

### Q43. What happens when a pem file gets deleted?
There is no way to recover the deleted pem file. The only solution is to create another one. And this can not be done using the console. We will have to use the CLI.

`$ aws ec2 create-key-pair --key-name MyKeyPair --query 'KeyMaterial' --output text > MyKeyPair.pem`

### Q44. What information is stored in the /etc/host file?
The /etc/hosts file contains a mapping of IP addresses to URLs. 

### Q45. What is SCP & what does this command do?
The SCP is a network protocol,which supports file transfers between hosts on a network. The scp command copies files or directories between a local and a remote system or between two remote systems. \
 ` $ scp -i key.pem demo.txt ubuntu@IP :/home/ubuntu `

### Q46. How port forwarding works?
 Port forwarding is a technique that is used to allow external devices access to computers services on private networks. SSH Port forwarding is used to forward ports between a local and a remote Linux machine using SSH protocol.Local port forwarding is the most common type of port forwarding. It is used to let a user connect from the local computer to another server, i.e. forward data securely from another client application running on the same computer as a Secure Shell (SSH) client.

### Q47. How can we connect without IP to AWS instance?
Assign an Elastic IP to the instance.

Go into the EC2 dashboard, then in the NETWORK & SECURITY menu go to Elastic IPs.

Click on Allocate a new address.

Right click on the new IP and select Associate address.

Associate it with your EC2 instance that doesn't have an elastic IP.

Now we can try to connect to the instance again and the RDP IP will be the elastic one instead of the VPC private one.

### Q48.  What is an ssh agent?
ssh-agent is a program to hold private keys used for public key authentication. The ssh-agent provides a secure way of storing the passphrase of the private key.

### Q49. Create a unit file for any application.
[Unit]
Description=The NGINX HTTP and reverse proxy server
After=syslog.target network-online.target remote-fs.target nss-lookup.target
Wants=network-online.target
Conflicts=apache2.service 

[Service]
Type=forking
PIDFile=/run/nginx.pid
ExecStartPre=/usr/sbin/nginx -t
ExecStart=/usr/sbin/nginx 
ExecReload=/usr/sbin/nginx -s reload 
ExecStop=/bin/kill -s QUIT $MAINPID 
PrivateTmp=true 

[Install] 
WantedBy=multi-user.target 



### Q50. What is RHEL?
Red Hat Enterprise Linux is a Linux distribution developed by Red Hat. Like all Linux distributions, RHEL is open source. Thus, people can view its source code, download it and make their own customized versions.Fedora, which is given entirely for free, is sponsored by Red Hat (the company) but is actively developed by a community of developers.