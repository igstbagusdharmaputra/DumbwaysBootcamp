# SSH

- buat file .yml untuk generate ssh dari server private lain

![text](assets/Screenshot_1.png)

- tambahkan ansible_user pada Inventory

![text](assets/Screenshot_2.png)

- comment root pada ansible.cfg dikarenakan melakukan remote dengan user yang sudah dibuat dan run file .yml untuk generate ssh. saya menggunakan
keterangan -bkK:
		- b = become
		- k = ask ssh pass
		- K = ask become pass

![text](assets/Screenshot_3.png)

![text](assets/Screenshot_4.png)

-  Melakukan generate ssh-keygen pada laptop atau host yang terdapat ansible dan lakukan `ssh-copy-id ke semua server`

![text](assets/Screenshot_5.png)

- Membuat user universal terhadap semua server, user yang dibuat usahakan sesuaikan dengan user ansible.

![text](assets/Screenshot_6.png)

![text](assets/Screenshot_7.png)

- Coba melakukan remote dengan hostname atau ip address.

![text](assets/Screenshot_8.png)