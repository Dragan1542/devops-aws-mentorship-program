# 📝 Class notes
## 📅 Date: 21.02.2023.
### Linux / UNIX Operativni sistemi

**UNIX** je stabilan, mocan i fleksibilan operativni sistem visokih performansi pogodan za
izvrsavanje kriticnih aplikacija od visoke vaznosti. **UNIX** je cvrsto povezan sa mreznim
servisima TCP/IP protokola, cime je u potpunosti promijenjena slika **UNIX**  servera i radnog
okruženja iz prošlosti. Umjesto servera sa klasicnim serijskim terminalima UNIX server se
nalazi u mreži, pri cemu sa radnim stanicama ostvaruje vezu preko LAN/WAN mreže i
TCP/IP skupa protokola. Veina velikih svetskih proizvodjaca racunara razvija specificnu
varijantu UNIX operativnog sistema, što ukazuje na njegov kvalitet, popularnost i
rasprostranjenost. Vecina UNIX sistema, poput Red Hat Enteprise, je komercijalna -
korisnik mora da plati licencu za korišenje, a izvorni kod nije rasploziv. To su razlozi
narastajuce popularnosti Linux sistema koji zadržava vecinu dobrih osobina UNIX
sistema, a dodatno se odlikuje raspolozivim izvornim kodom i prakticno besplatnim
korišenjem. Zbog toga danas veina proizvoaca racunara osim sopstvene komercijalne
verzije UNIX sistema nudi i podršku za Linux. Linux se najcesce koristi kao operativni
sistem na radnim stanicama ili serverima u manjoj ili srednjoj klasi servera, a jedna od
oblasti dominantne primjene, u kojoj veliki broj korisnika podržava i promoviše Linux kao
bazicni server, su Internet servisi. **(dio iz knjige [Linux i UNIX - B. Djordjevic, D.Pleskonjic, N.Macek - Beograd 2004](/resources/books/os-unix-i-linux-beograd-el-skola.pdf))**

**Osnovne Linux/UNIX komande:**

```bash
$ man ssh #Manual for ssh command $ man <command-name>

$ ssh [ip or hostname] #Secure shell, an encrypted network protocol 
                       #allowing for remote login and command execution  

$ ssh -vvv #verbose for troubleshooting access

$ pwd #displays the current directory

$ sudo su - #Switch to root user

$ whoami #Displays your logged in user id

$ id #Displays your user id and group id

$ hostnamectl #Displays your hostname

-----------------OUTPUT-----------------
[centos@ip-172-31-34-106 /]$ hostnamectl
   Static hostname: ip-172-31-34-106.eu-central-1.compute.internal
         Icon name: computer-vm
           Chassis: vm
        Machine ID: e887fc2c7f8279b206b7f75ba0a2b0bd
           Boot ID: 0431ad5636434ef2874634b3de2d90ad
    Virtualization: xen
  Operating System: CentOS Linux 7 (Core)
       CPE OS Name: cpe:/o:centos:centos:7
            Kernel: Linux 3.10.0-1160.76.1.el7.x86_64
      Architecture: x86-64
-----------------END-----------------  

$ cd / #Change directory to the root of the filesystem

$ cd target  #Change directory to “target” directory

$ cd ~ #Change directory to your user home directory

$ cp file1 file2 #Copy file1 to file2

$ cp -r dir1 dir2 #Copy directory dir1 to dir2

$ mv file1 file2 #Move file1 to file2, file1 is deleted

$ rm file1 #Remove file1

$ rm -r dir1 #Remove directory dir1 and all its contents

$ ls # Directory listing

$ ls -l 

$ ls -la #Long listing, displays file ownership Displays hidden files/directories

$ cat file1 #Display the contents of file1

$ tail -10 file1 #Display the last 10 lines of file1

$ head -10 file1 #Display the first 10 lines of file1

$ less file1 #Display the contents of file1, one screen at a time

$ diff file1 file2 #Display the differences between file1 and file2

$ sed 's/old/new/g' file1 > file2 #Replace all occurrences of “old” with “new” in file1 and save the result in file2

$ grep 'pattern' file1 #Display all lines in file1 containing the pattern

$ awk '{print $1}' file1 #Display the first column of file1

$ awk -F : '{print $1}' /etc/passwd #Display the first column of /etc/passwd

$ scp username@remote:/file/to/send /where/to/put #Copy file from remote host to local host

$ scp username@remote_1:/file/to/send username@remote_2:/where/to/put #Copy file from remote host to remote host

$ rsync -e "ssh -P $port_value" remoteuser@remoteip:/path/  localpath #Copy file from remote host to local host
```


