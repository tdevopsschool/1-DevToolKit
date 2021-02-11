# Devtoolkit demo

## Build tools
1. Install Ant, Maven and Gradle
2. `cd builders`
3. Build Java code:
    - Ant
      - `Ant compile` - compile classes 
      - `Ant jar` - packing to jar
      - `Ant run` - execute jar file
      - `Ant clean` - clean build directory
    - Maven
      - `Mvn compile` - compile classes
      - `Mvn install` - packing to jar
    - Gradle
      - `Gradle tasks` - list of tasks
      - `Gradle jar` - packing to jar

## Vagrant
1. Install Vagrant and VirtualBox
2. `cd vagrant`
3. Vagrant commands:
    - `vagrant up` - startup VMs
    - `vagrant ssh <NAME>` - sshc connection to a VM
    - `vagrant rsync` - sync all files in vagrant dir into VM to /vagrant/ 
    - `vagrant destroy` - stutdown and remove VMs
