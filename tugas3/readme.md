# Laporan Tugas 3 Workshop Administrasi Jaringan

![](https://lh7-us.googleusercontent.com/ovDdGMbqDQ9kyUjjya0tCt5O6-yEvpPuXK_GMdjqxAqvyJ-3wj7BUTllR8QKSluxWB89j9R5Hs8fQp9VYMbJvyG-sa1s9Wsa-K4SJLFhINGHmYvkXvRAR4aYyvLuMoZdyyFxd0uUIqe1tNNBzfec0Is)

Oleh :

Nama : Muhammad Iqbal Rahmatullah
Kelas : D3 IT A
NRP : 3122500014

Dosen Pengampu : Dr. Ferry Astika Saputra ST, M. Sc
##

# Topologi

![](https://lh7-us.googleusercontent.com/vKJGXMLi1N5zm16xxtQm2Dt_w4ZXGCs6zg8_VUEK8oJV8U5cux8atmXUMvi4fQvuwQbMdWt5SpZHYy0Mj5DTRLfvPlxs-bi0bJnvjqThXBzzeYvtQ-EXFlr-7sbaU1reFmLxqe6RdubH7afEpFvOdHw)

Router 0

Network : 192.168.88.0

Fa0/0 : 192.168.88.254

gateway : 192.168.88.1

Router 1

Network : 192.168.88.0

Fa0/0 : 192.168.88.6

gateway : 192.168.88.1

Fa1/0 : 192.168.6.2

gateway : 192.168.6.1

Cluster 0 as Internet

Laptop 0

Network : 192.168.6.0

Fa0/0 : 192.168.6.2

gateway : 192.168.6.1

PC 1

Network : 192.168.6.0

Fa0/0 : 192.168.6.3

gateway : 192.168.6.1

PC 2

Network : 192.168.6.0

Fa0/0 : 192.168.6.4

gateway : 192.168.6.1

  

# WINBOX

1.  Buka Winbox. Cari MACAddress Anda pada box dibawah lalu klik 2x. Setelah nilai combobox “Connect To” berubah menjadi MAC Address Anda, tekan connect.
    

![](https://lh7-us.googleusercontent.com/9yjCTjrOUvCrg3bgtlchg7cYwiG-dnAocoVBjWnJo1dM5ktWxBQBl0uOgcj3OLjW1vrAIxfcSs6ciV_qRC61fKVDdNlz9pEoaVE8z0TKWce3U6ae0yP4O8bDN9dENbDdTcqc5FqF5upTOSB85eFbc4kyqeka5n05)

2.  Setelah terconnect dan masuk kedalam menu utama Winbox, akan keluar window seperti ini, pilih saja “remove configuration”.
    

![](https://lh7-us.googleusercontent.com/wk1yFFEH_sf1_vvqSchanienkdynt9Qv9OSaLIXNZ87gIJBOFzxLa2p6tbA9Qm0GRiXlq5vscVodrl3JbdM2D-WukhLE__fKdyhrycC_GfLWhvQZKNsc5fyxdXkJsddM4f_Y8gbidrF60hk8gPZlhoJACTKA2jhn)

  
  
  
  

3.  Kita akan membuat address baru. Disini saya menggunakan address 192.168.88.6 dengan netmask 255.255.255.0. Oktet terakhir dari address berbeda-beda sesuai dengan kelompok masing-masing.
    

![](https://lh7-us.googleusercontent.com/3_Lz1atw7eZWY3Fri3yXiRTl2lEEyGn5k9yaUqtsxzwc0ZQKNSeUjThgJ9q3PxItzkpm5Z9vrESJ4Lq-zDrqv2mSsloQ2tSmyxAvPGxy-8FQBpmWCnLuyF4xmC3BmZJEeWZFEWNPTWmbSq16fsjP3988dC2-GMg_)

4.  Coba ping ke IP yang telah di-set tadi untuk memastikan bahwa kita sudah menyettingnya dengan benar. Jika terdapat balasan dan tidak ada packet loss berarti sudah berhasil terhubung.
    

![](https://lh7-us.googleusercontent.com/a9c78IQAk6lAkEbQvwqwgOE2vo7pTRl298MInjMZosj8hWERQYgsHDmduR0_O5PQ7zlwnIHs7eOBabsXkkF-EdEM1clSDGUGlVYll4Ghg4k2844s04UrfvkFTnLWbcvpN9NmsL4b45MG2DKDtehpI-Je56oxkXwY)

  
  
  
  
  
  

5.  Disini kita akan membuat bridge. Bridge berfungsi untuk menghubungkan dua atau lebih segmen jaringan. Langsung saja kita pilih OK.
    

![](https://lh7-us.googleusercontent.com/hg2bXkP1Eq1RbdZohKE0Xn5Po6NKjb8DHsV_HG-Plw6f3eE3mbM5XoEI11Zx-gaGb4bEEQ3emUcGI2fRPbbzhbnwEAZ4NW9Zfxz8dFK-RxVNXEJ4iINcCfUPAVCuzoqUHVBgAAL2ZjbxTh3FS1tM-KL4tUWLqN4P)

6.  Setelah membuat bridge, buka tab port pada bridge tersebut dan tambahkan interface dari ether2 sampai ether5.
    

![](https://lh7-us.googleusercontent.com/II_Lp-kJnuNI6X-zTugZ6rUQVkYGfp5okemQjPQXUY0UEuKI__2AMmCL0A-azYBOmXHLl4US7ElpQvHvZwMKv5cfjYleJ8l4EDWBdJoUNmTtDBuUBpMYVWMJp8aQlt1YFbSbsb0UZz8YeJ4pPI7WG5HQ-VaEsqFU)

  
  
  
  
  

7.  Selanjutnya kita akan menambah address pada interface ether2 dengan IP 192.168.6.1 dengan netmask 255.255.255.0.
    

![](https://lh7-us.googleusercontent.com/i8El0oX4tA_vK2E9u5AU6cuVsaKOKQfeXS4niAVdn0ExucPNC1pVUmUzV1M-WkrL_u-SlJTXKuWA2TwjhcvGWnWu2UCrTvG7k1ELO28JbWD6zdqWANbX32kG2g8mMwB2jWexHhjUMC4Ttus6719Lun4wzaDK4oVA)

![](https://lh7-us.googleusercontent.com/3V0R5TTA8celPcZe_p1m2svLImd_YOAdaHpdGqC9rdN-hA7Nu3H-YZWnpGbG11SLgzBcibPanAza1kVwsYdTBCnwkGmznC8WdkIoZAW_pe4jAGNKX2wwuW177OtXABaaaD-ktv9vJYrF7woQciWVtaSCMCazXfDY)
 

8.  Buatlah route untuk menghubungkan antar interface yang telah dibuat. Disini kita akan menggunakan destination 0.0.0.0/0 yang menandakan default route & gateway atau rute yang mengarah kepada seluruh jaringan yang di luar jaringan kita.
    

![](https://lh7-us.googleusercontent.com/Ja5B4bRXrIpsgrPVm2bGyh74pnxUibJkO6443q8WwKmY2yxuHXWZwFB1kuqmgN21oCS1MDnkeJD98WyhZLTzkCPjH5PakstGwoOpEf9acQW59zwx_6ANSeHZA7vtmj6jQhRGJidq_efHK8FUo9I--C2On58TYLTl)

9.  Membuat DHCP server di interface bridge_1 dengan IP, network, gateway, relay, dan DNS seperti berikut. Saya atur DHCP di jaringan 192.168.6.0/24
    

![](https://lh7-us.googleusercontent.com/JELEtFp1AywwztQEZ790x1b59v3u_L-sP3zbTTBQonq32X5p7tkOWyu59sAjFH9CcC5KFjX-C6-6PmsaKd5E43xNVTNLu4NedzzuQTTW6eAURtxRxbxhDeMCXRRXylQisnhafNF6_10zXKKbL6oUzI26m6qPKVQZ)

![](https://lh7-us.googleusercontent.com/A_iuoj3yS5u26uhPowx68QpRZMRTVNMHW5tGyXLUw3mF_Wul52oS94CjzZpult1XszKu1PNHVB5e2bRoV8avCBCrhUoRaEcRSeH-juoOQZvWqnEvI2wUoKVPCQzliYxhAQ4XvU4g3uSpm4NKk2t9PsK38rtrxqk9)

![](https://lh7-us.googleusercontent.com/3tUtGQCZbNNQmoRtQLFZfoJPPfmpvIubXL636TEktfou4MVGzuE4klrnNjJ2xLiX_oApgbdM6z91pzQCTqwQALXtG26UZedJbEUmLjuvWNXvXcF9aUuMagfiMP00x3RP7QGzw_B5CP1sEOtf5xzc_1Hxl7hDzgEc)

![](https://lh7-us.googleusercontent.com/1mxIFytmK3MqSi5RBHy6tbPGSufOyF2C1ztQkYHdmPhyhWzHd2cSVjTIR0u0fOUuhEk5jBi2nUsNRsir3dJjvkoySRIQr-YLa6frJGsOFh8tEAxjEcb1rOpepS0rr6O9Y25VvXyKfjYB8MBilZ7rJ48R9k1yKDxV)

  

![](https://lh7-us.googleusercontent.com/YIpx7lf_d2J-KNTYrkYOIoVQRimxJ9jVj2R4YtyEKUrO9WcB4YsDakKmpmYkkdD5_wh8swTX8w1Sy_igLqFIoc3p3ndodmOvkuSXJcWU1Qlmv1aTQbqnAM94tXr_yQUlrtmraRoAE3d09EJKjb_Ue-sVEBeNybq3)

10.  Tampilan ketika DHCP telah selesai.
    

![](https://lh7-us.googleusercontent.com/pDOBAlIricls5LShM9Rmzwe4zKr3OUR8jynXGizZ8aG58WRMuCWIbRgFPSkHEpB-JcNGBHykOfuEZOTKJvvlLEvzwxuP7Qwb5bUoHHeLjHUkj5PTIRWk1tvdb3sZcUzdV7NSLUvDlB8NIrV3wbdABhr1x8UBBoZw)

11.  Buatlah NAT dengan source sama dengan jaringan yang tadi (192.168.6.0/24) dengan destination ke seluruh jaringan di luar jaringan sendiri (0.0.0.0/0).
    

![](https://lh7-us.googleusercontent.com/wQ-QnIHfkcIyywFmDIx7NV9jXd00YC3UznHPFDyzcO4xAezi1bce7U6UU0r5ty8Nnw4VBPx_HSxOVrYmPWOSCrG5khi6K8XTr-iXaX1h453aWq-qzUpmo03iNJWthpA9OJD7oHyWCyBOF7Lk-E3dXT4OTJ71faUu)

12.  Atur NAT menjadi masquerade (NAT overload) agar beberapa devices / interfaces dapat menggunakan satu IP yang sama untuk berkomunikasi ke jaringan luar.
    

![](https://lh7-us.googleusercontent.com/CBl3zSUtSfOF1t9JI1D4XU81_xZ1Kd8iBqxRkcIR4lEkuo1cDbaLjuPJcoANGov1oMhvqQRri7FHtALz-irxunHuJHuKVR8iuHG2F8npjVLJ6CR69rsW4QnFrumpIotja2WR-D3smz79g4LCYUInbRM-QNXjCFZy)

  

# 8.6 Cleaning The System

Meskipun kapasitas hard disk meningkat drastis selama beberapa tahun terakhir, Anda mungkin memerlukan ruang kosong. Beberapa skrip mengotomatiskan proses pembersihan disk, namun harus saya akui bahwa saya lebih suka memeriksa sebelum menggunakan perintah rm (singkatan dari delete.chap.11.2).

## 8.6.1 Disk Space Information

Hal pertama yang harus dilakukan tentu saja adalah mengetahui ruang yang terpakai di disk Anda. Beberapa alat tersedia untuk Anda, dimulai dengan terminal Anda:

– Ruang disk dalam mode terminal –

Ringkasan penggunaan ruang disk untuk setiap titik pemasangan sistem (disk dan partisi) dengan perintah df:

  

![](https://lh7-us.googleusercontent.com/07beeg3NUcQtze9Pop-Q3waIzfyOpvoShWtux7MaoD8E1Gfoim2EU_E8Z36Boe0NJ7LrQ0Drb0CNIv49WHhFCeL8yH-Bnr5Y_u6ggfWxxR1nf8J8btTi_B_daxdj-DAz3yjUYV61FFVn_-k9Lmv5oJU)

– Buat daftar perbendaharaan Anda, diurutkan berdasarkan ukuran yang diperkecil –

Lihat direktori Anda dalam jumlah besar berkat du dan sortir (satuannya adalah megabite):

![](https://lh7-us.googleusercontent.com/sHUdmj6zdezI9G8qPhpo_ZsPvc62H3ZQyY8IRfaRCFxBCIxsWVzL9SYNmAjJwDlPlxFTTwaTCPrYzxQd-occQ_qJnBJyYhcAXhA65MOVY4IR8kjzpN2aiTnBwgOfXFudsEuwQ8Wh7rqNsOiWL_4hRk8)

- NCDU -

Penganalisis ruang disk dalam mode konsol. Untuk meluncurkannya, cukup ketik “ncdu” di terminal Anda. Untuk menginstal perangkat lunak ini (dalam mode administrator):

![](https://lh7-us.googleusercontent.com/Q4U4y_PUP9AJIZDwJXlrhNzkgh3c7miTwB7ardtjnNUghZUBpCAQnVAng7naaUbJq79zJzUJhBlArcmT4qAJI-258vVec37QCLXHFjyfNiwlZ5IALM0PtYIE-LlaCA7AlB91QklML26pEE7mEEZYWOo)

![](https://lh7-us.googleusercontent.com/eieCvp5i1gtd1YY7Synd1knMkNJv4VTchMVdVQaCuweRWAhHwOE8uINiAcDbQAkDnC_zwmUsrcrqHw4FQCrPXfsRFkIXqihXT8-dX6g-6vvi9H_pbGViCO2ik0me1xnV1GiB070DTUC8BQ8_tv3iL7E)

- Baobab -

Penganalisis ruang disk dalam mode grafis, terintegrasi di Gnome tetapi tersedia di lingkungan lain dengan:

![](https://lh7-us.googleusercontent.com/1BGdbYcyXlXMES-ego_0m0FbrEUrKTXiuVSo5QQhBDHhaiOevIHb3o2NoVMtF23QnRoVTeHBlFrNa2MmIoMHQg79WUujHk6JHrRKwSdwwAaYDDkVhskXX1uHd_9cdIgn0U4EyV-nALvA5_c_2HcA23g)

![](https://lh7-us.googleusercontent.com/L-CJ7B6ehMkT-HrElQ_9QdR-Ev4_RW4kOdK4HV_5HheBUav9HXpGq207HSVZerUFZdIou2N1mv_NOISXFC6JHNutQ2qZna47hXEpHZl_hP0fkXiDIwC1ICb0PkPxQz5fLa32iCAk8r4qguHqnpJOEks)

  
## 8.6.2 Cleaning the Packages

Apt/aptitude/dpkg adalah manajer paket Debian yang biasa. Saat Anda menginstal sebuah paket, file sumber arsip/debnya disimpan di sistem Anda (dalam folder /var/cache/apt/archives/) untuk memungkinkan kemungkinan instalasi ulang tanpa koneksi Internet. Untuk membersihkan “apt cache” gunakan perintah sederhana dalam mode administrator (bab.3.8.3):

![](https://lh7-us.googleusercontent.com/37nMJA_BimMtWLDe2OVbIM6JhWNVuK307A_Ifzzyynyh0gqMGXDctDWhdspNQFDxwbVYkhhccY8vBo-SoicdT6ARfeCkn2NRFmM-TLoPvD3fASn8Olhi5DwAQJPFtceDXNG7PxfTe7uc1HMDRQvbFho)

Setelah cache dari paket yang diinstal dibersihkan, Anda juga dapat menghapus paket yang tidak berguna dari sistem Anda, serta file konfigurasi. Peringatan! Ingatlah untuk memeriksa dengan cermat daftar paket yang direncanakan untuk dihapus, sebelum menerima operasi:![](https://lh7-us.googleusercontent.com/37nMJA_BimMtWLDe2OVbIM6JhWNVuK307A_Ifzzyynyh0gqMGXDctDWhdspNQFDxwbVYkhhccY8vBo-SoicdT6ARfeCkn2NRFmM-TLoPvD3fASn8Olhi5DwAQJPFtceDXNG7PxfTe7uc1HMDRQvbFho)

Jika Anda telah mengupgrade sistem Anda, ada kemungkinan beberapa paket tidak lagi tersedia di repositori baru: paket tersebut sudah usang. Untuk membuat daftar dan menghapus paket-paket ini, gunakan apt dan ingatlah untuk memeriksa dengan cermat daftar paket yang direncanakan untuk dihapus:

![](https://lh7-us.googleusercontent.com/37nMJA_BimMtWLDe2OVbIM6JhWNVuK307A_Ifzzyynyh0gqMGXDctDWhdspNQFDxwbVYkhhccY8vBo-SoicdT6ARfeCkn2NRFmM-TLoPvD3fASn8Olhi5DwAQJPFtceDXNG7PxfTe7uc1HMDRQvbFho)

Terakhir, untuk membuat daftar dan membersihkan file konfigurasi yang tetap ada meskipun aplikasi telah dihapus, Anda dapat menggunakan perintah ini

![](https://lh7-us.googleusercontent.com/xzS03my0AsTTLuPVB6R45wjoPMbFO6JaXTVXR6DAeoYouwlFgprROAQ4TE2ETBbe7IA0JggAYAqkMxm4sbXYPgU5zVg1qGWG2tGoWtqHYM5Ijviw_cnYgaA5oxtq9WYvLh0f6HhFBZFIZV-N4zE_QwE)

Bagi yang lebih maniak, Anda dapat menginstal alat deborphan yang mencantumkan paket-paket yatim piatu di sistem Anda: paket-paket yang tidak bergantung pada paket lain. Peringatan! Ingatlah untuk memeriksa dengan cermat daftar paket yang direncanakan untuk dihapus, sebelum menerima operasi.

![](https://lh7-us.googleusercontent.com/pm9bnPDXF0sTXchfHbCcNXbKYQ4RCayKzCrVjop1xNmzs3tESsa1JfwBt9Koi2_t9zEQiKBZecYLmZX3XB8FDd3lLtFH9S8KpW-RxW0EMmMXcW7ewHKZnGSrcOGc7pnU0iPOPeFnbaQVoZP8tAcVmgY)

![](https://lh7-us.googleusercontent.com/VCKDBUe_Z9nDa9dXiXs5otGh1S-CRMCRJBYaoE74qUn15TgBMn0CXrEZ_n2Aic4eo6w_-H12ogaB8CmoCrAWWIbsvXqE8lk1Wagm1VhNCpxvVxUHQ-Iawf7oNWZljXsg6E1UQqaVoImJ1fRh00vh36Y)

## 8.6.3 Emptying the Trash Bins

Tiga tempat sampah (atau keranjang sampah) yang berbeda harus dipertimbangkan:

Keranjang sampah pengguna : ~/.local/share/Trash/ . Anda dapat mengosongkannya dengan pengelola file sistem (bab.3.6.2.5), atau dengan terminal:

![](https://lh7-us.googleusercontent.com/N0KWvs-L9G1pofFEwvzAJgYn5cGNyZzi5VLuFszlqVQqgdtCLeBbtX30ij6_PuoR70WPB9g660EqRZKyzvt5W45cNqPp4yGUje5ld05ByZCVXqHYZhqc3rzf-L_c86ojIiWL57tUhFr_B3lv5WwjG5U)

Keranjang sampah administrator : /root/.local/share/Trash/ . Untuk mengosongkannya dengan cara yang benar, gunakan terminal dalam mode administrator:

![](https://lh7-us.googleusercontent.com/N0KWvs-L9G1pofFEwvzAJgYn5cGNyZzi5VLuFszlqVQqgdtCLeBbtX30ij6_PuoR70WPB9g660EqRZKyzvt5W45cNqPp4yGUje5ld05ByZCVXqHYZhqc3rzf-L_c86ojIiWL57tUhFr_B3lv5WwjG5U)

Keranjang sampah eksternal : terletak di disk eksternal Anda, biasanya diberi nama '/media/y- our_id/your_disk/.Trash_1000', dimana your_id sesuai dengan nama login Anda.

## 8.6.4 Purging application caches

Beberapa aplikasi menggunakan folder “cache”, tempat mereka menyimpan gambar, video, dan informasi lain-lain agar dapat berjalan lebih cepat. Biasanya data ini tidak memakan terlalu banyak ruang disk, namun jika (menggunakan alat yang dijelaskan di atas) Anda mendeteksi bahwa suatu folder menjadi terlalu tebal, jangan ragu untuk menghapusnya.

![](https://lh7-us.googleusercontent.com/N0KWvs-L9G1pofFEwvzAJgYn5cGNyZzi5VLuFszlqVQqgdtCLeBbtX30ij6_PuoR70WPB9g660EqRZKyzvt5W45cNqPp4yGUje5ld05ByZCVXqHYZhqc3rzf-L_c86ojIiWL57tUhFr_B3lv5WwjG5U)

Setiap aplikasi mempunyai caranya sendiri untuk mengelola cache-nya sendiri: beberapa membersihkannya secara sistematis ketika ditutup, yang lain menyimpan datanya di folder /tmp, yang akan dibersihkan selama sesi logout, yang lain menyimpan semua informasinya dalam folder tertentu.

Untuk Firefox, misalnya, Anda dapat membersihkan cache dari menu preferensi, dan bahkan mengotomatiskan tindakan ini setiap kali aplikasi ditutup.

## 8.6.5 Purging the thumbnails

Setiap kali Anda membuka folder yang berisi gambar atau video, thumbnail dibuat untuk mewakili file grafik tersebut. Thumbnail ini disimpan dalam folder tertentu untuk digunakan kembali, daripada dipaksa untuk menghitung ulang setiap kali Anda mengakses file semacam ini.

Masalah muncul ketika Anda menghapus file grafik, karena thumbnail-nya disimpan di sistem, dan ini menyebabkan sejumlah ruang disk terbuang untuk menyimpan thumbnail yang sudah usang.

Untuk membersihkannya, cukup dengan menghapus folder terkait:

![](https://lh7-us.googleusercontent.com/N0KWvs-L9G1pofFEwvzAJgYn5cGNyZzi5VLuFszlqVQqgdtCLeBbtX30ij6_PuoR70WPB9g660EqRZKyzvt5W45cNqPp4yGUje5ld05ByZCVXqHYZhqc3rzf-L_c86ojIiWL57tUhFr_B3lv5WwjG5U)

Folder ini akan dibuat lagi, pada saat sistem perlu menyimpan thumbnail yang baru dibuat.

## 8.7 Installing external “.deb” packages

Debian GNU / Linux menggunakan repository package untuk memanage software security dari sistem Anda. Tetapi itu membutuhkan package external dari format .deb. “Deb” adalah singkatan dari “debian”, mother company-nya. Format .deb adalah format terkompresi, cara kerjanya sama seperti .zip yang lumrah ditemui di PC kalian.

## 8.7.1 Installation in graphic mode with GDebi

![](https://lh7-us.googleusercontent.com/FrU6_j8VDQsIyC5HCg_eHudr6JKIblc8MOxondYSC1fDlz86ZLCRFHjnimz-sO_vhqRqJjRQT-yJGPKPJhRNvtGT1jSyE7oaQ_FoqEUnEh-G-UIDjLYGCAegUXUhxypbDUQTMxPwI9UGcy4mGkaT44o)

Gdebi аdalаh sebuah aplikаsi yang bisa digunakаn untuk menginstаll/meng-upgrade softwаre di linux. Gdebi akan menginstаll file .deb dengan memperhatikan dependensi. Gdebi аdаlah аplikasi untuk membacа file .deb dan menginstalnya. Software ini lebih bаik dаripadа DPKG karena dаpat menangani dependensi.

![](https://lh7-us.googleusercontent.com/dYOY_hq2pz1hMk7CpvJKpfwDkdGBLKWQwUZw5WTQTPk0IwRNhGBuUh3XI57V7HzioHBvSEqfBHEGH0fzXmqWb1uJxYY4zaYOF_0_lVDX2A3rZSow7G_qsRZ72u8Vtws7nqBVxpDsrCcYxyIM9wlo-PY)

  
## 8.7.2 Installation in terminal mode with DPKG

Perintah dpkg merupakan utility berbasi Debian Package Management System yang berfungsi untuk menginstal, meremove, dan memperoleh informasi dari setiap paket.

-   Menginstall paket dengan dpkg
    

![](https://lh7-us.googleusercontent.com/MlHd8ckO_i_oGwMQB_lhaQZg5OrqFqLi8mfrlIj4lAhTxw0zPTbqO1Re0FcD2_gtEPdWfqtSMPC5RAlZPSiL5y5w7Nekac2VktTzSKYxeleC5qxNFvnyKXlImM0cyB3HtlzlJrTd_Ua7luh0fel68Uc)
  

-   Menginstall dependencies kalau ada yang missing
    

![](https://lh7-us.googleusercontent.com/QR_nPjBf0CciTdXTqpgonz-0n8RAWY1C-DtD9Ewu9pVJil8S2FlHD70fVkgoYoYPKzbc9hi_PnKHdea_jec3_Ca1NVUwGjQB9pDwldr9QH23Jko2i2UJ2_xNGYReLdSBymohwi89aodqMDxTuKCf5fw)

-   Relaunch setelah menginstall dependencies
    

![](https://lh7-us.googleusercontent.com/MlHd8ckO_i_oGwMQB_lhaQZg5OrqFqLi8mfrlIj4lAhTxw0zPTbqO1Re0FcD2_gtEPdWfqtSMPC5RAlZPSiL5y5w7Nekac2VktTzSKYxeleC5qxNFvnyKXlImM0cyB3HtlzlJrTd_Ua7luh0fel68Uc)

-   Remove package eksternal
    

![](https://lh7-us.googleusercontent.com/wBYTflI6GMTs8OzfLuQdKXHK-1xV9OQ6P0CBnJwaSLyMSc8lDFJ_doh_BforvPpLwMtUK2gR9e_bkxQdvtnfmxn36OboLLuEV_v3qXYprcPn2BSkPNYMKCAKxhtBDcYzb_FSeCvSW5OCw493Ezi83cg)


