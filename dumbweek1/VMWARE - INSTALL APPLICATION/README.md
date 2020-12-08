# Instalasi WEB Server dengan NGINX dan Deploy Aplikasi NodeJS

## Instalasi Nginx
1. Hal pertama yang dilakukan adalah melakukan update terhadap repository ubuntu untuk menginstall aplikasi yang diperlukan.

![1](./asset/1.png)

2. Install packet aplikasi nginx.

![2](./asset/2.png)

3. Ketika install nginx sudah selesai, lakukan pengecekan (status) terhadap aplikasi.

![3](./asset/3.png)

4. Selanjutkan jalankan web server dengan ip static yang sudah di konfigurasi.

![4](./asset/4.png)

## Deploy aplikasi NodeJS
1. Hal pertama yang dilakukan adalah download repository nodejs dengan menggunakan versi 10 (https://github.com/nodesource/distributions).

![5](./asset/5.png)

2. Selanjutnya install aplikasi nodejs.

![6](./asset/6.png)

3. Clone repository project yang sudah disediakan.

![7](./asset/7.png)

4. Masuk kedalam directory project aplikasi dan lakukan npm install pada file package.json untuk meinstall dependencies yang diperlukan

![8](./asset/8.png)

5. Jalankan aplikasi dengan perintah npm start 

![9](./asset/9.png)

6. Lakukan pengujian pada browser dengan alamat ip address statik dan port 3000 (sesuai dengan aplikasi).

![10](./asset/10.png)
