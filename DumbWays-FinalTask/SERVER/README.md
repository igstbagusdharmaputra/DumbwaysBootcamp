# SERVER

- Pertama buat VPC terlebih dahulu atau bisa menggunakan VPC Default.

![text](./asset/Screenshot_0.png)

- buat subnet untuk public yang terhubung dengan NAT instance, dan private yang terhubung ke server lain

![text](./asset/Screenshot_1.png)

![text](./asset/Screenshot_2.png)

-  Selanjutnya pembuatan nat instance dengan memilih community AMI dan pilih nat hvm

![text](./asset/Screenshot_3.png)

- Untuk konfigurasi server sesuaikan dengan kebutuhan atau spesifikasi yang diperlukan pada aplikasi, dan bagian configure subnet pilih yang public dan assign di enabled.

![text](./asset/Screenshot_4.png)

![text](./asset/Screenshot_5.png)

![text](./asset/Screenshot_6.png)

![text](./asset/Screenshot_7.png)

- Untuk security group kita open all network traffic agak semua sever dapat akses

![text](./asset/Screenshot_8.png)

- Buat keypair baru dan lakukan download.

![text](./asset/Screenshot_9.png)

- Setelah melakukan konfigurasi atau installasi pada nat instance, selanjutnya matikan source/destination check agar tidak mengganggu traffic jaringan internet dikarenakan aws akan mematikan internet ketika ada traffic yang tidak wajar.

![text](./asset/Screenshot_10.png)

- Membuat route table untuk subnet public dan private dan assosiasikan sesuai dengan nama yang dibuat.

![text](./asset/Screenshot_11.png)

![text](./asset/Screenshot_12.png)

![text](./asset/Screenshot_13.png)

![text](./asset/Screenshot_14.png)

![text](./asset/Screenshot_15.png)

- Selanjutnya membuat internet gateway untuk menghubungkan ke jaringan internet pada subnet public 

![text](./asset/Screenshot_16.png)

- Lalu attach VPC yang digunakan

![text](./asset/Screenshot_17.png)

![text](./asset/Screenshot_18.png)

- Selanjutnya masukan router internet gateway pada subnet public dan nat instance pada subnet private.

![text](./asset/Screenshot_19.png)

![text](./asset/Screenshot_20.png)

![text](./asset/Screenshot_21.png)

- Buat server public atau sever nginx dengan menggunakan sistem operasi ubunt server dan auto assign public ip "Disable" dikarenakan untuk server nantinya menggunakan ip elastic atau ip public static.

![text](./asset/Screenshot_22.png)

![text](./asset/Screenshot_23.png)

![text](./asset/Screenshot_24.png)

![text](./asset/Screenshot_25.png)

- Alokasikan elastic ip agara server nginx dapat diakses secara public dan mendapatkan akses internet 

![text](./asset/Screenshot_26.png)

![text](./asset/Screenshot_27.png)

- Untuk konfigurasi server yang lain kurang lebih sama, hanya saja security group dan konfigurasi network untuk server private yang berbeda.

![text](./asset/sg/Screenshot_1.png)

![text](./asset/sg/Screenshot_2.png)

![text](./asset/sg/Screenshot_3.png)

![text](./asset/sg/Screenshot_4.png)

![text](./asset/sg/Screenshot_5.png)

![text](./asset/sg/Screenshot_6.png)

- Untuk melakukan remote ke server private, lakukan login terlebih dahulu ke server nginx, maka perlu menambahkan ssh key aws ke server nginx untuk melakukan proses login.

![text](./asset/Screenshot_28.png)

![text](./asset/Screenshot_29.png)