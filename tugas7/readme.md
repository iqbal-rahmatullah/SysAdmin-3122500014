<div align="center">

## LAPORAN WORKSHOP ADMINISTRASI JARINGAN

![Logo_PENS](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/8a555f25-f1dd-4af9-b0bd-14c19bcefdc6)

### Disusun Oleh:

### Muhammad Iqbal Rahmatullah D3 IT A /3122500014

### Mohammad Ilham Ramadani D3 IT A /3122500021

### Rifqi Rayita Dhiyaulhaq D3 IT A /3122500027

### Dosen Pembimbing :

### Dr. Ferry Astika Saputra ST, M.Sc

</div>

</br>

---

</br>
</br>

### **Install Docker Engine, Uninstall Conflicted**

Jalankan command berikut untuk menghapus konflik dalam paket :

`for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done`

<div align="center">

![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/2ef546ab-3103-49ab-a087-224218ec1a59)

</div>

### **Install Docker Engine**

Set up docker dengan command berikut sesuai dokumentasi :

#Add Docker's official GPG key:

`sudo apt-get update`

`sudo apt-get install ca-certificates curl`

`sudo install -m 0755 -d /etc/apt/keyrings`

`sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc`

`sudo chmod a+r /etc/apt/keyrings/docker.asc`

#Add the repository to Apt sources:

`echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null`

`sudo apt-get update`

<div align="center">

![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/4ac1480b-2d89-4d91-b16a-222b43b52b4f)

![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/34037c01-5705-44a9-b557-b554b55fd8ed)

</div>

Install the Docker packages latest version :

`sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin`

<div align="center">

![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/e5f85823-b850-4de6-9b4c-46c5f4ea9bc9)

</div>

### **Start Docker Engine**

Start Docker Engine dengan command :

`sudo service docker start`

<div align="center">

![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/7378abd6-e8b9-47ba-9bb6-e765428d3514)

</div>

### **Run a Container**

Jalankan command berikut untuk mengecek apakah instalasi docker sudah dilakukan dengan benar

`sudo docker run hello-world`

<div align="center">

![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/0423a6e7-655d-46af-8c39-464ccae272e0)

</div>

### **Simple Project**

Clone project dari link berikut :

https://github.com/alfiyansys/docker-examples.git

dan masuk ke directory docker-examples

<div align="center">

![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/f2bec931-c9b7-4b72-82e7-a9e06f57a3cb)

</div>

Jalankan Build image Example project dengan command :

`docker-build -t example.`

<div align="center">

![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/eb008c91-3795-4509-bccd-8aa3232a8749)

</div>

`docker run -p 3000:80 example`

<div align="center">

![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/cd3cd240-344e-4629-8297-dda8c516e956)

</div>

Masuk web browser dan cek menggunakan localhost port 3000

<div align="center">

![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/7cf6dd5e-ac9c-4685-819b-78deb3660004)

</div>

menampilkan daftar container yang berjalan di sistem docker, menggunakan command :

`sudo docker ps`

<div align="center">

![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/0a5f6937-2f22-44f7-bfa9-1f350823cb4b)

</div>

### **Tugas Run Uptime-Kuma**

1. Clone repository uptime-kuma pada link berikut:

   https://github.com/louislam/uptime-kuma.git

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/b7ba4721-2609-4335-99da-6db9153e1781)

    </div>

2. Masuk ke direktori dimana uptime-kuma diclone, kemudian start uptime-kuma dengan

   `sudo docker compose up`

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/c3aef76c-32ac-4f41-bb87-ee15bded9e89)

    </div>

3. Cek apakah uptime-kuma sudah running dengan sudo docker ps

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/c54323dc-adca-40ee-860d-10fe887efaf0)

   </div>

4. Uptime-kuma berjalan di 0.0.0.0:3001

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/29ecde78-21f0-492f-bc74-8fea9aa23c05)

   </div>

