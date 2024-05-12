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
