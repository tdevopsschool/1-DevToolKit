# Devtoolkit demo
### Preparation
1. Download and install [git-bash](https://gitforwindows.org/) **OR** configure WSL **OR** start up Linux VM **OR** use UNIX based OS **OR** use Windows CMD
2. Download and install [Java 1.8](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html) or higher 
## Build tools
1. Download and unpack Ant, Maven and Gradle binaries
    - Ant: https://ant.apache.org/bindownload.cgi
    - Maven: https://maven.apache.org/download.cgi
    - Gradle: https://gradle.org/install/#manually
3. `cd builders`
4. Build Java code:
    - Ant
      - `Ant compile` - compile classes 
      - `Ant jar` - packing to jar
      - `Ant run` or `java -jar ...` - execute jar file
      - `Ant clean` - clean build directory
    - Maven
      - `Mvn compile` - compile classes
      - `Mvn install` - packing to jar
    - Gradle
      - `Gradle tasks` - list of tasks
      - `Gradle jar` - packing to jar

## Vagrant
1. Download and install [Vagrant](https://www.vagrantup.com/downloads) and [VirtualBox](). Tested versions bundle is Vagrant 2.0.0 and VB 5.1.36
2. `cd vagrant`
3. Vagrant commands:
    - `vagrant up` - startup VMs
    - `vagrant ssh <NAME>` - ssh connection to a VM
    - `vagrant rsync` - sync all files in vagrant dir into VM to /vagrant/ 
    - `vagrant destroy` - stutdown and remove VMs
