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

---

<div align="center">

**Architecture Web Server and Client**

![Architecture Web Server and Client](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/b0e5bebc-1c8e-49c0-889a-4530a150cecc)

</div>

Pada gambar arsitektur di atas merupakan cara kerja web server dan client secara umum dan monolit. Berikut adalah penjelasan dari Arsitektur web server dan client:

- User atau Pengguna: mengakses perangkat untuk meminta baik dari data maupun file yang nantinya ditampilkan di User Interface.
- Network atau Internet: berguna untuk menghubungkan perangkat dan server melalui aplikasi web permintaan (request) dikirim melalui internet ke server.
- REST API: Penghubung antara client dan server. Digunakan untuk menerima request dari klien, memproses, dan mengirimkan respon balik.
- Server: menerima permintaan dari REST API yang dikirim oleh client, memproses sesuai dengan logika aplikasi, dan menghasilkan respons yang nantinya dikirim kembali ke client melalui REST API.

5. Database: memberikan data yang sudah ada, menerima data, dan memperbarui data sesuai dengan permintaan dari klien.

<br>
<br>
<br>

<div align="center">

**Architecture Web Server and Client**

![Single Architecture Web Server and Client](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/0906fad1-8ae2-43f2-b6c7-20e30bde8d8f)

</div>

Pada Single Server Architecture of Web Server terdapat satu server yang bertanggung jawab untuk memproses dan menyajikan data dari konten web untuk client. Hal ini cocok untuk situs web kecil dengan traffic yang rendah. Namun disisi lain arsitektur diatas memiliki keterbatasan dalam hal skalabilitas dan toleransi kesalahan. Jika server down, seluruh layanan menjadi tidak tersedia. Berikut adalah penjelasan dari skema di atas:

- User -> DNS Server : meminta, mengetik atau mengklik domain yang ada pada browser yang digunakan.
- DNS Server -> User : Mencari alamat IP yang sesuai dengan nama domain, setelah ditemukan, mengirimkan respon balik dengan alamat IP web server yang sesuai.
- User -> Web Server : Ketika pengguna sudah menerima respon dari DNS Server yang berisi alamat IP dari web server, browser pengguna membuat permintaan HTTP langsung ke alamat IP yang diberikan, bukan ke nama domain.
- Web Server -> User : Web server memproses permintaan dari pengguna, mengambil data yang diperlukan, dan menghasilkan respons HTTP. Respon HTTP biasanya berupa file-file data atau informasi.

<br>
<br>
<br>

<div align="center">

**Architecture Web Server and Client**

![Multi-Tier Architecture Web Server and Client](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/06f6d1f0-4cca-46a1-9483-c5d9fce1b9f2)

</div>

Dalam Multi-Tier (Load-Balanced) Architecture, terdapat beberapa server yang digunakan untuk mendistribusikan beban kerja dan memastikan high availability. Pada arsitektur ini juga mendistribusikan permintaan masuk secara merata ke seluruh cluster server web. Setiap server dapat menyajikan konten web secara independen, dan jika salah satu server gagal, maka mengalihkan ke traffic pada server yang sehat, hal ini memastikan layanan tidak terganggu. Berikut adalah skema dari arsitektur di atas:

- Client (end users) : pengguna yang mengakses browser melalui berbagai perangkat, seperti handphone, laptop, tablet, dan pc
- Internet : jaringan global yang menghubungkan berbagai perangkat dan server di seluruh dunia.
- Load Balancer : memantau kesehatan server aplikasi dan mengalihkan lalu lintas dari server yang kelebihan beban ke server lain yang memiliki kapasitas lebih. Software load balancer dan hardware load balancer memiliki fungsi yang sama, yaitu mendistribusikan lalu lintas secara merata di antara beberapa server aplikasi.
- Application Server : server atau kumpulan server yang menjalankan aplikasi web atau layanan yang digunakan oleh pengguna. Server aplikasi menangani permintaan yang diterima dari klien, memprosesnya, dan mengirimkan respon kembali ke klien.

<br>
<br>
<br>

<div align="center">

**Architecture Web Server and Client**

![Working Architecture Web Server and Client](https://github.com/Ilhamroe/Workshop-Administrasi-Jaringan/assets/111882022/f09096c1-646c-498b-b5a8-920868557c6e)

</div>

Pada gambar Working of Web Server diatas terdapat dua skenario untuk melakukan permintaan dari Web Client ke Static Data Store atau Application Data Store. Dari gambar tersebut, jalur tergantung pada apakah itu permintaan untuk data statis atau membutuhkan pemrosesan lebih lanjut dari server aplikasi. Pada akhirnya, respons dikirimkan kembali ke pengguna melalui web server. Berikut merupakan proses dari kedua skenario di atas:

1. Web Client -> Web Server -> Static Data Store

   - Web Client : membuat permintaan HTTP ke aplikasi web melalui peramban mereka, seperti sebelumnya.
   - Web Server : menerima permintaan HTTP dari pengguna. Permintaan tersebut adalah untuk file statis, web server langsung mengambil file dari penyimpanan statis dan mengirimkannya kembali ke pengguna sebagai respons.
   - Static Data Store : menyediakan data statis yang nantinya diambil oleh web server .Penyimpanan data statis seperti file HTML, CSS, JavaScript, gambar, dan lain-lain.

2. Web Client -> Web Server -> Application Server (Web Container, Other Services) -> Application Data Store:
   - Web Client : membuat permintaan HTTP ke aplikasi web melalui peramban mereka, seperti sebelumnya.
   - Web Server : menerima permintaan HTTP dari pengguna. Permintaan tersebut membutuhkan pemrosesan lebih lanjut dari server aplikasi, web server meneruskannya ke server aplikasi.
   - Application Server : memproses data yang disimpan pada application server dan memeriksa data pada application data store. Ini juga bisa melibatkan layanan lain seperti layanan basis data, layanan cache, atau layanan lainnya.
   - Applicaton Data Store : permintaan membutuhkan akses atau manipulasi data, server aplikasi akan berinteraksi dengan penyimpanan data ini. Setelah pemrosesan selesai, respons dihasilkan dan dikirimkan kembali ke web server.