### **CARA AGAR BISA MENGGUNAKAN DOMAIN monitoring.kelompok6.local**

1. Konfigurasi file dengan masuk direktori /var/lib/bind/db.kelompok6.local, kemudian run command

   `sudo nano /var/lib/bind/db.kelompok6.local`

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/62a2b83d-90d5-4b4f-9b3e-60aca38c6015)

    </div>

   mendefinisikan alias DNS (CNAME) untuk host monitoring yang akan mengarah ke host ns (dalam hal ini alamat IP 192.168.6.10).

2. Ubah config 000-default.conf pada apache dengan command

   `sudo nano /etc/apache2/sites-enabled/000-default.conf`

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/2efd384f-96a5-41ea-b12f-a3e76c36f1b3)

    </div>

   - ServerName monitoring.kelompok6.local: Menetapkan nama server yang akan digunakan untuk VirtualHost ini.
   - ProxyPreserveHost on: Memastikan bahwa header Host tetap tidak berubah saat permintaan diproses oleh proxy. Ini berguna karena memiliki beberapa VirtualHost yang ditangani oleh 000-default.conf.
   - ProxyRequests off: Mematikan kemampuan server untuk bertindak sebagai proxy forward, yang berarti server tidak akan meneruskan permintaan ke server lain.
   - ProxyPass / http://localhost:3001/: Menetapkan bahwa semua permintaan yang datang ke monitoring.kelompok6.local akan diproses oleh proxy dan diteruskan ke http://localhost:3001/ (docker uptime kuma dijalankan).
   - ProxyPassReverse / http://localhost:3001/: Menkonfigurasi Apache untuk mengubah header dalam respons yang diterima dari server proxy sehingga terlihat seolah-olah respons berasal dari server Apache, bukan dari server backend asli.

3. Lakukan Restart Apache dengan command berikut :

   `sudo systemctl restart apache2`

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/9f7cd047-205c-4749-a63c-43a16b0f9c15)

    </div>

4. Cek pada web browser

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/f4615c27-1d47-4c71-b832-7b7717c287f2)

   </div>

   ![video_bukti](./record_result.gif)

---

### **PLAY WITH DOCKER**

1. Masuk halaman website berikut: https://labs.play-with-docker.com/.

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/42064fb8-88d5-4dc6-9735-1072e3068e74)

    </div>

2. Login menggunakan akun yang sudah terhubung dengan docker atau register jika belum punya

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/afe40759-2d16-4bd0-bbc4-f6d6e3407b1c)

    </div>

3. Klik start dan anda akan diarahkan ke laman berikut

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/dfeaa7d9-cc02-41c4-8f57-d06ba545b125)

   </div>

4. Kemudian tambah tab untuk masuk ke halaman website berikut: https://www.docker.com/101-tutorial/. Dan scroll ke bawah hingga menemukan Play with Docker

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/8020d0de-4051-4c7e-9d66-6fcce9c12382)

   </div>

5. Kembali ke terminal sebelumnya, add instance Masukkan command berikut:

   `docker run -dp 80:80 docker/getting-started:pwd`

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/7d1f797f-cbd1-4f4b-90cc-115e8893f918)

   </div>

6. Lalu akan muncul port 80, klik halaman tersebut dan anda akan dialihkan ke cara penggunaan Docker 101 pada dockerLabs

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/126fbc2f-b529-40c4-9ddd-2482c2229359)

   </div>

#### **dockerLabs : Our Application**

#### Getting our App into PWD

1. Download the zip dan upload pada terminal, dengan cara drag and drop

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/e788117e-0e7b-48c7-b701-b5b619b5538e)

   </div>

2. extract zip yang sudah di download

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/6cb18ac9-4c0a-4081-8555-b8c427476ef4)

   </div>

3. Pindah ke direktori /app, menggunakan command

   `cd app/`

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/e59a160d-48d9-4b8f-85b5-9b7bbfb5319d)

    </div>

