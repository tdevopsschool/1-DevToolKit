# Devtoolkit demo
### Preparation
1. Download and install [git-bash](https://gitforwindows.org/) **OR** configure WSL **OR** start up Linux VM **OR** use UNIX based OS **OR** use Windows CMD (but the lab workflow will be different)
2. Download and install [Java 1.8](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html) or higher
3. [Disable Hyper-V virtualization](https://docs.microsoft.com/en-us/troubleshoot/windows-client/application-management/virtualization-apps-not-work-with-hyper-v)
4. Download and install [Vagrant](https://www.vagrantup.com/downloads) and [VirtualBox](https://www.virtualbox.org/wiki/Downloads). Tested versions bundle is Vagrant 2.0.0 and VB 5.1.36

## Build tools
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
      - `Ant compile` - compile classes 
      - `Ant jar` - packing to jar
      - `Ant run` or `java -jar build/jar/helloWorld-ant.jar` - execute jar file
      - `Ant clean` - clean build directory
    - Maven
      - `Mvn compile` - compile classes
      - `Mvn install` - packing to jar
      - `java -jar target/helloworld-maven-0.1.0.jar` - execute jar file
    - Gradle
      - `Gradle tasks` - list of tasks
      - `Gradle jar` - packing to jar
      - `java -jar build/libs/helloworld-gradle-0.1.0.jar` - execute jar file

## Vagrant
1. `cd vagrant`
2. Vagrant commands:
    - `vagrant up` - startup VMs
    - `vagrant ssh <NAME>` - ssh connection to a VM
    - `vagrant rsync` - sync all files in vagrant dir into VM to /vagrant/ 
    - `vagrant destroy` - stutdown and remove VMs
