# USER

- Install aplikasi ansible pada laptop atau pc 

![text](./asset/Screenshot_1.png)

![text](./asset/Screenshot_2.png)

![text](./asset/Screenshot_3.png)

NB: Untuk proses ansible memerlukan akses VPN server, laptop atau user ansible bisa mengakses server private pada aws, untuk cara dapat dilihat pada tutorial task bonus Access Private Network From External Network [VPN Server](https://github.com/igstbagusdharmaputra/DumbwaysBootcamp/tree/master/dumbweek2/Access%20Private%20Network%20From%20External%20Network)

- Selanjutnya copykan ssh key aws pada folder project ansible.

![text](./asset/Screenshot_4.png)

- Buat file invetory untuk menampung host atau ip pada setiap server yang terhubung.

![text](./asset/Screenshot_5.png)

- Untuk konfigurasi ansible.cfg, perlu inisialisasi Inventory, private key dan remote user untuk melakukan proses ansible.

![text](./asset/Screenshot_6.png)

- Sebelum login ke server private dengan user root, kita edit file authorized_keys dengan menghilangkan karakter sebelum ssh-rsa

![text](./asset/Screenshot_7.png)

![text](./asset/Screenshot_8.png)

![text](./asset/Screenshot_9.png)

- Lakukan test ping ansible dari ansible.

![text](./asset/Screenshot_10.png)

-  Lakukan update dan upgrade secara bersamaan terhadap server yang terhubung dengan ansible.

![text](./asset/Screenshot_11.png)

![text](./asset/Screenshot_12.png)

- Buat file .yml untuk melakukan installasi docker dan node exporter akan digunakan untuk monitoring dengan prometheus yang menghubungkan semua server.

![text](./asset/Screenshot_13.png)

![text](./asset/Screenshot_14.png)

![text](./asset/Screenshot_15.png)

![text](./asset/Screenshot_16.png)

- Install mkpasswd(whois) untuk generate password enkripsi dengan metode sha-512

![text](./asset/Screenshot_17.png)

- Buat file .yml untuk membuat user pada masing-masing server.

![text](./asset/Screenshot_18.png)

![text](./asset/Screenshot_19.png)

- Serta melakukan edit file konfigurasi ssh pada Password Authentication.

![text](./asset/Screenshot_20.png)

![text](./asset/Screenshot_21.png)

- Melakukan uji coba remote dengan user yang sudah dibuat.

![text](./asset/Screenshot_22.png)