# SETUP MONITORING SERVER

- Melakukan proses install prometheus dan grafana pada server monitoring dengan bantuan ansible untuk proses otomasi dan docker menjalankan aplikasi.

![text](./asset/monitoring/1.png)

![text](./asset/monitoring/2.png)

![text](./asset/monitoring/3.png)

- Melakukan proses otomasi terhadap reverse proxy nginx dengan melakukan copy file konfigurasi .conf ke server public

![text](./asset/reverse_proxy/1.png)

![text](./asset/reverse_proxy/2.png)

![text](./asset/reverse_proxy/3.png)

![text](./asset/reverse_proxy/4.png)

![text](./asset/reverse_proxy/5.png)

![text](./asset/reverse_proxy/6.png)

- Selanjutnya melakukan konfigurasi ssl dengan aplikasi certbot dan proses otomasi dari ansible.

![text](./ssl/1.png)

![text](./ssl/2.png)

![text](./ssl/3.png)

- Untuk prometheus terdapat kelemahan dalam security pada saat mengakses server tersebut, sehingga perlu authentication dari webserver nginx.

![text](./auth/1.png)

![text](./auth/2.png)