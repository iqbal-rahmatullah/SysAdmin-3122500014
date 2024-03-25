# Laporan Tugas 4 Workshop Administrasi Jaringan

![](https://lh7-us.googleusercontent.com/ovDdGMbqDQ9kyUjjya0tCt5O6-yEvpPuXK_GMdjqxAqvyJ-3wj7BUTllR8QKSluxWB89j9R5Hs8fQp9VYMbJvyG-sa1s9Wsa-K4SJLFhINGHmYvkXvRAR4aYyvLuMoZdyyFxd0uUIqe1tNNBzfec0Is)

Oleh :

Nama : Muhammad Iqbal Rahmatullah

Kelas : D3 IT A

NRP : 3122500014

Dosen Pengampu : Dr. Ferry Astika Saputra ST, M. Sc

##

# Tugas Baca tentang Ekosistem Internet (Materi sudah diunggah di Ethol). Tuliskan pendapatmu tentang bagaimana Internet bekerja (tugas pribadi)!

#### Apa Itu Internet?

Internet adalah jaringan komputer global yang terhubung menggunakan protokol standar komunikasi, yaitu Transmission Control Protocol/Internet Protocol (TCP/IP). Jaringan ini memungkinkan komputer di seluruh dunia untuk berkomunikasi dan berbagi informasi satu sama lain.

#### Bagaimana Internet Bekerja?

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

#### Infrastruktur Fisik Internet

Internet terdiri dari kabel, serat optik, satelit, dan infrastruktur nirkabel yang menghubungkan komputer di seluruh dunia. Data dan informasi dikirimkan melalui jaringan ini dalam bentuk paket-paket kecil, memungkinkan komunikasi dan akses informasi dari mana saja dan kapan saja.

##### Pengembangan Standar Terbuka (Open Standards Development)

Standar terbuka memungkinkan interoperabilitas antar sistem yang berbeda dan memastikan bahwa teknologi dapat berkembang tanpa terhalang oleh batasan vendor atau platform tertentu.

##### Penamaan dan Penugasan Alamat (Naming and Addressing)

Organisasi seperti IANA (Internet Assigned Numbers Authority) dan ICANN (Internet Corporation for Assigned Names and Numbers) memainkan peran penting dalam penugasan alamat IP dan pengelolaan domain tingkat atas.

##### Pengembangan Kebijakan (Policy Development)

Kebijakan lokal, nasional, regional, dan global dibentuk untuk mengatur berbagai aspek internet, termasuk privasi, keamanan, dan akses.

##### Pendidikan dan Pengembangan Kapasitas (Education and Capacity Building)

Inisiatif pendidikan dan pelatihan diperlukan untuk membangun keterampilan dan pengetahuan yang diperlukan untuk mendukung pertumbuhan dan inovasi dalam ekosistem internet.

##### Pengguna (Users)

Pengguna internet meliputi individu, bisnis, pemerintah, dan organisasi lainnya yang semuanya terhubung dan berinteraksi dalam ekosistem ini.

##### Layanan dan Operasi Bersama (Shared Global Services and Operations)

Layanan bersama seperti DNS (Domain Name System) dan infrastruktur jaringan memungkinkan pertukaran data yang efisien dan stabil di seluruh dunia.

##### Pengembangan Kebijakan Multilateral (Multilateral Policy Development)

Institusi multilateral dan organisasi seperti Internet Society berkontribusi pada pembentukan kebijakan yang mempengaruhi internet secara global.

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

![](https://lh7-us.googleusercontent.com/I_-OzrX74gD4EV9JdJe9pFFUOoTg8TakHjQITVe5Q7ya19pJontwK5FI6_gwlVTEsma5t8whB9lgvUK9JziE0EFiXZ85VsxfQcauaduFICws1K1MAxipjKm7IA1QRNlo48nZJ1nO4sq6H3kGfj9PWYE)

2.  Cek apakah sudah ada directory /etc/bind

![](https://lh7-us.googleusercontent.com/ML6TIo0qyxG80wvAJVHwR8TnRExjJnmlrnHMTpuHbotUnNnuzz7m0XWtyD2Pd4_FnU0RNDIVBZyg0fv4_G0V7X3F6hYn83gBR3AtBvtRFkLrB05J4t2BB7mrhBuEkcPOoXmxTBMtEAAj0-2zQfvNT1w)

3.  Melakukan konfigurasi pada named.conf → sudo nano named.conf

![](https://lh7-us.googleusercontent.com/KNWlPGolwN-0ge5DquAQe0As5VIS8tmuwh439kZJIpahWJlYORUSdWkukUPmbVsLL4hi53XpDKDqcnabIfM8_GaX6nDGtUurxnh1-OfgO5ZbVH0JNqabk7ELmyRt7jO2ngiHWl9FQQFT2UtAfIX4pRI)

- Penjelasan konfigurasi

![](https://lh7-us.googleusercontent.com/kXuqh2Kk0zr__Fba1pjVSpFGuArtHaAPuAyOtxo5RHRLNrx_D6TvhmWD8gNUOzze0euwD4Xnr-HxLXQFgXin9xGpNxr1y3Ob0Xhs588g0LhzD_NkhYj7MCgj9FCsw5OXv3DjVRSl8kwaaO4M_p7J6ac)

Melakukan konfigurasi ACL ( Access List ), dinamakan internal,

![](https://lh7-us.googleusercontent.com/DX6KHTXuNvcOSrlcjgp1UzfVyeEVaJd4lEo5ZnHymWV-kx8SBBofamy88f2FW594Wc_DY7osxBxIUfAjDNAx7EPfeKeL1YJJ1U7VAgKV7pUm_NirJETiYI7TEASP1bNc_J7Zq54nwh_KD562O_7giJI)

Melakukan Konfigurasikan saluran komunikasi untuk Administrative BIND9 dengan rdnc. Secara default, key ada di file rndc.key dan digunakan oleh rndc dan bind9 di localhost

4.  Melakukan konfigurasi pada named.conf.options → sudo nano named.conf.options

![](https://lh7-us.googleusercontent.com/3pJ5pgLtDWEw0sdfPZ4sDQ4PJTCPbmFNSEf_y20BwEhjGZQm3wdQ-TCt_OnwwpjSWU8gLsPafV1sjfOBSnKhlw5yczSf-sb504aPXYFA6VB2WXUTmEGUljwLu0jG-aZ2WqKyCoOLMJBcblxOT2t1ezs)

![](https://lh7-us.googleusercontent.com/BB4GBlE0jkeOb6wtlEHM_fA9EayAFuBLSigz9cPBhP10aKPReN2I6TuDlqjE_qkHJuyxHW32zKAbQRl3ylaNMD_ssDYzJNS-2R0mHAw-30teXkaujYH5N3FunU7nmmBa6VGUAmXDUxESi20BGPNkVrA)

- Penjelasan konfigurasi :

![](https://lh7-us.googleusercontent.com/_82X3LkffLry2NWNPB6dUC0XK2Zlnr6Zn96FJewxwbmEc5GH9Fcn43yt_dvaleuiVarCn27HqR_dTjMFVVA6ehjm8CMS4NLCY51lB6V4Scijc2j0B4ZPl1q0JqRFfAneaiYpjRLnnpynytPiiBaeyyU)

Mengatur fowarder ke nameserver pens. Maka akan mengirim permintaan ke 202.9.85.3 dan 202.9.85.4 jika servernya tidak tahu cara mengatasinya.

![](https://lh7-us.googleusercontent.com/I9WVI5Psd3FZ1mBhj5bAAxM1aaHBXufXurNP8ZSZCpuRwJFCz-yZgWjSegRgUm9d1EJc-DZ_uCDPdutERtClxBfYNnYQKuYA8A9Thk3Sbu61lUbjpizJJ_cF_3cJAfkJ3TgDQa65EA9VH4_68EAcB24)

Melakukan konfigurasi tersebut mengikuti spesifikasi RFC1035. dalam konfigurasi BIND DNS server menetapkan bahwa server DNS tidak akan mengembalikan respons NXDOMAIN (No Such Domain) yang otentik saat mencari domain yang tidak ada dalam zona yang dikelola oleh server tersebut.

![](https://lh7-us.googleusercontent.com/avFYFoemjGNMH2ZtqkJ2nZyC_0vfdqeZ68ybOuva9cg9USonl3MRgqj6ZNzUIvryTEnfRndNxJK-y7yxyx8bkZC32N79FIntcfhvDnweIGjeR1IzymDLV6y4uyd9eO3sUs06xyrE-poJEp_oJVt0lRU)

Mengganti listen on ke ip address kelompok 6 (192.168.6.10)

Melarang mentransfer informasi zone ke secondary DNS

Hanya menerima request dari internal network saja

Mengizinkan kueri rekursif ke host lokal

Membuat versi bind versi none

5.  Melakukan konfigurasi named.conf.local → nano named.conf.local

![](https://lh7-us.googleusercontent.com/llEbRVP2G-EAdh6Un6yBFZoC4H_JqeO5YTlR6RfW2cacI19PV99rmWLmxBODfuPn5kKXCF97mvE-AI_uCruv6dpBq7lsM1oZwnZJnIZ4ygOatQVhrDGsGTHAm-sLhMGgck9SLMfRvQxja8LD5LmUgFY)

Penjelasan konfigurasi :

Mengkofigurasi zone file ke kelompok6.local dan mengganti lokasi zone file nya ke kelompok6.local

Mengkofigurasi invers zone yang memetakan dari ip ke nama

6.  Mengecek utilitas → sudo named-checkconf /etc/bind/named.conf, apakah ada error/issues

![](https://lh7-us.googleusercontent.com/Wyjr1Wla5n6IpXU7sDJ0xlWpHmTcvQPwwTzUQiLSjT60OhNEtFuOTS7XLMjVkT0KAyH0fcAJeXIo1l9f8Mc2BKWJBjKXosFAuefRTzXe6fKZaHevHDRAt8hsla1WpkeWDV-A-QlEt4SwSHUCaxoPb8w)

Tidak ada error/issues

7.  Berpindah ke file zone dan mengecek isi dari file zone

![](https://lh7-us.googleusercontent.com/EZRAsnOShg3crhHywrX9SvWWAYdc54G2JNvQx5E-4aMPEYrQEP_HQQx4cot1elsdI47xfw4kfHabQpaZ5EtEOfCGDtC-ibLhUpijZ6j5IWuQ4aS4WsaOQi2TQqbzEwGIn_RO0rYqHdCcHDYzFp5qWAc)

8.  Buat file db sesuai yang sudah ada di konfigurasi zone file sebelumnya db.kelompok6.local → sudo nano db.kelompok6.local

![](https://lh7-us.googleusercontent.com/z6HFV2lFfnTBVzhNPUvfGFsGW0ceSzh1H9lb7KBiYyiWPAPRmPoks4VT4AXksg55XCX4UL7H749W7Kl04kQD_E16wQVrFN8530_h0eMYBOzFC9GQsXfczCoJdbzj2v6jClS5PwmVGtzUW8XOPnoRliA)

Penjelasan :

Mengkofigurasi SOA ( Start of Authority )

Serial dengan pola tahun, bulan, tanggal, urutan editing nya

Melakukan set NS memiliki internet address 192.168.6.10

Mengset www dan main memiliki CNAME ns

9.  Buat file db invers sesuai yang sudah ada di konfigurasi zone file sebelumnya db.kelompok6.local.inv → sudo nano db.kelompok6.local.inv

![](https://lh7-us.googleusercontent.com/JbWuIro2jcO5cm9BgpLLMhlPNKw12RZlG9mqLtdHicwsOcwdQ-n11lpRDq1qxCZ6Vxf34z1lT1OgYmGlTmd7Y0xN0mgn4jhk4VEddKuYvnTezoaaAR7PNIKnl_bKLqK-0eRi6PkSYsP4M7Lco5YlT0U)

Penjelasan :

Mengatur internet pointer ke ns.kelompok6.local

10. Melakukan named-checkzone kelompok6.local db.kelompok6.local dan named -checkzone 6.168.192. inaddr-arpa db.kelompok6.local.inv

![](https://lh7-us.googleusercontent.com/FGJyzAWizJbSyktgzxQ7XsEmPZBgJE18pR8yk2cx0DJhzPTOgI509rpHnfBdvapu59JjvySJohmB0b-i1_k77A1nPfM0cGttQNpHRfLgSNev95k1tUmw0b6desqyjnCtFvJ_t25ACM0NN_6bco7YXZs)

Penjelasan :

Memverifikasi bahwa file zona DNS Anda ditulis dengan benar sebelum menggunakannya pada server DNS BIND, membantu mencegah kesalahan konfigurasi yang mungkin menyebabkan masalah dalam resolusi DNS. Dan kedua pengecekan menghasilkan output OK.

11. Melakukan konfigurasi /etc/resolv.conf → sudo nano /etc/resolv.conf

![](https://lh7-us.googleusercontent.com/9Ups0iUqirtLmYj-m7ovQh-0AtAU7UzleI5-FICIeoYZZYnxnz27UDc0tOYU7Es5iRIikHAUBg6LmAc6ei9Yb4Utx49Kc6oEONWbq2QG2mMRfg3JsOhQdLT73mDP4-803v_H8IBb8tELFV0CJusgFDc)

resolv.conf adalah konfigurasi untuk sistem dns pada linux

Pada kasus ini ketika search kelompok6.local maka akan mencari ke nameserver utama 192.168.6.10, jika tidak merespons atau tidak ada maka akn mencari di alamat ip cadangannya yaitu 2 baris bawahnya.

12. Menjalankan service named → sudo systemctl restart named

![](https://lh7-us.googleusercontent.com/slvxVpoHtcNWlTrPBYMbkDlbn7ytC4heIFpdWJzNA5bPLQoZl_EAWyw_LkwRRWWuUKRhWEkiB8c1nRQKKw5-8N1iLJycwLI9kVat_A8Hckcc0PfeypEmURYP4URT29BxjNy7WTKtL317IYkMUmt_D2k)

service named telah active(running)

13. Mengecek Port dari TCP/IP (:53) terbuka atau tidak → sudo netstat -ptlun

![](https://lh7-us.googleusercontent.com/SGspqMfhOIlyQmCJ-dvfrPCD9jX-obqFWFvL--woONJRlHq1prc-OJQzBh4fiV9psnQfeDwN5n9sbKTiqKuKpLGq7uzHT_0cwCJttLnmd41o7_yeHIw_p2jFw1OtXsyQW63TkQfkdyX3MDHesNN1n6s)

14. Melakukan dig kelompok6.local

![](https://lh7-us.googleusercontent.com/BkeO3cS5Ba8Lj1nMgXRkBdG49cZjw13fSz-OsEGIeFw3dV26ddXk9p7wc8ChnHhoIUSLRbitx8K7rXmd3acn0UgxAiyjewxn-gfcTB_Wu4VGlQ5J_6CdEpWlV6wz5sJ4vC4NCgNrBwpTZLv6h01Jx2o)

Mencoba untuk menemukan informasi DNS terkait dengan domain kelompok6.local, seperti alamat IP yang terkait (jika domain tersebut adalah nama host) atau catatan lainnya yang terdaftar dalam server DNS yang diatur untuk domain tersebut.

15. Melakukan dig -x 192.168.6.10

![](https://lh7-us.googleusercontent.com/PyAEv8rxOaYJHiG1j4-jE7QMYpY5yMvdCGYS5C3HGgofnRxN6VXE6pvva3fNC78p6sub2UKTSluOKHzJYIatI-qvtkq4Xq7NTlLNlFnx37i40iA78b4ElgpIRscITAPOV7Sw2c7Pm_cy9RMjRw6b_a0)

16. Melakukan nslookup

![](https://lh7-us.googleusercontent.com/quITdM6P7ADjIsqsn3gyzrbpIfDzLgHPNe0sDCHe2ibYkiFYe1Sy-2CdJm12jx8a9h21VIe-0c9zGo0EJ-EbcWpZJtkjcj5wnzgsK6SmKyRbbIW5stTYO6CZVjc_FxhiDpc--alVI0jvCitW22OZ3BM)

Digunakan untuk mengecek nameserver dan ip telah sesuai.

##
