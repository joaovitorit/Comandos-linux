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

