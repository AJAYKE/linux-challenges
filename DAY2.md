## GET TO KNOW YOUR SERVER

Create an free tier instance on aws or any other free tier provider.
Syntax to ssh into your system from mac.

```bash
ssh -i <key_to_path/> ubuntu@ip
```

I got the error:

```bash
Permissions 0644 for 'default.pem' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
```

This means, your .pem file as a key for the instance does not have appropriate permissions to be used as the key

```bash
chmod 400 default.pem
```

This will solve your issue

commands to check:

1. General Information About the Server

```bash
lsb_release -a #this will show the linux distribution version you are using

#you can also check this in os-release file in etc

cat /etc/os-release
```

To see the system information of your instance

```bash
uname -a
```

```bash
uptime #this command will show you how long the instance has been up and running
```

```bash
whoami #this will show the username withwhich you logged in
```

2. Hardware Information

```bash
lshw #all the hardware information
lscpu #all the cpu configurations
lsblk #block devices are the storage devices to store fixed blocks of data
lspci #pci busses that connect with computer motherboard
lsusb
```

3. Memory CPU and Stoarge

```bash
#this will show the free memory available
free -h
vmstat

#top or htop are the commands for task manager in linux
top
htop

#this will show the disk storage consumption
df -h
```

4. Network

```bash
ip address
#or
ip addr show #this will show basic details needed

#to see the bandwidth usage, number of bytes in and out of the interface

sudo apt install ifstat

netstat -i #for a static view
ifstat  #for a realtime continuous view

#to see more detailed traffic and bandwidth information over an interface

sudo iftop -i eth0

# q to exit the stream
```
