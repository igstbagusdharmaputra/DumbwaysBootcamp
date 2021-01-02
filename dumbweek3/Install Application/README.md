## INSTALL APPLICATION FRONTEND

- Hal yang pertama yaitu membuat file docker-compose.yml pada project dan menbahkan script seperti gambar berikut. Pada frontend perlu menambahkan stdin_open.

![text](./asset/frontend/1.png)

- Selanjutnya menjalankan aplikasi tersebut dengan `docker-compose up -d`.

![text](./asset/frontend/2.png)

## INSTALL APPLICATION BACKEND

- Lakukan hal yang sama pada frontend, hanya saja isi file dari docker-compose.yml berbeda.

![text](./asset/backend/1.png)

![text](./asset/backend/2.png)

## INSTALL APPLICATON IMAGE MULTISTAGE

- Pada multistage pada frontend dan backend kurang lebih hampir sama dengan tanpa multistage hanya saja yang perlu diperhatikan pada frontend adalah port yang sudah di expose pada dockerfile.

![text](./asset/frontend/multistage/1.png)

![text](./asset/backend/multistage/1.png)