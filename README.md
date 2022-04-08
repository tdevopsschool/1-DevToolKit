# Devtoolkit demo
## Vagrant Preparation
1. Download and install [git-bash](https://gitforwindows.org/) **OR** configure WSL **OR** start up Linux VM **OR** use UNIX based OS
3. Download and install [Vagrant](https://www.vagrantup.com/downloads) and [VirtualBox](https://www.virtualbox.org/wiki/Downloads). Tested versions bundle is Vagrant 2.0.0 and VB 5.1.36 OR Vagrant 2.2.16 and VB 6.1.22 OR try latest. Vagrant [mirror](https://www.filecroco.com/download-vagrant/download/)

## VM installation
1. Open git-bash or another terminal
2. Clone git repository [tdevopsschool/cm](https://github.com/tdevopsschool/cm)
    - `git clone https://github.com/tdevopsschool/cm.git`
3. Execute `vagrant up` command in folder with Vagrantfile
4. Check the installation logs, if everything is OK and you don't see error messages - cool. VM is almost ready. You may go inside VM `vagrant ssh` if you want to check VM is runnig 100%
5. Type exit command if you are inside the VM - `exit`
6. Open Vagrant file and comment (#) the rows with ansible provisioning. From 14 to 22 rows. And uncomment shell provisioning on 12 row. 
7. Save the Vagrantfile changes. 
8. Execute `vagrant provision` to start shell provisioning
9. `vagrant ssh`
10. Execute the commands for Gradle installation
```
curl -s "https://get.sdkman.io" | bash
source "/home/vagrant/.sdkman/bin/sdkman-init.sh"
sdk install gradle
```
12. You are done. Perfect! You may use the VM for all father home works and practices. 

### Vagrant usage
Vagrant commands:
- `vagrant status` - shows status of VMs
- `vagrant up` - startups VM or VMs
- `vagrant provision` - start provisioning process on running VM
- `vagrant ssh` - ssh connection to a VM
- `vagrant rsync` - syncs all files in vagrant dir into VM to /vagrant/
- `vagrant halt` - stops VM
- `vagrant destroy` - removes VM
- `vagrant destroy -f` - stops and removes VM

### Vagrant tips
- `vagrant up --provision --debug &> debug_log` - how to collect logs. [Source](https://unix.stackexchange.com/questions/244343/where-is-vagrants-log-file)

## Build tools - Home work
1. Go inside VM `vagrant ssh`
2. Clone the devtoolkit repo `git clone https://github.com/tdevopsschool/devtoolkit.git`
3. `cd builders` directory
4. Build Java code:
    - Ant
      - `ant compile` - compile classes 
      - `ant jar` - packing to jar
      - `ant run` or `java -jar build/jar/helloWorld-ant.jar` - execute jar file
      - `ant clean` - clean build directory
    - Maven
      - `mvn compile` - compile classes
      - `mvn install` - packing to jar
      - `java -jar target/helloworld-maven-0.1.0.jar` - execute jar file
    - Gradle
      - `gradle tasks` - list of tasks
      - `gradle jar` - packing to jar
      - `java -jar build/libs/helloworld-gradle-0.1.0.jar` - execute jar file


## Terminal Preparation if you don't want to use Vagrant and don't want to install build tools via OS package manager
Download and install [Java 1.8](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html) or higher. If you use **git-bash** then download Java for Windows.

> If you use git-bash add JAVA_HOME variable with paths to your java instalation folder, like `C:\Program Files\Java\jdk1.8.0_301`. [How to](https://windowsloop.com/add-environment-variable-in-windows-10/)
1. Download and unpack Ant, Maven and Gradle binaries
    - Download links:
        - Ant: https://ant.apache.org/bindownload.cgi
        - Maven: https://maven.apache.org/download.cgi
        - Gradle: https://gradle.org/install/#manually
    - Unpack commands:
        - `tar -zxvf <ARHCIVE>` for *tar.gz* archives
        - `unzip <ARHCIVE>` fir *zip* archives
    - Export binaries's paths to PATH
        - `export PATH=$PATH:<PATH_TO_BIN_DIRECTORY>`. Example: `export PATH=$PATH:/c/Users/emiachko/Desktop/temp/devtoolkit/gradle-7.0.2/bin`