4. Lihat apa saja yang ada di direktori app dengan command

   `ls`

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/5c737c20-7366-43fb-a48f-66b0da3d7a9a)

   </div>

#### Building the App's Container Image

1. Buat file baru dengan nama "Dockerfile", dengan command berikut:

   `vi Dockerfile`

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/2b0bfe71-39dc-49f5-b5b2-c184dea77c0d)

2. Masukkan content berikut dan save dengan klik "shift : + w + q + !"

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/99b63c34-8f9f-4c02-89c9-e76a02eb5f47)

3. Build container image tadi menggunakan command berikut:

   `docker build -t docker-101 .`

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/763f6216-8059-4296-bfc7-bf267a54bec2)

#### Starting an App Container

1. Mulai containermu menggunakan command berikut:

   `docker run -dp 3000:3000 docker-101`

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/eed65c29-2926-472c-ba89-745c196ec98b)

2. Kemudian buka website dengan port 3000, maka akan tampil seperti berikut. Anda juga bisa menambahkan item sesuai yang diinginkan

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/85be5a01-0d9c-4382-b10e-4cf876a7d464)

#### **dockerLabs : Updating our App**

#### Updating our Source Code

1. Masuk ke direktori berikut ~/app/src/static/js/app.js menggunakan editor atau langsung dari command line

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/247f7771-763a-45cf-a162-a78f5e50b569)

   </div>

2. Build lagi menggunakan command yang sama

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/3e5b5526-7d74-47b9-b05c-916e70e100f3)

   </div>

3. Mulai container lagi dengan port yang sama (:3000), maka akan muncul error

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/ab744f69-5f0b-44fe-b632-6cb8b660868b)
   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/269e31b0-25cd-44e2-bd35-d0f749a839fb)

   </div>

#### Replacing our Old Container

1. Cek semua container yang berjalan menggunakan command berikut :

   `docker ps -a`

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/d1dcf340-8dc4-4669-8fdc-e4ed8f20dff9)

   </div>

2. Gunakan command docker stop untuk menghentikan container yang berjalan menggunakan command berikut:

   `docker stop <the-container-id>`

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/17145108-7193-43d7-a1fa-28386daf4b8c)

   </div>

3. setelah itu hapus container id tadi menggunakan command berikut:

   `docker rm <the-container-id>`

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/fd9d04ff-ba00-431c-90fc-eb66433cb0a7)

   </div>

4. Kemudian mulai lagi container menggunakan port 3000

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/05840934-2d0f-40d0-ae20-4ca2c6d10b97)

   </div>

5. Buka tab lagi menggunakan port 3000 yang baru saja di update. Lihat perubahan dari tulisan teks dibawah field.

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/df48a682-df03-43b6-8c8f-a05b4a009e46)

   </div>

#### **dockerLabs : Sharing our App**

#### Create a Repo

1. Pergi ke laman berikut dan login : https://hub.docker.com/

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/ea948349-cc90-4212-99cd-27f570472ca7)

    </div>

2. Kemudian klik create repository. Untuk nama repo gunakan nama "101-todo-app" dan buat menjadi "public"

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/84ba39fa-7f9a-48ac-94c5-5e57c27e95c2)

   </div>

3. Klik buat, maka akan muncul tampilan seperti berikut

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/00658b06-0a49-4194-a732-f7774707972a)

   </div>

#### Pushing our Image

1. Pada terminal, jalankan command berikut:

   `docker push YOUR-USER-NAME/101-todo-app:tagname`

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/49875027-1653-4709-bea0-e0cf71226e4b)

   </div>

2. Login ke docker menggunakan username dan passowrd

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/b2e1c9ff-4133-4eb7-a0eb-a01484e300c9)

   </div>

