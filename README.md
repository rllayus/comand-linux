# comand-linux
Comandos linux usados
## DOCUMENTACION
https://www.eginnovations.com/blog/jboss-performance-tuning/

## Comando para determinar la cantidad de conexiones TCP que existen
    netstat -n | awk '/^tcp/ {++state[$NF]} END {for(key in state) print key,"\t",state[key]}'
    
    
## Comando para visualizar los parametros de TCP
    sysctl -a |grep keepalive
    
### Comandos para setear valors TCP

    echo 15 > /proc/sys/net/ipv4/tcp_keepalive_intvl
    echo 5 > /proc/sys/net/ipv4/tcp_keepalive_probes
    echo 3000 > /proc/sys/net/core/somaxconn
    echo 3000 > /proc/sys/net/core/netdev_max_backlog
