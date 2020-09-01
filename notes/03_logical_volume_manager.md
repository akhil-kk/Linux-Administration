
## Logical Volume Mnager

* You can create file systems that extend across multiple storage devices.
* You can aggregate multiple storage devices intoa single loial volume.
* Expand or shrink file sysytems in real-time while the data remains online and fully accessible.
* Migrate data from one storage device to another while online.

**Logical volume creation process**
1. Create one or mre physical volumes
2. Create volume group from those one or more physical volumes.
3. Create one or more logical volumes from the volume group.

```
lvmdiskscan             //Shows all storage devices to use 
lsblk                   // more info
lsblk -p                
fdisk -l                // see storage attached to the linux sysytem.
eg : pv create /dev/sdb // create a pv
pvs                     // view th elist of pvs

```
## Manage Users and Groups

* Case sensitive
* less than 8 characters in length by convention.
* The root account is always UID 0.

```
userdadd[options] username
-c "COMMENT"            // comments for account
-m                      // create the home dire tory
-s/shell/path           // The path to the users shell.
groups username         // to know the group
``` 

## Networking

**TCP IP**

* Used for networkcommunications.
* TCP = Transmission control protocol
* IP = internet protocol
* TCP - controls data exchange
* IP - Sends data from one device to another.

for a device on the network to communicate properly it needs 3 pieces of information.
 1. IP address
 2. subnet mask
 3. broadcast address

 Each one of these are comprised of four octets separated by a dot.
 An octet represents 8 bits.

 ### IP Networking

**IP address**
 * comprised of two parts
  * network address - tell what network the host belongs to
  * host addres     - tells the specific device the data is delivered to.

  ![IP](/notes/img/nw.png?raw=true "Title")

  **Subnet Masks**

  ![subnet](/notes/img/subnet.png?raw=true "Title")

  **Boroadcast Address**
* A boroadcast address is a special logical address used to send data to all hosts ona given network.

![subnet](/notes/img/broadcast.png?raw=true "Title")

**Reserved Address Space**

![reserved](/notes/img/reserved.png?raw=true "Title")

**Display IP**

```
ip a
ip addr
ifconfig
```

### DNS

Translate human readable name to  IP addresses.

![dns](/notes/img/dns.png?raw=true "Title")

displaying host name
```
hostname
uname -n
hostnam -f
```

### Netowrk ports

![dns](/notes/img/ports.png?raw=true "Title")

## Troubleshooting

 **ping**

 ```
 ping HOST
 ping -c count host // sent specific number of ackets to host
 tracepath-n google.com
 ```
![dns](/notes/img/stat.png?raw=true "Title")




