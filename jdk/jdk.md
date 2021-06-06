# Установка Java с apt в Ubuntu 20.04
```
~$ sudo apt update
~$ java -version

Output
Command 'java' not found, but can be installed with:

sudo apt install default-jre              # version 2:1.11-72, or
sudo apt install openjdk-11-jre-headless  # version 11.0.7+10-3ubuntu1
sudo apt install openjdk-13-jre-headless  # version 13.0.3+3-1ubuntu2
sudo apt install openjdk-14-jre-headless  # version 14.0.1+7-1ubuntu1
sudo apt install openjdk-8-jre-headless   # version 8u252-b09-1ubuntu1

~$ sudo apt install default-jre
~$ java -version

Output
openjdk version "11.0.7" 2020-04-14
OpenJDK Runtime Environment (build 11.0.7+10-post-Ubuntu-3ubuntu1)
OpenJDK 64-Bit Server VM (build 11.0.7+10-post-Ubuntu-3ubuntu1, mixed mode, sharing)

~$ sudo apt install default-jdk
~$ javac -version

Output
javac 11.0.7

~$ sudo apt install software-properties-common
~$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys EA8CACC073C3DB2A

Output
gpg: key EA8CACC073C3DB2A: public key "Launchpad PPA for Linux Uprising" imported
gpg: Total number processed: 1
gpg:               imported: 1

~$ sudo add-apt-repository ppa:linuxuprising/java

Output
 Oracle Java 11 (LTS) and 12 installer for Ubuntu, Linux Mint and Debian.

Java binaries are not hosted in this PPA due to licensing. The packages in this PPA download and install Oracle Java 11, so a working Internet connection is required.

The packages in this PPA are based on the WebUpd8 Oracle Java PPA packages: https://launchpad.net/~webupd8team/+archive/ubuntu/java

Created for users of https://www.linuxuprising.com/

Installation instructions (with some tips), feedback, suggestions, bug reports etc.:

. . .

Press [ENTER] to continue or ctrl-c to cancel adding it

~$ sudo apt update
~$ sudo mkdir -p /var/cache/oracle-jdk11-installer-local/
~$ sudo cp jdk-11.0.7_linux-x64_bin.tar.gz /var/cache/oracle-jdk11-installer-local/
~$ sudo apt install oracle-java11-installer-local
~$ sudo update-alternatives --config java

Output
There are 2 choices for the alternative java (providing /usr/bin/java).

  Selection    Path                                         Priority   Status
------------------------------------------------------------
  0            /usr/lib/jvm/java-11-openjdk-amd64/bin/java   1111      auto mode
  1            /usr/lib/jvm/java-11-openjdk-amd64/bin/java   1111      manual mode
* 2            /usr/lib/jvm/java-11-oracle/bin/java          1091      manual mode

Press <enter> to keep the current choice[*], or type selection number:

~$ sudo vim /etc/environment

add JAVA_HOME="/usr/lib/jvm/java-11-openjdk-amd64"

~$ source /etc/environment
~$ echo $JAVA_HOME

Output
/usr/lib/jvm/java-11-openjdk-amd64
```

