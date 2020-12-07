# Instalasi Ubuntu Server 18.04 pada VMWare Workstation 15
## Setup pada VMWARE
1. Membuat virtual machine baru dengan typical (recomended)
![1](./asset/1.png)
2. Pilih iso sesuai lokasi file anda (ubuntu server 18.04)

![2](./asset/2.png)

3. Setting account user pada sistem operasi

![3](./asset/3.png)

4. Letakan lokasi install virtual machine atau vmdk pada directory anda

![4](./asset/4.png)

5. Setting size harddisk (20 GB)

![5](./asset/5.png)

6. Klik Finish

![6](./asset/6.png)

7. Edit Virtual Machine Setting
![7](./asset/7.png)
8. Remove CD/DVD dan Floppy autoinst (supaya tidak melakukan auto install)
![8](./asset/8.png)
## Installasi Sistem Operasi Ubuntu
1. Pilih Bahasa dan Keyboard Layout
![9-10](./asset/9.png)
![9-10](./asset/10.png)
2. Settup interface sesuai dengan adapter yang digunakan
![11](./asset/11.png)
3. setup proxy (kosongkan)
![12](./asset/12.png)

4. Pilih mirror address

![13](./asset/13.png) 

5. Pilih Continue without updating

![14](./asset/14.png)

6. Pilih Custom Storage Layout

![15](./asset/15.png)

7. Settup partisi swap 4G sesuai dengan 2x jumlah memory (RAM)

![16](./asset/16.png)

8. Settup partisi untuk system / dengan size 15.997G

![17](./asset/17.png)

9. Pilih Done

![18](./asset/18.png)

10. Setting profile account untuk sistem operasi ubuntu server

![19](./asset/19.png)

11. Uncheck openssh-server dikarenakan proses install ssh dilakukan manual, tekan done

![20](./asset/20.png)

12. Proses Installasi selesai
![21](./asset/22.png)