3. Gunakan `docker tag` untuk memberi nama baru, contoh seperti command berikut:

   `docker tag docker-101 YOUR-USER-NAME/101-todo-app`

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/65999f80-8064-4b39-9aa7-009572d941b4)

    </div>

4. Sekarang coba lagi push, menggunakan command berikut:

   `docker push YOUR-USER-NAME/101-todo-app`

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/66797159-8e16-4474-bedb-de47447d022a)

   </div>

#### Running our Image on a New Instance

1. Balik ke terminal dan run kembali container dengan port 3000, jika port 3000 sudah digunakan maka bisa distop dan dihapus terlebih dahulu.

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/f0f91f63-a8d3-4de8-919f-38d7e4328103)

   </div>

#### **dockerLabs : Persisting our DB**

#### The Container's Filesystem

1. Start container ubuntu yang akan membuat file bernama /data.txt

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/6192bc46-4812-4f7b-b7c5-ba11c7b66cc2)

   </div>

2. Melihat output untuk nomor acak dari container ubuntu

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/cc10d43c-9242-4ef3-94ab-4d5e50ebe1f6)

   </div>

3. Jalankan container dan liat tidak ada file yang sama

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/0c967da1-888b-465e-b8c7-e20d53e394e3)

   </div>

#### Persisting our Todo Data

1. Buat volume menggunakan command berikut:
   `docker volume create todo-db`

    <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/c1275813-8f05-442e-ba04-985f5de98de4)

    </div>

2. Start container menggunakan dengan spesifikasi jumlah volume di /etc/todos. Stop dan Remove jika port yang digunakan sama

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/0dc9b6ac-ffa9-414c-bdd5-8a42ef00af03)

   </div>

3. Lihat hasilnya pada port 3000

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/8d480de4-fd76-44d0-a23d-c879597e853d)

   </div>

4. Remove container dari Todo App menggunakan docker rm -f "container-id" kemudian buatlah container baru dengan cara yang sama seperti diatas.

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/8caab4b5-b51b-4c7b-bd8f-5ceb848f6036)

   </div>

5. coba tutup dan buka lagi browsernya maka data masih tersimpan.

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/8d480de4-fd76-44d0-a23d-c879597e853d)

   </div>

#### Diving into our Volume

1. Menginspeksi apa yang ada di volume todo-db

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/3bdaf282-16cb-4089-9866-20202efe35fa)

   </div>

#### **dockerLabs : Using Bind Mounts**

#### Starting a Dev-Mode Container

1.  Pastikan tidak ada port yang berjalan sama, jika ada stop dan hapus terlebih dahulu.

    <div align="center">

    ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/08dfa6ae-9f1e-454b-bcb1-878adaed9d8b)

     </div>

2.  Jalankan command berikut untuk memulai dan menginstall dependency yang diperlukan.

    <div align="center">

    ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/9c18134b-98a4-4423-b518-866c0c1f49b2)

    </div>

        ●	docker run: Perintah untuk menjalankan container baru.
        ●	-dp 3000:3000: Menjalankan container dalam mode terpisah (detached) di background, dan membuat pemetaan port dari port 3000 di host ke port 3000 di container.
        ●	-w /app: Mengatur direktori kerja (working directory) di dalam container ke /app.
        ●	node:10-alpine: Menggunakan image node:10-alpine sebagai dasar untuk container kita. Ini adalah image yang sudah memiliki Node.js dan Alpine Linux sebagai sistem operasinya.
        ●	sh -c "yarn install && yarn run dev": Memulai shell di dalam container menggunakan sh dan menjalankan perintah yarn install untuk menginstal semua dependensi, dan kemudian menjalankan perintah yarn run dev untuk memulai aplikasi dalam mode pengembangan menggunakan nodemon.

3.  Anda dapat melihat logs docker melalui container id dengan command berikut:

    `docker logs -f <container-id>`

    <div align="center">

    ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/ff346123-0a1a-402d-995b-8df337979a50)

    </div>

