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