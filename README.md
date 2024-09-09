# Laboratorio sobre Camada de redes  

Data do expérimento 04/09/2024


##  Integrantes

| Matricula  | Nome |
| ------------- | ------------- |
| 200060783 |  Ana Beatriz Wanderley Massuh   |
| 190084570  | Arthur D'Assumpção Loureiro  |
| 200057421  | Delziron Braz de Lima  |
| 200017322  |  Emerson Luis Teles dos Santos  |
| 180016067  |  Erick Levy Barbosa dos Santos  |
| 190091606  | Lucas Caldas Barbosa de Souza  |
| 190020521  | Valderson Pontes da Silva Junior  |


## Componentes Utilizados

Switch de mesa, 2 Cabos de rede de 2 metros, 3 Adaptadores ethernet e 3 computadores

## Perguntas e Respostas

## 1 - Escolha três computadores, A, B e R e distribua os endereços IP, conforme apresentado na Figura 1 e monte as tabelas de rotas desses equipamentos, de modo que as máquinas da rede #01 consigam visualizar todas as máquinas da rede #02 (usar o comando ping para isso).

![fig1](/assets/FIG1.png)




### A) Qual o comando para atribuir um endereço IP para uma máquina Linux, usando a console (terminal)? Qual o comando para listar a tabela de rotas das máquinas (sintaxe geral)?

Primeiro comando necessario para desligar :

    sudo sistemclt stop NetworkManager 

Atribuir  o IP

    Computador A configura : sudo ifconfig eno1 172.25.0.2 netmask 255.255.255.0 up
    Computador B configura : sudo ifconfig eno2 192.168.93.2 netmask 255.255.255.0 up
    Computador R configura : sudo ifconfig eno2 192.168.93.1 netmask 255.255.255.0 up

Comando para repassar o ip nas maquinas:

    net.ipva4.ip_forward = 1

Comando para listar tabela de rotas:

    netstat -nr



### B ) Qual a tabela de rotas das máquinas A, B e R?

#### Tabela A

| Destino |Roteador | MáscaraGen. | Opções | MSS | Janela | irtt |Iface|
| ------ | --------- | ------ | --------- | ------ | --------- | ------ | --------- |
|172.25.0.0 | 0.0.0.0 | 255.255.255.0 | U | 0 |0 | 0 |enx00e04c534458|
|192.168.93.0 | 172.25.0.1 | 255.255.255.0 | UG | 0 |0 | 0 |enx00e04c534458|

#### Tabela B

| Destino |Roteador | MáscaraGen. | Opções | MSS | Janela | irtt |Iface|
| ------ | --------- | ------ | --------- | ------ | --------- | ------ | --------- |
|172.25.0.0 | 192.168.93.1 | 255.255.255.0 | UG | 0 |0 | 0 |enp2s0f0|
|192.168.93.0 | 0.0.0.0 | 255.255.255.0 | U | 0 |0 | 0 |enp2s0f0|

#### Tabela R

| Destino |Roteador | MáscaraGen. | Opções | MSS | Janela | irtt |Iface|
| ------ | --------- | ------ | --------- | ------ | --------- | ------ | --------- |
|172.25.0.0 | 0.0.0.0 | 255.255.255.0 | U | 0 |0 | 0 |eno1|
|192.168.93.0 | 0.0.0.0 | 255.255.255.0 | U | 0 |0 | 0 |enx00e04c534458 |






## 2 - 2. Altere a configuração anterior, de modo que as máquinas A, B e R consigam acessar a Internet, considerando o que está apresentado na Figura 2. Obs.: Implementar NAT no equipamento de saída para Internet.

![fig2](/assets/FIG2.png)

### A ) Qual o comando para atribuir um endereço IP para uma máquina Linux, usando a console (terminal)? Qual o comando para listar a tabela de rotas das máquinas (sintaxe geral)?
Atribuir  o IP
    Computador A configura : sudo ifconfig eno1 172.25.0.2 netmask 255.255.255.0 up
    Computador B configura : sudo ifconfig eno2 192.168.93.2 netmask 255.255.255.0 up
    Computador R configura : sudo ifconfig eno2 192.168.93.1 netmask 255.255.255.0 up
Comando para listar tabela de rotas:
    netstat -nr



### B ) Qual a tabela de rotas das máquinas A, B e R?




### C ) Que configurações adicionais foram necessárias para todas as máquinas tenham acesso à Internet? Na resposta, relatar o equipamento e as configurações adicionais feitas.






## 3 - Altere a configuração anterior, de modo que as máquinas A, B e R consigam acessar a Internet, considerando o que está apresentado na Figura 3. Obs.: Implementar NAT no equipamento de saída para Internet.

![fig3](/assets/FIG3.png)

### A ) Qual o comando para atribuir um endereço IP para uma máquina Linux, usando a console (terminal)? Qual o comando para listar a tabela de rotas das máquinas (sintaxe geral)?
Atribuir  o IP
    sudo ifconfig eno1 192.168.93.0 netmask 255.255.255.0 up
    sudo ifconfig eno2 172.25.0.0 netmask 255.255.255.0 up
Comando 
    netstat -nr




### B ) Qual a tabela de rotas das máquinas A, B e R?




### C ) Que configurações adicionais foram necessárias para todas as máquinas tenham acesso à Internet? Na resposta, relatar o equipamento e as configurações adicionais feitas.