[grep command - slika](/resources/images/grep.jpg)    
[find command - slika](/resources/images/find.jpg)      
[Find i Grep - Notability biljeske](/resources/notability/bash_notes.pdf)  

```bash
$ chmod 600 <filename> #Change persmissions for user
$ chmod u+x <filename> #Change persmissions for user
$ chown user:group <filename> #Chenge owner
```

 - Struktura Linux/Unix file sistema

```bash
$ tree #list contents of directories in a tree-like format`
$ tree -L 2 #list contents of directories in a tree-like format with depth 2
```

 ```bash
 [centos@ip-172-31-34-106 /]$ tree -L 1
.
|-- bin -> usr/bin
|-- boot
|-- dev
|-- etc
|-- home
|-- lib -> usr/lib
|-- lib64 -> usr/lib64
|-- media
|-- mnt
|-- opt
|-- proc
|-- root
|-- run
|-- sbin -> usr/sbin
|-- srv
|-- sys
|-- tmp
|-- usr
`-- var
 ```

  ![alt Linux Directory Structure](/resources/images/linux-dirs.jpeg)  


## 📖 Reading materials
- [Linux i UNIX - B. Djordjevic, D.Pleskonjic, N.Macek - Beograd 2004](/resources/books/os-unix-i-linux-beograd-el-skola.pdf) 
- [Osnove Administracije Operacijskog Sustava Linux - Obrazovni Sustav Srce Hr](/resources/papers/osnove-administracije-operacijskog-susteva-1-linux-srca.pdf) | [Biljeske iz Knjige](/devops-mentorship-program/02-february/week-2-210223/files/osnove-administracije-linuxa-biljeske.md)  
- [UNIX and Linux System Administration Handbook, 5th Edition](/resources/books/unix-linux-sys-admin-handbook.pdf)   
- [UNIX Operativni Sistemi](http://os.etf.rs/POS/tutorials/srdjan/kurs/html/sadrzaj.html)   
- [yum cheat sheet](/resources/chaet-sheets/yum-cheatsheet.pdf)  
- [Linux Performance Analysis in 60,000 Milliseconds](https://netflixtechblog.com/linux-performance-analysis-in-60-000-milliseconds-accc10403c55)   
## 📹 Session recordings  
- [**WEEK-2-tier-1-group-1 video session recording**](https://youtu.be/VWUv7sISfs0)   
- [**WEEK-2-tier-1-group-2 video session recording**](https://youtu.be/ZbtgMIyu5ZY)  

## 🛠️ Tools 
- vim - [Vim Cheat Sheet 1](/resources/chaet-sheets/vi-vim-cheat-sheet-and-tutorial.pdf) [Vim Cheat Sheet 2](https://vim.rtorr.com/)
- [:octocat: tmux](https://github.com/tmux/tmux/wiki)
- [chmod calculator](https://chmod-calculator.com/)



[:fast_forward: Homework Task](/devops-mentorship-program/02-february/week-2-210223/01-homework.md)  
[:fast_forward: Additional Reading](/devops-mentorship-program/02-february/week-2-210223/02-additional-reading.md)   
[:fast_forward: HOME - README.md](https://github.com/allops-solutions/devops-aws-mentorship-program#devops-mentorship-program)  
