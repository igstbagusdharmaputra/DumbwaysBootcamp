# CREATE JENKINS JOB

- Pertama yang saya lakukan adalah membuat token github agar bisa diakses oleh jenkins, token yang digunakan berfungsi untuk mendapatkan akses workflow repo dan read/write.

![text](./asset/job/1.png)

- Selanjutnya menambahkan token yang sudah digenerate pada github dan diconfigure ke jenkins pada bagian github server. Untuk credential tambahkan terlebih dahulu dengan type `Secret text`.

![text](./asset/job/2.png)

- Membuat job baru dengan `Free stype project` lalu menambahkan repository url dan credential dari private key frontend sertah brach `main` pada github repository.

![text](./asset/job/3.png)

- Centang `Github hook trigger for GITScm polling` untuk integrasi source code ke github.

![text](./asset/job/3.1.png)

- Menambahkan ssh server remote yang ingin dihubungkan dengan publish over ssh. Pada kasus ini, saya tidak menggunakan ssh key private dari frontend.

![text](./asset/job/4.png)

- `Pada proses build di job jenkins menggunakan plugin publish over ssh, yang sebelumnya sudah di konfigurasi dan sudah berhasil konek ke remote server. Untuk remote directory udah masuk /home/user dan exec command berisi perintah yang akan dijalankan pada server remote. Pada tahap build pada dasarnya adalah proses change directory, melakukan pull source code terbaru, mematikan container, menghapus images sebelumnya, melakukan build image terbaru dan menjalankan container.` Berikut langkah atau konfigurasi build pada image multistage dan tanpa multistage pada aplikasi frontend 

## Build Frontend Dengan Image Multistage dan Tanpa Multistage


- Untuk exec command pada frontend pertama menggunakan image dengan tag multistage:latest serta memberikan jeda waktu beberapa menit dan melakukan penghapusan image dangling.

![text](./asset/job/6.2.png)

- Selanjutnya untuk frontend kedua hanya melakukan pull image terbaru yang didapatkan dari proses build di dockerhub.

![text](./asset/job/6.3.png)

- Untuk yang tanpa multistage pada frontend pertama dan kedua tidak memerlukan durasi waktu serta dengan tag image yang berbeda.

![text](./asset/job/6.png)

![text](./asset/job/6.4.png)

- Untuk setiap job pastikan sudah set 0 ms pada build, untuk mengantisipasi terjadinya proses build yang tidak bisa kita tentukan dikarenakan tergantung koneksi internet.

![text](./asset/job/6.1.png)

- Untuk push image ke docker saya menggunakan fitur yang sudah disediakan oleh docker, yaitu docker build yang terintegrasi dengan akun github, jadi ketikan melakukan push terhadap repositoy github maka docker akan otomatis melakukan proses build baru untuk melakukan perubahan yang terdapat pada repository github.

![text](./asset/job/7.png)

- Contoh ketika proses build selesai tedapat informasi yang bisa dilihat seperti recent builds.

![text](./asset/job/11.png)

- Berikut hasil ketika melakukan push ke repository github dan jenkins melakukan proses CI/CD.

![text](./asset/job/8.png)

- Berikut log github dari jenkins

![text](./asset/job/12.png)


# Setting Notification pada Jenkins dengan Slack Notification

- Install plugin slack notification pada jenkins.

![text](./asset/notif/1.png)

- Hubungkan atau integrasikan aplikasi slack ke jenkins.

![text](./asset/notif/2.png)

![text](./asset/notif/3.png)

- Pada saat melakukan intergasi slack kita mendapatkan token, sehingga perlu menambahkan ke credential jenkins untuk token tersebut.

![text](./asset/notif/4.png)

- Pada configure system cari bagian slack dan konfigurasi bagian workspace isi dengan nama yang sudah disediakan dari slack aplikasi, default channel isikan dengan nama channel dan untuk credential menggunakan slack-token yang sudah dibuat.

![text](./asset/notif/6.png)

- Pada setiap job build kita perlu menambahkan konfigurasi Post Build Action yang berfungsi untuk memberikan informasi ketika telah melakukan proses build.

![text](./asset/notif/7.png)

- Berikut hasil konfigurasi atau notification dari slack.

![text](./asset/notif/8.png)