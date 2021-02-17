# Comandos-linux

########## Aplicando configuração de rede no Ubuntu a partir do 18.04 ##########

netplan apply ---> Esse comando valida a sintaxe do arquivo e vai aplicar as alterações.

netplan try ---> Esse comando valida a sintaxe do arquivo e vai aplicar as alterações no período de 120 segundos.

########## Configurar túnnel ##########

1 - Entrar no arquivo /etc/netplan/50-cloud-init.yaml e adicionar a configuração do arquivo o conteúdo descrito abaixo.

 version: 2
    
    tunnels:
        
        NOMEDOTÚNNEL:
         
         mode: gre
         
         local: iplocalpúblico
         
         remote: ipremotopúblico
         
         addresses:
         
          - "ip do túnnel"

########## Aplicando configurações nas interfaces GRE ##########

ip link set nomedotúnel up ---> Ativa a interface do túnnel

ip link delete nomedotúnel ---> Deleta o túnnel

ip link show ---> visualiza o status das interfaces do túnnel GRE



########## Aplicando configurações de fuso-horário no Ubuntu 18.04  Lts ##########

timedatectl list-timezones ---> Comando para listar todos os time-zone do sistema.

timedatectl list-timezones | grep America/Sao_Paulo ---> Comando para listar um timezone especifico no sistema.

timedatectl set-timezone America/Sao_Paulo ---> Comando para setar um timezone especifico no sistema.

timedatectl ---> Comando para vizualizar as informações de timezone do sistema.



########### Gerando chave publica e privada no linux ###############

ssh-keygen -t rsa -b 4096

ssh-copy-id -i /caminhodiretório/name-file.pub root@104.248.2.220

ssh -i /caminhodiretório//name-file.pub root@ip.do.destino


########### Comando para saber quais discos instalado no servidor e qual o tipo ###############

lsblk -o +ROTA,DISC-GRAN

########### Copiando arquivos entre servidores Linux ###############

Copiando um arquivo remoto para máquina local:
* scp user@domain:/pasta-remota/arquivo-remoto.txt /pasta-local/arquivo-local.txt

Enviando um arquivo local para um servidor remoto:
* scp /pasta-local/arquivo-local.txt user@domain:/pasta-remota/arquivo-remoto.txt

Copiando pastas e subpastas do servidor remoto para máquina local:
* scp -r user@domain:/pasta-remota/ /pasta-local/

Enviando pastas e subpastas da máquina local para o servidor remoto:
* scp -r /pasta-local/ user@domain:/pasta-remota/

Créditos: https://udgwebdev.github.io/dicas-de-terminal-copiando-arquivos-via-scp/







