# INSTALL JENKINS

- Menginstall jenkins dari docker dengan menjalankan perintah

```
docker run --name ci-cd -p 8080:8080 -p 50000:50000 -d -v jenkins_home:/var/jenkins_home jenkins/jenkins
```

docker akan secara otomatis mendownload jenkins yang ada pada docker hub

Keterangan: 
	- digunakan port 8080 untuk akses gui jenkins dan 50000 untuk jenkins master/slave
	- perintah -v untuk membuat volume jenkins yang ada pada directory jenkins_home
	- jenkins/jenkins merupakan images dari dockerhub
    - --name untuk memberikan nama container

![text](asset/1.png)

![text](asset/2.png)

- Pada tahap proses install jenkins perlu memasukan secret password dari jenkins dengan cara masuk ke dalam container aplikasi seperti gambar berikut.

![text](asset/4.png)

- Berikut proses installasi jenkins dengan menginstall plugin recommendation.

![text](asset/5.png)


- Reverse proxy pada jenkins

![text](asset/3.png)

- Berikut tampilan dari jenkins 

![text](asset/6.png)


untuk proses instalasi saya langsung pilih konfigurasi standar dan tambahan install plugin github, slack notification dan publish over ssh
