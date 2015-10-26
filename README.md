mongosb
*******

Summary
=======

MongoDB Sandbox - Create, destroy, experiment, learn MongoDB - quickly!

Quick Install
=============

Setup your environment:

    mkdir -p ~/mongosb/bin
    mkdir -p ~/mongosb/msb

    cd ~/mongosb/bin
    wget https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-rhel70-3.0.6.tgz
    tar xzf mongodb-linux-x86_64-rhel70-3.0.6.tgz
    mv -f mongodb-linux-x86_64-rhel70-3.0.6 3.0.6
    wget --no-check-certificate -O ~/bin/mongosb \
        https://raw.githubusercontent.com/dotmanila/mongosb/master/mongosb
    chmod 0755 ~/bin/mongosb
    export MONGOSB_HOME=~/mongosb/msb
    export MONGOSB_BINARIES=~/mongosb/bin

Run your first sandbox:

    ~/bin/mongosb --release=3.0.6 create

Configuration
=============

The script creates a baseline configuration below:

    net:
      unixDomainSocket:
        pathPrefix: <dbPath>
      port: 27017
    processManagement:
      fork: true
      pidFilePath: <dbPath>/mongodb.pid
    storage:
      dbPath: <dbpath>
    systemLog:
      path: <dbPath>/mongodb.log
      destination: file

These values cannot be overridden from the command line when creating new instances.

You can pass additional configuration options at creation time from the command like like:

    mongosb --release=3.0.50 create -- storage.directoryPerDB=true storage.journal.enabled=true

This will create a configuration file with the additional options:

    [...]
    storage:
      journal: 
        enabled: true
      dbPath: <dbPath>
      directoryPerDB: true
    [...]

