# Create & Setup Server

## Konfigurasi Interface

#### Setup VPC dan Subnet Public dan Private
Amazon Virtual Private Cloud (Amazon VPC) memungkinkan Anda menyediakan bagian yang terisolasi secara logika pada AWS Cloud di mana Anda dapat meluncurkan sumber daya AWS pada jaringan virtual yang Anda tentukan.

- Hal yang dilakukan pertama adalah membuat VPC dengan range atau network ip yang sesuai kebutuhan.
    - Contoh :
        - VPC ip  10.200.0.0/16

![text](./asset/network/1.png)

- Tentukan subnet untuk ip public dan private dengan IPv4 CIDRs yang sudah ditentukan
    - Contoh :
        - subnet ip public 10.200.0.0/24 
        - subnet ip private 10.200.1.0/24  

![text](./asset/network/2.png)

![text](./asset/network/3.png)

## Setup Instance Pada Server Public

## Setup Instance Pada Server Private

## SSH Pada Server Public

## SSH Pada Server Private Melalui Server Public

## NAT Gateway