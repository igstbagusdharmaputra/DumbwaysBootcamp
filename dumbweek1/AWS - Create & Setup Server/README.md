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

![text](./asset/network/4.png)

#### Setup Internet Gateway
Internet Gateway disini bertujuan untuk instance agar bisa berkomunikasi dengan instance yang lain atau satu jaringan komputer lain.
- Create Internet Gateway dan menambahkan tag sebagai identitas.

![text](./asset/network/5.png)

- Lakukan Attach to VPC untuk menginisialisasikan VPC yang dituju.
    - Contoh : VPC yang sudah dibuat sebelumnya (MY-VPC)

![text](./asset/network/6.png)

![text](./asset/network/7.png)

#### Setup Route Table Untuk Subnet Public dan Private
Route disini bertujuan untuk menghubungan jaringan yang berbeda yang dimana subnet dari ip public dapat terhubung ke internet melalui internet gateway dan subnet ip private dapat berkomunikasi ip private pada server public.

- Create route table dengan menambahkan name tag dan VPC.
    - Contoh : 
        - public-route-table
        - private-route-table

![text](./asset/network/9.png)

![text](./asset/network/12.png)

- Menambahkan masing-masing subnet pada setiap route table

![text](./asset/network/11.png)

![text](./asset/network/13.png)

## Setup Instance Pada Server Public



## Setup Instance Pada Server Private

## SSH Pada Server Public

## SSH Pada Server Private Melalui Server Public

## NAT Gateway