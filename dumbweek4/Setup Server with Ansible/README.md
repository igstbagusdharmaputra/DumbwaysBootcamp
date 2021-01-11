# SETUP SERVER WITH ANSIBLE

- Install ansible secara manual tanpa menggunakan docker
```
apt install python
sudo apt-add-repository ppa:ansible/ansible
apt update
apt install ansible
```

![text](./asset/start/1.png)

- Untuk langkah awal buat suatu folder untuk project Ansible dan tambahkan file `Inventory` untuk melakukan remote dengan user root dan file `ansible.cfg` untuk konfigurasi ansible

![text](./asset/start/2.png)

![text](./asset/start/3.png)

- Melakukan edit file ssh yaitu `authorized_keys` pada server.

![text](./asset/start/4.png)

- Pengujian melakukan remote dengan user root terhadap server.

![text](./asset/start/5.png)

- Ketika ansible sudah terhubung dengan server lainnya, maka lakukan pengujian ping pada ansible.

![text](./asset/start/6.png)

- Melakukan upgrage dan update repository tehadap server yang terhubung dengan ansible.

![text](./asset/start/7.png)

![text](./asset/start/8.png)

- Selanjutnya membuat user remote untuk sever yang tehubung dengan ansible, dengan bantuan automation file .yml ansible serta beberapa hal yang perlu diperhatikan adalah pada saat membuat password user adalah enkripsi pada account user tersebut, sehingga perlu menggunakan batuan tool `mkpasswd` dengan method sha-512

![text](./asset/create-user/1.png)

![text](./asset/create-user/2.png)

![text](./asset/create-user/3.png)

![text](./asset/create-user/4.png)

![text](./asset/create-user/5.png)

![text](./asset/create-user/6.png)

- Pengujian remote dengan user

![text](./asset/create-user/7.png)

NB: ketika sudah membuat user pada masing-masing server maka perlu menghapus remote_user=root pada file `ansible.cfg` serta menambahkan sintak `ansible_user` pada Inventory seperti `dharmapublic ansible_host=10.200.0.71 ansible_user=public`

- Instal Nginx pada public server.

![text](./asset/nginx/1.png)

![text](./asset/nginx/2.png)

- Selanjutnya melakukan generate ssh-key pada server frontend dan backend melalui ansible.

![text](./asset/SSH/1.png)

![text](./asset/SSH/2.png)

![text](./asset/SSH/3.png)

![text](./asset/SSH/4.png)

- Melakukan proses clone repository private pada github.

![text](./asset/GitClone/1.png)

![text](./asset/GitClone/2.png)

NB: Untuk proses upload public key ke github.com, lakukan secara manual

- Proses install mysql untuk database server.

![text](./asset/database/1.png)

![text](./asset/database/2.png)

![text](./asset/database/3.png)

- Pada proses ini lakukan Run docker terhadap aplikasi frontend, backend serta jenkins untuk ci/cd.

![text](./asset/docker-run/1.png)

![text](./asset/docker-run/2.png)

![text](./asset/docker-run/3.png)

- Melakukan install docker

![text](./asset/docker-run/4.png)