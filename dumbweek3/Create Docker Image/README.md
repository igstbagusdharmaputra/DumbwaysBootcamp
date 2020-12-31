# CREATE DOCKER IMAGE FRONTEND

- Membuat Dockerfile dengan isi sebagai berikut

![text](./asset/frontend/1.png)

- Build dengan perintah sebagai berikut

```
docker build -t namaimage:tag .
```

![text](./asset/frontend/2.png)

- Cek docker images yang sudah dibuild

```
docker images
```

![text](./asset/frontend/3.png)

- Menjalankan aplikasi frontend dengan docker run, yang perlu diperhatikan pada aplikasi frontend perlu interactive shell sehingga perlu parameter -it

```
docker run --name housy_fe -it -d -p 3000:3000 dharmatkj/housy-fe:latest
```

![text](./asset/frontend/4.png)


NB: pastikan port tidak bentrok dengan aplikasi lain.

- Cek jika container sudah berjalan dengan `docker ps` atau bisa cek dengan `docker log nama-container`

![text](./asset/frontend/5.png)

- Untuk push image, buat image dengan format akundocker/namaimage:tag dan pastikan sudah login terlebih dahulu. lalu jalankan perintah 

```
docker push namaimage:tag
```

![text](./asset/frontend/6.png)

![text](./asset/frontend/7.png)

# CREATE DOCKER IMAGE BACKEND

- Terkait langkah-langkah pada dasarnya sama seperti membuat images pada frontend, namun ada beberapa parameter yang berbeda seperti port ataupun dependency package berikut dockerfile dari backend.

![text](./asset/backend/1.png)

- Proses build images untuk aplikasi backend

![text](./asset/backend/2.png)

![text](./asset/backend/3.png)

- Proses pembuatan container dan running container.

![text](./asset/backend/4.png)

- Proses docker push image ke docker hub

![text](./asset/backend/5.png)

![text](./asset/backend/6.png)

# MULTISTAGE IMAGE PADA DOCKERFILE

```
Dengan multi-stage build kita bisa menggunakan statemen FROM lebih dari 1, dan setiap FROM bisa menggunakan base image yang berbeda, dan setiap statemen FROM dipanggil menandakan pembuatan image pada stage baru, anda juga bisa dengan mudah menyalin artifacts dari satu stage ke stage lain, sehingga size image bisa menjadi lebih kecil daripada yang tanpa menggunakan multistage.

```
- Berikut Docker file multistage dari frontend

![text](./asset/frontend/multistage/1.png)

![text](./asset/frontend/multistage/2.png)

- Berikut Docker file multistage dari backend

![text](./asset/backend/multistage/1.png)

![text](./asset/backend/multistage/2.png)