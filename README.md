# important
if you create folder for volume
```
    mkdir -p ./elasticsearch
    chown -R 1000:1000 ./elasticsearch
```

# library for fluentd laravel
```
    https://github.com/ytake/Laravel-FluentLogger
```
# edit config to project
```
   ./fluentd/config/fluent.conf 
```
# production mode

Linux

The vm.max_map_count setting should be set permanently in /etc/sysctl.conf:
    
```    
    $ grep vm.max_map_count /etc/sysctl.conf
    vm.max_map_count=262144
```   
To apply the setting on a live system type: ```sysctl -w vm.max_map_count=262144```

macOS with Docker for Mac

The vm.max_map_count setting must be set within the xhyve virtual machine:
```    
    $ screen ~/Library/Containers/com.docker.docker/Data/vms/0/tty
```    
Just press enter and configure the sysctl setting as you would for Linux:
```    
    sysctl -w vm.max_map_count=262144
```    
Windows and macOS with Docker Toolbox

The vm.max_map_count setting must be set via docker-machine:
```    
    docker-machine ssh
    sudo sysctl -w vm.max_map_count=262144
```
