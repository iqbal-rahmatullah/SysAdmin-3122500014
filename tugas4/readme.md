# Laporan Tugas 4 Workshop Administrasi Jaringan

![](https://lh7-us.googleusercontent.com/ovDdGMbqDQ9kyUjjya0tCt5O6-yEvpPuXK_GMdjqxAqvyJ-3wj7BUTllR8QKSluxWB89j9R5Hs8fQp9VYMbJvyG-sa1s9Wsa-K4SJLFhINGHmYvkXvRAR4aYyvLuMoZdyyFxd0uUIqe1tNNBzfec0Is)

Oleh :

Nama : Muhammad Iqbal Rahmatullah

Kelas : D3 IT A

NRP : 3122500014

Dosen Pengampu : Dr. Ferry Astika Saputra ST, M. Sc

##

# Tugas Baca tentang Ekosistem Internet (Materi sudah diunggah di Ethol). Tuliskan pendapatmu tentang bagaimana Internet bekerja (tugas pribadi)!

1.  Cara Internet Bekerja

Apa Itu Internet?

Internet adalah jaringan komputer global yang terhubung menggunakan protokol standar komunikasi, yaitu Transmission Control Protocol/Internet Protocol (TCP/IP). Jaringan ini memungkinkan komputer di seluruh dunia untuk berkomunikasi dan berbagi informasi satu sama lain.

Bagaimana Internet Bekerja?

Langkah 1: ISP dan Browser

Ketika Anda ingin mengakses internet, Anda memulai dengan perangkat seperti komputer atau smartphone yang terhubung ke Internet Service Provider (ISP). ISP Anda memberikan akses ke internet dan memungkinkan browser Anda untuk mengirim dan menerima data.

Langkah 2: DNS (Domain Name System)

Ketika Anda memasukkan alamat situs web, komputer Anda akan mencari alamat IP dari situs tersebut melalui DNS. DNS berfungsi seperti buku telepon internet yang menghubungkan nama domain dengan alamat IP.

Langkah 3: TCP (Transmission Control Protocol)

TCP mengatur bagaimana data dibagi menjadi paket yang lebih kecil untuk dikirim melalui internet. Ini juga memastikan bahwa paket-paket tersebut tiba dengan urutan yang benar dan tanpa kesalahan.

Langkah 4: HTTP (Hypertext Transfer Protocol)

HTTP adalah protokol yang digunakan oleh World Wide Web untuk mendefinisikan bagaimana pesan diformat dan ditransmisikan, serta apa tindakan yang harus dilakukan oleh server dan browser web dalam menanggapi berbagai perintah.

Langkah 5: Pertukaran Data

Setelah komputer Anda terhubung ke server, data dikirim kembali ke komputer Anda dan ditampilkan di browser sebagai halaman web. Proses ini terjadi sangat cepat berkat infrastruktur jaringan internet yang canggih.

Infrastruktur Fisik Internet

Internet terdiri dari kabel, serat optik, satelit, dan infrastruktur nirkabel yang menghubungkan komputer di seluruh dunia. Data dan informasi dikirimkan melalui jaringan ini dalam bentuk paket-paket kecil, memungkinkan komunikasi dan akses informasi dari mana saja dan kapan saja.

Manfaat Internet

Internet telah merevolusi cara kita berkomunikasi, belajar, bekerja, dan bermain. Dari browsing web, berkomunikasi dengan orang jarak jauh, mengunduh gambar dan video, hingga bermain jejaring sosial dan berbelanja online.

##

# Bagaimana Cara kerja dari iterative dan recursive dari DNS Query, ada 8 step kalo gasalah, dari PC anda! misal akses detik.com

![](https://lh7-us.googleusercontent.com/HcIHC8-93tc6jXUhW8Xc3aMCSLQ6T11HNpyQNde2sehzuvpqyUg3YYrOp0Vb_oHqXM6emsac7egbij5829PXmViCvXGyUqqMWqzByg0zAGuZceBv0EDtqq95irTGYAp8Q9s5SCbB_M9KWPkEohpPalc)

Source : [DNS Queries — Recursive and Iterative | by Geeky much! | Networks & Security | Medium](https://medium.com/networks-security/dns-queries-recursive-and-iterative-cdb73e290299)

Dari gambar dalam Proses Cara Kerja DNS secara Iterative dan Recursive berbeda, Berikut adalah cara kerja untuk tahapan DNS :

1.  Requesting host : Komputer client mengirimkan pengiriman ke local DNS server untuk mengakses web browser detik.com.
2.  Local DNS Server: Komputer klien mengirimkan permintaan ke Root DNS server untuk mengakses situs web detik.com.
3.  Root DNS Server: Jika server DNS lokal tidak memiliki catatan dalam cache-nya, maka akan mengirimkan permintaan ke server DNS akar (Root). Server DNS akar memberikan informasi tentang server DNS yang bertanggung jawab atas domain detik.com.
4.  TLD DNS Server: Server DNS akar merujuk server DNS lokal ke server DNS TLD (Top-Level Domain) yang sesuai dengan top-level domain dari detik.com, misalnya ".com".
5.  Server DNS yang Berwenang (Authoritative DNS): Server DNS TLD kemudian merujuk server DNS lokal ke server DNS yang memiliki informasi lengkap tentang domain detik.com.
6.  Respons ke Root DNS Server: Setelah mendapatkan informasi dari server DNS yang berwenang, server DNS TLD memberikan informasi tersebut kepada server DNS lokal, yang kemudian diteruskan kembali ke server DNS akar.
7.  Respons ke Server DNS Lokal: Server DNS akar meneruskan respons dari server DNS TLD kepada server DNS lokal.
8.  Respon ke Komputer Klien: Akhirnya, server DNS lokal memberikan respons kepada komputer klien yang awalnya membuat permintaan. Komputer klien menerima informasi yang diperlukan untuk mengakses situs web detik.com. Dengan demikian, proses DNS iteratif dan rekursif telah selesai, dan komputer klien dapat mengakses situs web yang diminta.

##

# Ikuti langkah-langkah instalasi DNS server dengan menggunakan aplikasi BIND9 pada Debian 12 anda [BIND9-debian wiki](<[https://wiki.debian.org/Bind9#Debian_Bookworm](https://wiki.debian.org/Bind9#Debian_Bookworm)>)

### Langkah - langkah :

1.  Melakukan install bind9 bind9-doc bind9-dnsutils → sudo apt install bind9 bind9-doc bind9-dnsutils

![](https://lh7-us.googleusercontent.com/xETvp1UD3CZJcrHJ-CgYiqJgNORER_SmpY8DQRQcZ8vlnN4jGbAiXN3cbMspIJP8d6PkLnB-rdIch46E2mIMPtFfbgduwfFMcpFFeErFY6wnZ_Orn2ygFSMdaOQHxtE_15DwuIJJnLN-fmJjgAme1SQ)

2.  Cek apakah sudah ada directory /etc/bind

![](https://lh7-us.googleusercontent.com/RRsumo59NaOeyWVR9y7hdSwb-y8icyue0LIop5DVZC3x5c3Hg1GsCpUZ5wINiQ3Ef-3Fi8iBZ8atTVDM2SKtAbyx1sugo7FpRJUas1O_A1fWX4LbGkBsr6KlamS1j-rcT_xKvPEq1q80eTOcJLBSl4s)

3.  Melakukan konfigurasi pada named.conf → sudo nano named.conf

![](https://lh7-us.googleusercontent.com/EOEvvbV5LOutmbiyY4cn1FqtOICwrO8eRUjBlf-600Ct8_5R4TB1XnDmps6a9NM6xBAu3EpoMxL0SYs-apYVzOL2bh1fsW-qmJ7nj3L7LDpU1gONsW5HcVCf8kqKVk3RJewasrzvI4tCE_BtLRHI3PY)

- Penjelasan konfigurasi

![](https://lh7-us.googleusercontent.com/8EOWSeEg36g_jvtKS3R4dhV1NSelsSNieZlTO5lnJA7oFDv4C8o0P0vZf-UEjLInmbyvb1Zo2WVCnEAI-S9GWlIuBXqV2MyaosSRq4UG1YSmGcTTSYNkZYj20Ddb9fqliFz7QKaQxCoUl_pUhYOIZVM)

Melakukan konfigurasi ACL ( Access List ), dinamakan internal,

![](https://lh7-us.googleusercontent.com/8Aks8uNge4-4amc2G-ryNllnVKKR2lpJXDTOuFH9ovfjAbmYVhkkMgrHd9GBUuXCv11Qnv93d9eJgz1ZNqwc82kTou9C6og_dN_MTyCH_8kwu50vnhQAG9nv6LNGx96R27dM3ksto1vLmvJe5ZzLGBk)

Melakukan Konfigurasikan saluran komunikasi untuk Administrative BIND9 dengan rdnc. Secara default, key ada di file rndc.key dan digunakan oleh rndc dan bind9 di localhost

4.  Melakukan konfigurasi pada named.conf.options → sudo nano named.conf.options

![](https://lh7-us.googleusercontent.com/lmXtrcjVIEhYkAciY9RtXRg_RnCsk1TF4nDxTJBgbBylS2yIlhmVu9I1Wg2aLhjB6REIq1rC5xOzRuuk057V_9cwwjWMuOEYqVSiCZj8zNfp5CQ1CA4t4BtzSTomiX71r-u-SA8TCoIz4NSM7Fyi1bI)

![](https://lh7-us.googleusercontent.com/iAUg5pSZBmJ2ieZgeCMKV4CQ_DEmbans-KE1BP-iI-8Pm0ygoFm0kUt6lXjC_gVkCeTLuO5mD2KUQRlA93VEeGwhLhY49PJEFz6WUk1EkVmXlp2Ql4vkBLxnKgDwU0cHlDwksyN38qUpMFxLzhEiqDs)

- Penjelasan konfigurasi :

![](https://lh7-us.googleusercontent.com/aZcXAtIJYOpDi-yLYXvmtIpaA_wVqHllyGPbHYCHvoCbqaZD9zNyy7gTOJYwrq16cN4QBr6U6i78fELBrToK0QHHDHO43Aicb5v0SCXcDe6W-UdKDs9fOt9GHC8K7vfjNwMDrRmaoscpeRinjuL2HJY)

Mengatur fowarder ke nameserver pens. Maka akan mengirim permintaan ke 202.9.85.3 dan 202.9.85.4 jika servernya tidak tahu cara mengatasinya.

![](https://lh7-us.googleusercontent.com/oEmi7WEuPc0yuxYe3nAk5RgaPxxOUc7ySsNyRJqt-l-MArDrpWFjixH7VYEjjDXaZPiz6c-pNfTRvDtMeI00jDzTw8LHlg1PuNLbKMVF3clZkbTysqKvSczkj9vS_sxLy6dHygjCXQewwQDzNvP5OIQ)

Melakukan konfigurasi tersebut mengikuti spesifikasi RFC1035. dalam konfigurasi BIND DNS server menetapkan bahwa server DNS tidak akan mengembalikan respons NXDOMAIN (No Such Domain) yang otentik saat mencari domain yang tidak ada dalam zona yang dikelola oleh server tersebut.

![](https://lh7-us.googleusercontent.com/iFOHKZXKR-e1h6WSgWExW_6m9G6_GPqpFJ26PCCzurlfExyWq2eHcBe3B5sl7y5YDTb5xhdcFlKa0yD0FgVifaRqm_qM7Qwl-teZh9zALNxkDlLoyIOp44lWa5mwwYaJ0hvAo1GKrxEH09I_z_wu7RI)

Mengganti listen on ke ip address kelompok 6 (192.168.6.10)

Melarang mentransfer informasi zone ke secondary DNS

Hanya menerima request dari internal network saja

Mengizinkan kueri rekursif ke host lokal

Membuat versi bind versi none

5.  Melakukan konfigurasi named.conf.local → nano named.conf.local

![](https://lh7-us.googleusercontent.com/ukGcRnfqrLdTKq9ax9MGM2VWvwF838lDsk1B3H5QJfQWM83sbMTCk_V6EO8rkPfuumEP8JvmBqd4R7xlIVv6FtXUR7xZHoWl72K2wB8TpxcRnQrl-7PYrmW0BeC112rzFD1IxWqKhkOQ21w1n0yhNos)

Penjelasan konfigurasi :

Mengkofigurasi zone file ke kelompok6.local dan mengganti lokasi zone file nya ke kelompok6.local

Mengkofigurasi invers zone yang memetakan dari ip ke nama

6.  Mengecek utilitas → sudo named-checkconf /etc/bind/named.conf, apakah ada error/issues

![](https://lh7-us.googleusercontent.com/etj7Ip7oIWZuRylIq_GEgmEVKq5osbaTptfCRReXj3id29g0BTWmHLgRBijDJzhNy4QNt4VyiD-Hu_WGi312okihP3uBeaB50198NpI269wCTe2x586U99MmUCbeiO5EhSCgnVvU8B0M-U5ssJvvjb8)

Tidak ada error/issues

7.  Berpindah ke file zone dan mengecek isi dari file zone

![](https://lh7-us.googleusercontent.com/Ye5SEFBNzJPrzvx_AOA2e2oTA1JdvILhtcrJdRM3FeVW1qWtLNhEAbO-vYyEqbwzswETFnp0c8pEyVlmLzhDAIfm73XYKKTBLJGGplrrIoR3Xb7Mc61OHHXnwfCdQnIKF5xHl-ymxrb8jHRsDWLWSfE)

8.  Buat file db sesuai yang sudah ada di konfigurasi zone file sebelumnya db.kelompok6.local → sudo nano db.kelompok6.local

![](https://lh7-us.googleusercontent.com/UYSkhCcTBG89qh5rVL4jZdIGt6lix1AwevDD01WoAEFVy-_ZqSC6bR_zKNquGv1Kh_hqbItxjQynA1ex8y1COx3sQNxJwmhZ1BJp1us4JAO4KHZXTTHgAEi4gsbks5WxYUs4iCWYJFEOs11kYffVbiw)

Penjelasan :

Mengkofigurasi SOA ( Start of Authority )

Serial dengan pola tahun, bulan, tanggal, urutan editing nya

Melakukan set NS memiliki internet address 192.168.6.10

Mengset www dan main memiliki CNAME ns

9.  Buat file db invers sesuai yang sudah ada di konfigurasi zone file sebelumnya db.kelompok6.local.inv → sudo nano db.kelompok6.local.inv

![](https://lh7-us.googleusercontent.com/QqJlhDKN81BNNek9_feMv07FdVqAvlrP_TW_e8Kz3etz0y5E5Hq5CkgeymMTU4uXYoKw0t3dsFI4x0u7mu2jCuR7fCxyEPos9A0Kye7-C3cijjx1bFxbURboiQvJ-AhakmpE62amxluhfJCRrnoejv0)

Penjelasan :

Mengatur internet pointer ke ns.kelompok6.local

10. Melakukan named-checkzone kelompok6.local db.kelompok6.local dan named -checkzone 6.168.192. inaddr-arpa db.kelompok6.local.inv

![](https://lh7-us.googleusercontent.com/PLjpL-36isEcKr7Fyhy7JETUEEBqM-ILbBtHMOfO4lhoVysKZd_-Ao5xN58r9Rls4qvH891wKJt5YsFzN8AIYUPo_eI6kjGt7jp0JOXEN62ToNcWE8LD4kBF0bDOXrzj1zlXxn9CWtKwOQL4KgBtX9U)

Penjelasan :

Memverifikasi bahwa file zona DNS Anda ditulis dengan benar sebelum menggunakannya pada server DNS BIND, membantu mencegah kesalahan konfigurasi yang mungkin menyebabkan masalah dalam resolusi DNS. Dan kedua pengecekan menghasilkan output OK.

11. Melakukan konfigurasi /etc/resolv.conf → sudo nano /etc/resolv.conf

![](https://lh7-us.googleusercontent.com/HqJlqvbsvXZnV40U4yuKsVgSwHzxN3Mrckcbr1z0_3QnpXfmFQYfzL_Jli9KvMejUzRLYWkKT3uEqxJjQgsxsf9rZLauFd0D6Bm0NpSL0teaRXMHXRyMyOLCX5hnRFmf-vrOAv2TLHF1C-SYWIDZJfQ)

resolv.conf adalah konfigurasi untuk sistem dns pada linux

Pada kasus ini ketika search kelompok6.local maka akan mencari ke nameserver utama 192.168.6.10, jika tidak merespons atau tidak ada maka akn mencari di alamat ip cadangannya yaitu 2 baris bawahnya.

12. Menjalankan service named → sudo systemctl restart named

![](https://lh7-us.googleusercontent.com/UQUeB7xwmK_S9zHuVhcr18ug4W__RPr2M_OGINZNlRttKUaJo6zWlM3Lcg3TGa6VImw_hWrs5wAFoPQt4bNoIXy9rKVGm5q8R4hHzuHHMCIzG3SwFYGy_AFjcEHKJZ6e27yuUC8jZtDpKscTbUC0hiY)

service named telah active(running)

13. Mengecek Port dari TCP/IP (:53) terbuka atau tidak → sudo netstat -ptlun

![](https://lh7-us.googleusercontent.com/5W4_1cePoJVTDTstr0Z9pCTnlNkF91eSnSVkFJ0OjhtVK2Y-s5JW1TeZ3Ha_jdUKGHpq7gJTwMVuRMXdvdVKFnxE54W8FVNRJjPo2zgRBkrddZszl8xuJgwXbP0zq7N-lt-cVbcODv0rTHMOUgn56hk)

14. Melakukan dig kelompok6.local

![](https://lh7-us.googleusercontent.com/W_HsyzQhUC7m3afY6zSDAkycho1Q37OXjOREL4HnaEUmJ7DVOSrTzMJhRo2QzxcbPWqzLmpYScDQkOuZdNssE8-KwwfnICzhhQnXolfsPiLNip-FSQbbjsU9j8H_uFiAR76EUzoedul3XGKCiqw_hmU)

Mencoba untuk menemukan informasi DNS terkait dengan domain kelompok6.local, seperti alamat IP yang terkait (jika domain tersebut adalah nama host) atau catatan lainnya yang terdaftar dalam server DNS yang diatur untuk domain tersebut.

15. Melakukan dig -x 192.168.6.10

![](https://lh7-us.googleusercontent.com/TpCECHwF3CCNLE3RCmk3NBrkHW-XzCkc_Ui_ZHmMjEWP3l2GPpqiHNqvefmtm_5brSUgmyNFO5PCnDYDRvIUsA17_ilPMK-YiVjeZRXajirXiTOCRZyFbHn9nFXPm2tzG7-6YAFOf-adEaGpIc64Dxc)

16. Melakukan nslookup kelompok6.local

![](https://lh7-us.googleusercontent.com/MiSAG72veWkacxZPsk9Ni14uJ7mwSDwtF7uy6Kx4whmjgiYUrc4MKCFgW9hBjFC8rTXveii2NLNkBlOp8RvLiIrA8EUSHwVLweG0LjEiOJUolIiAtn9_Qyjx0DRq8e8F6uF7ZM6JC9SddUh6CBS7Rpc)

##