4.  Ubah baris berikut pada directory file berikut "src/static/js/app.js"

    <div align="center">

    ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/b2fe824f-c50d-4a36-8ce0-2df4bb48214c)

    </div>

5.  Refresh kembali halaman todo apps tadi dengan port 3000

    <div align="center">

    ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/7d0b173f-d138-4ff2-add6-f3384f968f25)

    </div>

#### **dockerLabs : Multi-Container Apps**

#### Starting MySQL

1. Buat jaringan pada aplikasi todo-app

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/8c26cc48-86bd-487a-a394-331d09b797c8)

   </div>

2. Kemudian jalankan mysql dengan command berikut:

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/5f8a0166-b978-4eb3-83b2-4a5998cb3674)

   </div>

3. Eksekusi docker berikut menggunakan mysql container yang tadi, dan masukkan passwordnya, yaitu "secret"

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/5f370f47-cd77-4ad7-936b-fa16ddae8f5a)

   </div>

#### Connecting to MySQL

1. Start container baru menggunakan nicokala/netshoot image dan pastikan dengan jaringan yang sama

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/153791aa-bd23-4147-acef-7c497f071fde)

   </div>

2. Gunakan perintah berikut untuk mencari alamat IP untuk nama host mysql

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/45a72642-4ddd-4893-b3ab-889a1293ff3d)

   </div>

#### Running our App with MySQL

1. Menetukan environment variables, serta menghubungkan container ke jaringan

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/099400e3-e626-49b0-81ac-b607eab9b352)

   </div>

2. jika menggunakan logs, dapat dilihat bahwa container berikut menggunakan database mysql

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/3ff73c19-74d3-43b6-a121-60539e31b790)

   </div>

3. Buka kembali browsermu dan masukkan beberapa dari item

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/e2d4d023-2d11-40b2-ad35-455995689746)

   </div>

4. Kembali ke terminal dan jalankan command berikut untuk melihat apakah item yang ditambahkan sudah masuk ke table database

   `docker exec -ti <mysql-container-id> mysql -p todos`

5. masuk ke dalam database, jalankan query berikut:

   `select * from todo_items;`

   <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/b5f4fb53-465b-42cf-9997-ee3348b6359b)

   </div>

#### **dockerLabs : Using Docker Compose**

#### Installing Docker Compose

1. Lihat versi dari docker compose menggunakan command berikut:

   `docker-compose version`

    <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/4f98b981-5670-4049-bc5b-cec476e0e695)

   </div>

#### Creating our Compose File

1. Buat file docker-compose.yml, meggunakan command berikut, save menggunakan tombol "shift : + w + q + !"

   `vi docker-compose.yml`

    <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/13f3f233-eaae-4c69-9b59-d651883c1cd4)

   </div>

#### Defining the App Service

1.  Definisikan layanan aplikasi dengan kode berikut:

        `docker run -dp 3000:3000 \

    -w /app -v $PWD:/app \
    --network todo-app \
    -e MYSQL_HOST=mysql \
    -e MYSQL_USER=root \
    -e MYSQL_PASSWORD=secret \
    -e MYSQL_DB=todos \
    node:10-alpine \
    sh -c "yarn install && yarn run dev"`

          <div align="center">

        ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/83e42a68-94e2-423a-89a5-a1bde2bff7d4)

         </div>

2.  Tambahkan baris kode mulai dari image, command, ports, working_dir, volumes, dan environment:

          version: "3.7"

          services:
          app:
             image: node:10-alpine
             command: sh -c "yarn install && yarn run dev"
             ports:
                - 3000:3000
             working_dir: /app
             volumes:
                - ./:/app
             environment:
                MYSQL_HOST: mysql
                MYSQL_USER: root
                MYSQL_PASSWORD: secret
                MYSQL_DB: todos

     <div align="center">

    ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/92a4dbff-1c33-4354-a27f-475b1a7f5453)

    </div>

