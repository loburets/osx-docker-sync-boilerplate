# Docker-sync OS X boilerplate

OUTDATED! Nowadays docker is fine on OSX

## What is it

There is a problem with performance when you share code into Docker containers under OS X.
One of the solutions is [EugenMayer/docker-sync](https://github.com/EugenMayer/docker-sync) which used rsync and unison and has different options and strategies. But the repo has not very friendly documentation. 
This is a just example of using for the specific case when you have OS X and need two-way synchronization between your localhost and containers. 
In this case it can took about 1 minute if you have a lot of dependencies, but it is least evil. 
Furthermore, it is only for first running.
Original docker files will not be affected and you can get speed increases up to 10 times.

The main files exactly you want to see is:

- [docker-sync.yml](docker-sync.yml)
- [docker-compose-dev.yml](docker-compose-dev.yml)

All other is Docker containers for PHP and can be replaced by any what you want

## Install:

    sudo gem install docker-sync
    # At project directory
    git clone git@github.com:dima-loburec/osx-docker-sync-boilerplate.git docker
    cd docker/

## Use:

    docker-sync start
    docker-compose -f docker-compose.yml -f docker-compose-dev.yml up -d

    # Or to start at the same time:
    docker-sync-stack start
    # Crtl+C to stop
    
    # Stop and remove containers at the same time:
    docker-sync-stack clean
