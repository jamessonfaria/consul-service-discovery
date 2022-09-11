# Consul Service Discovery

## comandos

#### Criar servers consul 
- consul agent -server -bootstrap-expect=<NUMBER_SERVERS> -node=<HOST_MACHINE> -bind=<IP_MACHINE> -data-dir=<DATA_DIR> -config-dir=<CONFIG_DIR>
    
    ex: consul agent -server -bootstrap-expect=3 -node=consulserver03 -bind=172.21.0.2 -data-dir=/var/lib/consul -config-dir=/etc/consul.d

#### Realizar join entre servers
- consul join <IP_MACHINE>

#### Verificar membros do cluster
- consul members

#### Criar clients consul
- consul agent -bind=<IP_MACHINE> -data-dir=<DATA_DIR> -config-dir=<CONFIG_DIR>
    
    ex: consul agent -bind=172.21.0.2 -data-dir=/var/lib/consul -config-dir=/etc/consul.d


