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

#### Registrar um serviço
- Criar o arquivo do serviço
- Registrar o serviço no client com o comando: consul reload

#### Usando o comando Dig para pesquisar servers e serviços
- dig @localhost -p 8600 nginx.service.consul

#### Encontrar em qual node o serviço esta registrado
- consul catalog nodes -service nginx

#### Detalhar todos os nodes existentes no consult
- consul catalog nodes -detailed

#### Criar clients com o retry join (alem de criar o client ja faz o join no cluster)
-consul agent -bind=172.21.0.6 -data-dir=/var/lib/consul -config-dir=/etc/consul.d -retry-join=172.21.0.2

#### Para ativar o health check
- Obs: Adicionar o parametro "-enable-script-checks=true" na subida dos agentes servers

#### Subindo agentes servers apontando para arquivo de configuração
- consul agent -config-dir=/etc/consul.d

#### Gerar chave para criptografia no consul
- consul keygen
