# Devtoolkit demo
### Preparation
1. Download and install [git-bash](https://gitforwindows.org/) **OR** configure WSL **OR** start up Linux VM **OR** use UNIX based OS **OR** use Windows CMD (but the lab workflow will be different)
2. Download and install [Java 1.8](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html) or higher. If you use **git-bash** then download Java for Windows.
3. [Disable Hyper-V virtualization](https://docs.microsoft.com/en-us/troubleshoot/windows-client/application-management/virtualization-apps-not-work-with-hyper-v) if will be necessary
4. Download and install [Vagrant](https://www.vagrantup.com/downloads) and [VirtualBox](https://www.virtualbox.org/wiki/Downloads). Tested versions bundle is Vagrant 2.0.0 and VB 5.1.36 OR Vagrant 2.2.16 and VB 6.1.22 OR try latest

## Build tools
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
3. `cd builders`
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

## Vagrant
1. `cd vagrant`
2. Vagrant commands:
    - `vagrant status` - shows status of VMs
    - `vagrant up` - startups VM or VMs
    - `vagrant ssh <NAME>` - ssh connection to a VM
    - `vagrant rsync` - syncs all files in vagrant dir into VM to /vagrant/
    - `vagrant halt` - stops VM
    - `vagrant destroy` - stops and removes VMs

### Vagrant tips
- `vagrant up --provision --debug &> debug_log` - how to collect logs. [Source](https://unix.stackexchange.com/questions/244343/where-is-vagrants-log-file)
- `mv Vagrantfile Vagrantfile.demo & mv Vagrantfile.jenkins Vagrantfile` - if you want to startap up Jenkin's vagrant box for home work.
