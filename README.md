# Bash-Scripting

``` Shell is native to linux and had better native advantage with better performance.

```
There are 300+ flavors of Linux :

Kali Linux :  Majority ethical hacking ppl will use this Flavor
Corporate : RedHat , CentOS ,  Ubuntu , Fedora , IBM AIX , HP_Unix , Cisco Unix ,OEL.

In Linux OS, there is no file-extensions. Extensions are given only for user understanding.
Also, linux commands and files are case sensitive.

Linux Directory Structure :
Unlike any operating system Linux also has its own directory structure and here in linux it starts with /
/ -> Root Directory

Types of files:
    d - Directory   
    - - Regular file 
    l - Link
    b - block devices
    c - character files 
    S - socket files 
    p - Named pipe file 

Permissions:

In linux, permissions are classifed to Read [ r and the value of it is 4 ] ,Write [ w and the value of it is 2 ] ,execute [ x and the value of it is 1 ] ,

 U:  4+2+1 = 7     [ Owner can read, write and execute the file ]
  G:  4+2   = 6     [ Owner can read, write the file ]
  O:  1     = 1     [ Other can just run the file ]

Process Management

Most useful commands to see the list of running process and their utliisations are :
$ ps
$ top

 $ ps -ef                 [ Shows every process on the system using standard syntax]
    $ ps -aux                [ Shows every process on the system using BSD syntax ]
    $ top                    [ Top shows you dynamic result and refresh the result for 3 seconds ]
    $ ps -U root -u root u   [ every process running as root (real & effective ID) ]

Kill is a command which has the capability to kill any process and the parent process of your choice. Also kill has lot of signals to kill :

 Syntax: 
        $ kill pID 
        $ kill -9 pID  [ To delete a process forcefully ]

Pipes : Pipes are used to send the output of one command to another command without storing the content anywhere physically on disk.

Syntax :  com1 | com2

Ex: cat /etc/passwd | grep root

sudo
sudo is a command in linux to give the temporary privileged access to the user
Below commands shows how to switch between the users

$ sudo su -   [will be switched to the root user]
# whoami      [shows you the output as root]

By default, in centos apart from root and the centos user, none of the users will be having root access.
Here is the file where we can add / enroll the users to gain sudo access

Service Management: Systemctl is the command to start,stop, restart , enable the service in centos 7.

# systemctl start serviceName
    # systemctl stop service
    # systemctl restart service
    # systemctl enable service

Network Management

# curl ifconfig.co   [ shows you the public ip address of the server ]
    # ip -a              [ shows you the private ip address of the server ] 
    # netstat            [ shows the network statistics ]
    # netstat -ln        [ shows the actual core information]
    # netstat -tulpn     [ shows you the list of listening ports and the associated process running on it]

`head`  : This prints the top 10 lines by default of the file
`tail`  : This prints the last/bottom 10 lines by default of the file



$ cat /etc/sudoers   [ You can see the list of users with sudo access in the system ] 





Linux Command Standard Syntax:

Command-name {options} {inputs}

Options:
    - <Single-Character>
    -- <Single-Word>

Standard Option to all the commands is --help
    Ex: uname --help

To check the vendor of the operating system.

$ cat /etc/*release

To check the CPU information

$ cat /proc/cpuinfo

To check the memory information

$ cat /proc/meminfo

To check the disk information

$ fdisk -l   or    lsblk

Get list of hidden files and directories.

$ ls -A

Get list of files with long format, usually shows properties of a file

$ ls -l



&&  :  Second command will be executed only if the first command is TRUE or a pass

        ex : df -h && uptime             : First command is true, second command will be executed
             df -asdfasf  && uptime      : first command is false, second command will not be executed

||  :  Second command will only be executed if the first command is false or a failued

        ex : df -h || uptime             : First command is true, second command will not be executed
             df -asdfasf  | uptime      : first command is false, second command will be executed