#### Defining the MySQL Service

1.  Definisikan layanan aplikasi dengan kode berikut:

        `docker run -d \

    --network todo-app --network-alias mysql \
    -v todo-mysql-data:/var/lib/mysql \
    -e MYSQL_ROOT_PASSWORD=secret \
    -e MYSQL_DATABASE=todos \
    mysql:5.7`

          <div align="center">

        ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/4836fd75-e722-46ac-b0b4-78bdae267d05)

         </div>

2.  Tambahkan baris kode mulai dari mysql image:

          mysql:
             image: mysql:5.7

     <div align="center">

    ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/f8903ffd-41e1-423a-bb9e-acf987fc5db6)

    </div>

3.  Tambahkan baris kode mendifinisikan volume mapping:

          mysql:
             image: mysql:5.7
             volumes:
                - todo-mysql-data:/var/lib/mysq
          volumes:
             todo-mysql-data:

     <div align="center">

    ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/73c5f432-8c12-458c-9829-d3d5f52ffe96)

    </div>

4.  Tambahkan baris kode environment dari mysql:

          mysql:
             image: mysql:5.7
             volumes:
                - todo-mysql-data:/var/lib/mysql
             environment:
                MYSQL_ROOT_PASSWORD: secret
                MYSQL_DATABASE: todos

          volumes:
             todo-mysql-data:

     <div align="center">

    ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/4d1964b0-b263-4bca-895c-2fa599fa66dc)

    </div>

5.  Tambahkan baris kode mulai dari mysql image:

          mysql:
             image: mysql:5.7

     <div align="center">

    //image

    </div>

#### Running our Application Stack

1. Matikan dulu container yang berjalan pada ports :3000, kemudian jalankan application stack dengan command berikut:

   `docker-compose up -d`

    <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/fe48c0cc-d23c-4e68-ac06-370590d2268f)

   </div>

2. Melihat logs dari tiap service

    <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/e250ffba-856b-4119-810b-ea94ed12e7b4)

   </div>

#### Tearing it All Down

1. Saat ingin menghilangkan semuanya, gunakan command berikut, maka kontainer akan berhenti dan jaringan akan dihapus

   `docker-compose down`

    <div align="center">

   ![image](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/2ec04b37-a3f4-46c0-90a1-4014b8576c48)

   </div>

#### **dockerLabs : Image Building Best Practices**

#### Image Layering

1. Mengecek docker image history dari docker-101

    <div align="center">

   ![image](https://github.com/rifqirayita8/SysAdmin-3122500027/assets/114125588/ea2919ae-41ba-4b9d-b764-0da1826743ea)
   </div>
   Layer teratas adalah layer terbaru, dan urut ke bawah. Serta disini anda bisa melihat ukuran dari tiap layer containernya.

    <div align="center">

#### Layer Caching

1. Buka Dockerfile yang ada di folder app

    <div align="center">

   ![image](https://github.com/rifqirayita8/SysAdmin-3122500027/assets/114125588/9cc4bc6f-ec69-4e22-8009-1ab8858adc77)
   </div>

2. Coba build image baru

    <div align="center">

   ![image](https://github.com/rifqirayita8/SysAdmin-3122500027/assets/114125588/5847fa6d-f914-4d3d-863a-bc7114d65efc)
   </div>

   Bisa dilihat layer melakukan rebuild

3. Coba ubah title yang ada di src/static/index.html

    <div align="center">

   ![image](https://github.com/rifqirayita8/SysAdmin-3122500027/assets/114125588/65657712-c58e-4de6-bf59-138f1982a5e2)
   </div>

4. Build docker image lagi

    <div align="center">

   ![image](https://github.com/rifqirayita8/SysAdmin-3122500027/assets/114125588/77646528-de79-4f15-a5e5-5529f6afa469)

   </div>

   Bisa dilihat build image sangat cepat, karena step 1-4 menggunakan cache.
