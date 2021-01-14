# CI/CD

Untuk schema diminta mendeploy aplikasi ketika ada commit dengan branch production.

![text](./asset/CiCd.png)

- Melakukan install jenkins melalui ansible, hal yang perlu diperhatikan adalah volume untuk jenkins, agar konfigurasi yang sudah dibuat tidak hilang begitu saja.

![text](./asset/Screenshot_1.png)

- Setelah melakukan proses instalasi jenkins tambahkan server untuk publish over ssh dengan key private yang ada pada server remote.

![text](./asset/Screenshot_15.png)

- Membuat personal token terhadap githu repo, agar jenkins mendapatkan informasi ketika ada perubahan pada repo github.

![text](./asset/Screenshot_2.png)

- Lalu masukan personal token ke dalam credential dengan type secret text.

![text](./asset/Screenshot_3.png)

- Setelah itu hubungkan jenkins dengan server github.

![text](./asset/Screenshot_4.png)

- Tambahkan credential dengan ssh key pada server, agar tidak memerlukan login username atau password pada saat proses git.

![text](./asset/Screenshot_5.png)

- Tambahkan slack token untuk slack notification.

![text](./asset/Screenshot_6.png)

![text](./asset/Screenshot_7.png)

- Hubungkan jenkins dengan slack notification.

![text](./asset/Screenshot_8.png)

- Membuat proses job atau freestyle projec pada jenkins dan memasukan url project.

![text](./asset/Screenshot_9.png)

- Untuk build proses trigger ketika github sudah melakukan proses push.

![text](./asset/Screenshot_10.png)

- Berikut proses build yang digunakan.

![text](./asset/Screenshot_11.png)

- Untuk proses setelah melakukan job, makan dilakukan proses notification dengan slack.

![text](./asset/Screenshot_12.png)

![text](./asset/Screenshot_13.png)

![text](./asset/Screenshot_14.png)