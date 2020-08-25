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











