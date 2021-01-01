# Create Job dengan Jenkins Pipeline Script

## Install Jenkins

- Install menggunakan Dockerfile dikarenakan jenkins yang didalam container tersebut memerlukan docker untuk proses build dan lakukan build image pada dockerfile tersebut.

![text](./asset/Install/1.png)

- Jalankan container dengan image yang sudah dibuild, untuk jenkins pada docker hal yang diperlukan yaitu volume docker.sock, volume untuk jenkins_home, serta url jenkins prefix. Untuk jenkins prefix bertujuan agar tidak bentrok dengan jenkins yang sudah di install sebelumnya, serta port yang digunakan harus berbeda.

![text](./asset/Install/2.png)

- Melakukan reverse proxy pada aplikasi jenkins.

![text](./asset/Install/3.png)

- Hasil install jenkins

![text](./asset/Install/4.png)

## Install plugin yang diperlukan untuk Jenkins

- Plugin yang diperlukan yaitu Docker pipeline, Nodejs, Github Integration, dan SSH Agent.

![text](./asset/plugin/1.png)

![text](./asset/plugin/5.png)

![text](./asset/plugin/6.png)

- Konfigurasi Untuk tool yang digunakan pada menu Global Tool Configuration

![text](./asset/plugin/0.png)

- Setting tool git 

![text](./asset/plugin/2.png)

- Setting tool Node Js dengan versi 10

![text](./asset/plugin/3.png)

- Setting tool Docker

![text](./asset/plugin/4.png)

## Configure Webhook Jenkins to Github

- Pertama membuat API token pada jenkins untuk integrasi dengan github.

![text](./asset/webhook/1.png)

- Masuk ke repository project dan konfigurasi webhook serta memberikan secret dengan token jenkins.

![text](./asset/webhook/2.png)

- Hasil konfigurasi

![text](./asset/webhook/3.png)

## Create Job

- Membuat credential ssh dengan private key pada jenkins.

![text](./asset/JOB/1.png)

- Membuat credential username dan password untuk docker login.

![text](./asset/JOB/2.png)

- Membuat job baru dengan mode Pipeline

![text](./asset/JOB/3.png)

- Lalu check list Github hook trigger for GITScm Polling

![text](./asset/JOB/4.png)

- Sebelum melakukan build pastikan pada project sudah terdapat Jenkinsfile. Lalu isikan dengan script.
```
pipeline {
  environment {
     dockerRegistry = "dharmatkj/housy-be-multistage-2"
     dockerRegistryCredential = 'docker'
     dockerImage = ''
  }
  agent any
  tools {nodejs "node" }
  stages {
    stage('Cloning Git') {
      steps {
	      git branch: 'main', credentialsId: 'backend', url: 'git@github.com:igstbagusdharmaputra/backend-private-2.git'
      }
    }
    stage('Build') {
       steps {
         sh 'npm install'
       }
    }
    stage('Test') {
      steps {
        echo 'test'
      }
    }
    stage('Building image') {
       steps{
         script {
           dockerImage = docker.build dockerRegistry + ":latest"
         }
       }
     }
    stage('Upload Image') {
       steps{
         script {
           docker.withRegistry( '', dockerRegistryCredential ) {
             dockerImage.push()
           }
         }
       }
     }
     stage('Remove Unused docker image') {
       steps{
         sh "docker rmi $dockerRegistry:latest"
         sh 'docker rmi -f $(docker images -f "dangling=true" -q)'
       }
     }
     stage('Deploy App') {
        steps{
          sshagent(credentials: ['backend']) {
             sh """ ssh -t -t dharmabackend@10.200.3.86 -o StrictHostKeyChecking=no << EOF 
                cd /home/dharmabackend/backend-2/
                docker-compose down
                git pull origin main
                docker rmi dharmatkj/housy-be-multistage-2:latest
                docker-compose up -d
                exit
                EOF"""
            
          }
        }
     }
  }
}
```

- Selanjutnya proses integrasi build dengan github repository.

![text](./asset/JOB/5.png)

- Pastikan bahwa jenkins sudah bisa melakukan remote ssh ke server aplikasi.

![text](./asset/JOB/6.png)

- Berikut hasil Build job 

![text](./asset/JOB/7.png)

![text](./asset/JOB/8.png)

