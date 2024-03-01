
# Sistem Administrasi

Sumber : The Beginner Handbook Debian12-SysAdmin

## 
# Software Sources

**![](https://lh7-us.googleusercontent.com/DoVcgJ7-ja95DsLHRLf5FSIs_QOVaBzOAGWeY8sWFFysbSWrzerbnsYvuj5roHtGxQFb_lTDCufAztXmB0r40hDlL7VURdthiSeISQJCY550_kFzhn4F8l6i21X4QM7pbNJiY0gSGD3CSU8kE8ixOy4)**

Linux menggunakan metodologi repository untuk distribusi aplikasi sehingga kita tidak perlu mengunjungi website dari software terkait File sources.list terletak di /etc/apt/sources.list. 
Untuk mengeditnya, dapat dengan command : apt edit-sources dan nano /etc/apt/sources.list.

## Repositories, Branches, Components,and Packages

Debian mengorganisir software-nya didalam repository. Ada 4 section pada repository official Debian yaitu, main, non-free firmware, contrib, non-free. DFSG(Debian Free Software Guidelines): https://www.debian.org/social_contract#guidelines.

Hanya package didalam main section/component yang 100% free dan disupport secara official oleh Debian. Debian memiliki repository khusus bernama Backport yang berisi versi terbaru dari beberapa aplikasi. Repository ini tidak diaktifkan secara default.

## Modifikasi Repository

1. Buka terminal di administrator mode dan gunakan command `apt edit-sources`
2. File ini akan dibuka menggunakan editor vim atau nano. Simpan menggunanakan ctrl+x di nano atau :wq dengan vim.

# APT Dalam Terminal

**![](https://lh7-us.googleusercontent.com/NPQc-F4pVQ_5voiBJKmC2mNklnR2tDR5rNJ3xj8ZmDaCLHfnSCMSFiMMV4LsNXsooGLI5xrugPCZJ11TpDQsjT_R52IoDec2GHytcQqsg4ouV0Lx2W4zMO6S659LrTqFZ3aZ84vsr5cgD0VdsyAe5VQ)**

Command seperti `apt show foo”`, `apt search foo` `apt-cache policy foo` tidak perlu dilakukan dengan sudo, karena tidak akan berdampak ke sistem.

command lain seperti `apt full-upgrade`, `apt remove foo`, dan `apt autoremove` perlu memiliki hak sebagai administrator atau sudo karena memiliki impact terhadap sistem

# Software: Simplified package manager

**![](https://lh7-us.googleusercontent.com/TwED53h23nIrPgJ8p19sYwtpP5jUoGkOdONWDRRZZIai3XwyurAXe4_FHGin0wee6qaQ3yO1EkE0tJKyeSF6s0v_0phvW15KgriTJTAlZkxloodNMoOyKSSdSa0gbZQgDnkBbkktsIDZb0WakNYMEZ8)**

Software adalah simplified manager untuk aplikasi Debian. Software mirip seperti PlayStore di Android atau AppStore di iOS. Disini, kita dapat mendownload, mengupdate, atau menghapus package yang berisi aplikasi kita. Software dapat dicari di search box Debian.

**![](https://lh7-us.googleusercontent.com/Xqe8M1FEXIjEBFzXSW2cNrZoY8EPeBU_VYlhgDziDaCOvjRGIzLSsEyO81z2lunsR2ZzR6ImZI6Zl0hmQ6YprYECDB0KJkArXuYZTVbtpzj3t-fF2uhfdlU7-IC-T3XprpuYDxHR-98ChDMtaMMFcwg)**
Kita bisa search untuk mencari packages

**![](https://lh7-us.googleusercontent.com/Oo1Ntu-CCXg6UYSXuCgypfbHrFwNF1V22o9sms1QPV1cIHtBoat2AgPMwNONY93dsOlHu-k_MZhW0WCekZcOWLuO_7A_nC3LvKrB95jQbiVsE9gaoa45dD7VxAfK-1aUwXCxMaEGN9-ZvHt0lGoS2JM)**
Tampilan home dari Software

**![](https://lh7-us.googleusercontent.com/7ptD4hGOjAlzW_GL6dtY7WxKVeEuT-glTUNfXb5KQVmGi0gD__W79vJc0xZhBOeOqmPswkI6SA1wQJ2fNDFcz01uoIXRx5aHX75NEvecMS8t3ZZdMljbcnLConraItcd6m9zFuk7uXTQvHykCvSNZKY)**
Disini kita bisa menginstall packages. Masukkan password agar proses instalasi bisa dimulai.

# Discover: KDE package manager

**![](https://lh7-us.googleusercontent.com/ynHFYJX6sZB2gr6bYeqn2Wm2ZI1FMHLo8j01kLmD9xc55_NV2w8LkJK5inDKCCbTc_NgZqwjNtP1WQpLoEdnWtuGPDEDASuTN4rivSu6x2W42A7C40jsCDX8Dg5RWCMdd0R3-JrIb3maaLFhhBe0CQs)**

Discover adalah "Software" untuk manage aplikasi dengan cara yang simple. Discover membantu anda untuk search, install, remove or update aplikasi yang anda butuhkan melalui sebuah interface. Kamu juga bisa memodifikasi source software mu menjadi install - or not - some non-free applications.

## Search & Install Dengan Discover

1. Search & Install Dengan Discover
**![](https://lh7-us.googleusercontent.com/itmJrQ-HnIrRIKbnM-RLWkThoVCjfuEWOLP0VsUx-esLV3UI4SQwBvlBO-BCS1VWt10F57gC3jhJmFIqMdLxDJIVTs89dFYXTt-CCF2k7KoQUemeXYWl7av7jjkcgHRg1XuOt0EZjoUvFx0btvFPOj0)**

2. Tekan tombol install untuk, melakukan penginstallan
**![](https://lh7-us.googleusercontent.com/3mhkN-HXpNkhRtltIRmUs4gLGRYRQpQ3UuzdAMWSN2fK1ENQTgKX8fJUQH9Emk8FXrRTUcJ4NaSIpi_vXPe9xBqxWnHeXCnOubxzzYSNZkzuAAN4gJsl3A-3r_UUjj7KJVkUlrB-dWYUXyNPgHxPbKU)**

## Uninstall Applikasi Dengan Discover
**![](https://lh7-us.googleusercontent.com/b4gu0Wi58Ih_j11M5sSqNR3ZEpdqkqsa33KuoHiuVP_Db6htohlGhMW5QM6G7mUiSgUb5HUm2lmuIZIu3ZeqWoXmJR-ue7sXuFAlGkIyCo0_JNvmF7sOUc5-RwuFqf-o6CaLQwCJCGpTRe4lgBk6C7g)**
Cari aplikasi yang ingin anda cari, tekan tombol remove untuk menghapus aplikasi.

## Update Aplikasi Dengan Discover
1. Buka menu update yang berada di bagian bawah navigasi
**![](https://lh7-us.googleusercontent.com/qP6ztHovl-u0kJv9u4N-8BXfLh0TIT1FC0GB4gSqUeJ3pb3Cx3SC11kDCwsZyM4YbrCoPFzZVBxbuMuehye0tlWAlqucoqBjJ2L1Vu1N1RjPbz6sar1gaUaOhaJYzF93oeE5EkfH6Ol4f5BdQbCVIjs)**
2. Untuk melakukan pengecekan update, anda bisa click tombol refresh yang berada di pojok atas. Kemudian centang aplikasi yang ingin di update --> update all.
**![](https://lh7-us.googleusercontent.com/B2HqDXa8lAvfqcE_2X6nGb9AMASU_aNqH_G23QoTuc3IAnMLaj7HvpXuJFWbsb95PIxG8lWmf0laz_KTZu7WOhoAjB9NWMQ92yEUrPlF9W18Os1l7k8BioKKQVgfu-77JGHszHFhy-9veAao5Od6ct0)**

## Discover: managing repositories
Discover juga mengizinkan untuk melakukan modifikasi sumber aplikasi yang ingin di download tanpa menggunakan terminal.
1. Masuk ke menu setting 
2. Centang sumber yang ingin anda jadikan sumber aplikasi
**![](https://lh7-us.googleusercontent.com/LD0OUQ9V91KMmVEJdltYTu0hISVxDW0TH1cv7djWJNz6Z88V_6pzwEi6KupzcncL1lRisQ6QQh3RGDjyWm4GHoJtCNMrBRtjNVm2mwFk87mTAl4mUAaOHdl7gYgNwNcyLMUblx7X3aTTcOc0qabI7Bs)**

# Synaptic : Package Manager

**![](https://lh7-us.googleusercontent.com/c0Ky2OUg6ld8zrlG-7L4Ij9zUcofHwLO21mgxVEvfcT_yMe7jZeyxXMrjUrdvQHfmdcouy6n_nlg43FqrTjXxPCnZjGctjc4ggpGe_btjlv4YGf9wQRYuOO3AckOerv1s5Sobf3ljKSFJOH0ceQTjpI)**
Synaptic adalah manajer packet yang dapat digunakan memberikan akses cepat ke paket baru yang tersedia, paket terinstall, paket yang dapat diupgrade, paket usang, dan seterusnya.

## Main Interface Sypnaptic
**![](https://lh7-us.googleusercontent.com/RsUHfiB4Yx0_2PNmdbM5gEtKNsk6osIoI8FEtMB7wYWBH79x-uYc3qoObNbRZ7gKE4SM0AuN28YofpXZU09djTTzk5U6y2cFsHoU1CkHQr-Nu4NyyB-m9Hqithhw3DTU_Za2H40lCEAgPxByUjDip2Y)**

Window dari synaptic terbagi menjadi 4 bagian :

1. Toolbar di atas 
**![](https://lh7-us.googleusercontent.com/VlsRd6tKv8A-mZks-AHvjVEv_hEaE1tZNWbM_9NjqADpB4Z2s_u1Hs7Y9PJ5YSXNp4VhGvGeJ_iSe9G9SLPfGz5TmVhVdlF4iwwPt7ybi7F1NmAIH8t5ckd6kp_cpPQzwKXF2UD4QBYKO1CMAPXoT_Y)**
2. Left panel yang dapat membantu melakukan penyortiran 
**![](https://lh7-us.googleusercontent.com/pJtAeS91dB3rJhwNie0gKx7x473TrOIXvmIBAkNz-KzSIPDy1L8pcol0BWn9pp-mlnQQNGpA5hs1hlkNHCP1qdKzP5ALfmLWIzU6A8bQm8h7RGKkdpWLC93oYpKD7WJ2uMOMg1J4S8pCPqyAEcz_T1o)**
3. Center panel yang menampilkan package yang kita punya 
**![](https://lh7-us.googleusercontent.com/uvuqzDHMPlgdInAr7qC_jrvUAVmiImhtlLdEzlAyIbnHhpLtoR4EgP3BhWy5fBvQ-NLHk8b-qm1DienjD_LRZ5NlpPFHy9lvMZz4XZbyyL8w7FZEQUUhiDciJEehsVhA7m9hBqnDRjMUFumXydG3Bzs)**
4. Panel hosting berisi deskripsi dari package yang kita pilih
**![](https://lh7-us.googleusercontent.com/QWVSUM-34Fw9W9DznTj9SFHU2mjNWsLOx85rguEq866_ZO41lonlINlrLPFQDbu7um-nSxKEd3SLrIiyU7KTEs1NWr6HGF63CZFRsAR-NzCEJArQ3ya9zafDmXOnC2oUwAd7l6Sjox5sXHvs6ZrIKqs)**

## Synaptic : Manage Repository

1. Click setting > repositories pada toolbar atas.
**![](https://lh7-us.googleusercontent.com/IHnpe8SFq5IOhiQzFRT-rST3Bjny06RGIUQ7t_XRJJ7Wl6HB6JkkxSgLX9QGtrjNwRob-mBVBcRxY8B86HSiCth9V_JuDf-B1ujtrf-7d1RCKcJp1AJXBhRuCkvSypwbk8Ia6oEBvk8K3w93xRWlbfI)**
2. Sekarang, anda bisa melakukan konfigurasi repository disini. Perlu di ingat setelah anda melakukan perubahan repository, Synaptic akan mengajak anda melakukan reload untuk pembaruan yang terjadi.
**![](https://lh7-us.googleusercontent.com/7WWPUC_TgJzqspQMtJu8DWNzntmRbCxQV5teO-Ngc6V0Y0HNnsBb7RCjd57eynouGvNslA9cRyAnYusniTeKf1s7NGoph4Y2sRoSdd-RzwG1tLMGJPqYrMW32vofyK6Ih2fUw--chqySto2BVgJESxs)**

## Synaptic : Arti beberapa komponen
**![](https://lh7-us.googleusercontent.com/oDokkpSwstjzEEkz_-hj6rJ8MFgQ5q1-6kSy5Y0IB-SeiWLJYZfhoJTaLjJ1ZMqVbHJI48yxOFJ-3XVWqLvL76TcSTKmSfBm-MTMoDkhJTVkNfGiUqwfaUlugLSpPEfdj1ERyEaodrpEC0j_dionlEE)**

- Disebelah kiri logo debian, terdapat litle box yang merupakan indikator pakckage (putih untuk packages yang belum terinstall, hijau ketika package sudah terinstall, merah ketika terindikasi sebuah kerusakan). 
- Kemudian, logo debian mengindikasi package termasuk package free.

## Synaptic : Update System
1. Klik reload pada menu top bar untuk mengecek pembaruan paling baru yang tersedia.
**![](https://lh7-us.googleusercontent.com/fLzOgaPMRvgib4YWm0sepg7jnVOJc1PnupOFxEpMa07_r-qE8VmBWPNnSJTSqy73u6_TTfxDOP0PixMqU3zHGNhvYC8NWXLFH0490Qu8TKwKg_5YmLlmHe8t_XGwuzn4BxN4puPLyjGpWHj9S7D3Vlo)**
2. Klik Mark All Upgrade ini akan membantu anda untuk melakukan upgrade semua package yang terindikasi ada pembaruan.
**![](https://lh7-us.googleusercontent.com/UfHF4dKJHxrQhxHJkBTyA0_wCqH3TtkyGpeNLtj-hxXnLY7hGWY-gBgVQ9YI-Jei6OmbkacOplfo2W0z2JXQ-Eh80xTQphvV-hIRYnTdVgU9b4KmGO2GpyMlUZdGslcxAsv7jGNcYjQlfj8jkrgcEGU)**
3. Klik tombol apply di top bar untuk mulai melakukan update
**![](https://lh7-us.googleusercontent.com/IYcX3kyG5h8R0XxyBmeEnKsvqQwwaoNHvr_wtaSHgQPPxRm6mwfog29v7vfyH7sWvJj-AW8S7-zyZUXfCMzQtibSrRzFBaMkBAwFah5SarcPmVHeuAtCjlMdiHIw5NmUbZnewwD0yRjF_HU2ngYZiBQ)**
4. Tunggu proses update selesai
**![](https://lh7-us.googleusercontent.com/CzKVudpiYc_Q-eaBuf3zPV5rLO3Y1QjDuuKUlgEUCPb8Yljrj_XZeA-7SBfQhhXljjPigVeWICBkHcMjxaFe67eB75bNLBqCPfnUFeOj73hrWIXfEGbPvA_zQxmxDOE0Buyot0ZS9g7q7wJXeT8P03M)**

## Synaptic : Melakukan Pencarian Package

1. Klik Button search yang ada di top bar.
**![](https://lh7-us.googleusercontent.com/qCG3sB_6J9MivZNoWkzIe1UDrCN0yLrjhBsmcYqOuST5azjyxSuPrqXJIIxzErWi__e50IkJ080qKIXGzonq7GwOAEN9_VW5l7xXV7PSeFuQUwlQaUtrAsZrm1vDxmcxFWG88D8-60Di6XvKWYQmFgA)**
2. Disini anda bisa melakukan pencarian nama package atau juga bisa melakukan pencarian package berdasarkan nama, description, maintainer, version, dependencies, dll
**![](https://lh7-us.googleusercontent.com/JuKUVHCMeIa0f8-WaKQUf1y_ZRBGOxQI9ed1DcxKs_5xtJ4mHsU3P94e5ogEUOjHTERzB6LOODetYWLVVz2OxEMvN6vvvQg-IrosTPgKGLHSLmWkRsP6Ixmbq--egCW_jzWIK80xWyO_ntVvczoqTmU)**

## Synaptic : Install Sebuah Package

1. Klik litle box yang berada di depan logo debian, kemudian anda bisa memilih “Mark for Installation”. Lakukan hal ini untuk semua package yang ingin di install
**![](https://lh7-us.googleusercontent.com/pPRh_rLfZFwL5XqzaynfdjsUvxbRGBX3Cvz18VZZRnf0hlFl1pmmSvV3zLieLdSdYFz4fl66yh9_bnJ1TPSE6GgNdF19z00mCQRk7qX3Vp6ThJ9PhnEUvucurdiWNpXuhU0RcoiDoUFqC56TkgF-tvA)**
2. Jika dirasa package yang di tandai sudah cukup, anda bisa mengklik tombol “Apply” yang berada di top bar. Setelah itu proses download akan dimulai, dan anda dapat memantau seluruh proses download di dalam aplikasi Synaptic.
**![](https://lh7-us.googleusercontent.com/ss_XlSgyhAcTZSzV0cdV-u6j60g4sX7bLq5VsD1gQ3xsWSEZXjnYwScKk-N-bwyFUGcOzSHiM-mAIGEtWVQrmnZgjxe02yxOVDmTDZpBObFt41jqY9bVUdcSxwL3DLfWRyUbPPjcyd0NN-xAUVxhzfU)**

## Synaptic : Uninstall Package

1. Klik litle box yang berada di depan logo debian, pada package yang sudah terinstall. Terdapat 2 tipe uninstall : 
	- Simple removal : Tidak menghapus configuration file yang ada di sistem, digunakan ketika memang ada kemungkinan melakukan re install di kemudian. 
	- Remove juga dengan configuration file : Melakukan purge.
**![](https://lh7-us.googleusercontent.com/JpggxxJnvPeFwAnXVWN1GazDm6q97j4gLWuoTvYhqMfTYEddhGF63rRJxQzUVthGlx70aHvQhOD579D8HDy6teAt1X5PHDgSwFwG6bDYOpA4B9L6nQsFAh23ZxK-nCxckA2gIV2oTvp1wYf4GnPBo08)**
2. Jika dirasa package yang di tandai sudah cukup, anda bisa mengklik tombol “Apply” yang berada di top bar. Setelah itu proses uninstall akan dimulai.
**![](https://lh7-us.googleusercontent.com/5sTE4BQf-jrLzWx_KDVFhjjqDUmSGUcWErnFztYkiWf3_UI-YglMzwMUNTVgx8HCf4JvuBddctPlo_zvrDdKE59YucD6dpanfastYd-rNNube0Psd79lGVH3f5pT5LdqsO5W5qY58xuwqf_XYdu3paY)**

## Menghapus Paket dengan Synaptic

**![](https://lh7-us.googleusercontent.com/6G8ZWjzVehwppP4fzzLB3T30x5ls82oU4aLSKc3J7LOQy7s5QZrwFUUni-xVrTBt_4EKRUNi3sK6eVtvKBbHF7qI01aV5ePVnJczZu-Du6t2BZfyj6FxkdrFqEmHRy4Ka__SbZbb08o6oHIKq_7f8jg)**

Sama seperti saat instalasi, untuk menghapus paket juga dapat menggunakan klik kanan pada kotak kecil di depan nama paket, dan pilih opsi “Mark for Removal”. Kemudian klik "Terapkan".

Untuk penghapusan sederhana akan menyimpan file konfigurasi paket di sistem Anda, dan dapat digunakan kembali untuk jiika anda ingin menginstallnya kembali.

Untuk penghapusan menyeluruh pilih opsi “Mark for Complete Removal” atau setara dengan “purge” di baris perintah terminal.

## Menghapus Paket yang tidak berguna dengan Synaptic

Seringkali, ketika perangkat lunak di-uninstall, beberapa paket (dependensi) tetap berada di sistem dan tidak berguna lagi. Paket-paket tidak berguna ini dapat dengan mudah dihapus dengan Synaptic.

Saat Synaptic diluncurkan, klik tombol “Status” di bagian bawah panel kiri. Jika kategori “Installed (Auto removable)” muncul, klik kategori tersebut untuk menampilkan paket yang sesuai seperti lihat gambar di atas. Selanjutnya klik kanan pada setiap paket di panel tengah, dan pilih opsi “Mark for Complete Removal”. Setelah semua paket ditandai, klik tombol “Apply”.
**![](https://lh7-us.googleusercontent.com/inLZTpTPf-FDwovHu_vUtJVWtDakSHpNhN4Mk81Cqm0PwrORvw46euS-Vf3Zmdp2CIyvOr1SW9WtWppafr5Skr8j2nr-QHe0fjYFUhaQNTPRe32t83wC8a_PoF6tngp1-PCmRN9Mf2XGka9Z1Ytnf4I)**

## Menghapus Sisa Konfigurasi

Klik tombol "Status" di bagian bawah panel kiri. Jika kategori “Not installed (residual config)” muncul, pilih kategori tersebut. Yang harus Anda lakukan selanjutnya adalah klik kanan pada setiap paket di panel tengah, dan pilih opsi “Mark for Complete Removal”. Setelah semua paket ditandai, klik tombol “Apply”.
**![](https://lh7-us.googleusercontent.com/HSQyCupUutRnsn5T9iJE80DOfD0zX1y404whn7MXy5AToW4p4OqeVL0O2teG0A6oMhtamKYFGiKdMRhGCHNH2XHZCE8IeOerkyvzQGVdu9QbYN6Do6J0nc_2mI56MYEMQ5bJLO7PeIfuQiGZvDTJk48)**

Saat menghapus perangkat lunak sepenuhnya, beberapa sisa konfigurasi mungkin masih tertinggal di sistem, namun residu tersebut juga dapat dengan mudah dihapus dengan Synaptic.

## Melihat informasi rinci pada suatu paket

Dengan mengklik sebuah paket, deskripsinya ditampilkan di panel tengah bawah Synaptic. Untuk mendapatkan lebih banyak informasi tentang suatu paket, klik kanan padanya, dan pilih Properties, atau masuk ke menu “Packages > Properties”. Maka Anda akan mengetahui segalanya - secara positif segalanya - pada paket ini: dependensi, file yang diinstal, ukuran dan versi.

## Synaptic Preferences

**![](https://lh7-us.googleusercontent.com/nS2XzWFTbsyr9xoP9T1FXz_nCC8_dvJNwI2ErOVcrPWN8JZzXroV7LctOkGM6SZes7oLi9hHhxdf3JR0vba7ZanG-gLj4Gx09fS1ywsc7XjTID_eojRIeQ8Oy6EKhfrvH7BCVdjeRMDtRcHsl37gyxI)**
Jendela Preferensi diakses melalui menu (Pengaturan > Preferensi) menampilkan 6 tab :
- General: pilihan di dalamnya agak eksplisit. Catatan: Anda dapat menghapus centang pada opsi “Pertimbangkan paket yang direkomendasikan sebagai dependensi”, jika itu membantu Anda mempertahankan sistem ultra-ringan. Namun dapat menimbulkan masalah saat menginstal paket. 
- Columns and Fonts: memungkinkan Anda menampilkan / menyembunyikan beberapa kolom dalam daftar paket, dan menentukan font. 
- Colors: di sini Anda dapat menentukan warna paket sesuai dengan statusnya. 
- Files: Saat Anda menginstal suatu perangkat lunak, perangkat lunak tersebut terlebih dahulu disimpan dalam cache. Paket-paket ini dapat menempati lebih banyak ruang disk saat Anda menggunakan komputer Anda. Di sini Anda dapat segera menghapusnya atau mengonfigurasi tindakan otomatis. 
- Network: Cara Synaptic terhubung ke Internet. Anda harus tahu jika situasi Anda memerlukan modifikasi parameter ini. 
- Distribution: Mendefinisikan perilaku upgrade paket dan sangat eksplisit. Jika ragu, jangan memodifikasinya!

# Membersihkan Paket

1. Membersihkan cache

    apt clean

2. Membersihkan Paket dan File Konfigurasi

    apt autoremove --purge

3. Membersihkan paket usang saat upgrade sistem

    apt list '?obsolete'

    apt remove '?obsolete'

4. Membersihkan paket yang tidak tergantung paket lain

    apt install deborphan

    echo $(deborphan)

    apt autoremove --purge $(deborphan)

5. Membuat daftar dan membersihkan file konfigurasi yang tetap ada

    dpkg --list | awk '/^rd/ {print $2}'
    apt purge $(dpkg --list | awk'/^rd/ {print $2}')

## Mengosongkan tempat sampah

Tiga tempat sampah yang harus dipertimbangkan :
1. Trash Bin User
Anda dapat mengosongkannya dengan menggunakan command terminal :
    rm -Rf ~/.local/share/Trash/*

2. Trash Bin Admin
Untuk mengosongkannya dengan cara yang benar, gunakan terminal dalam mode administrator :
    rm -Rf /root/.local/share/Trash/*

3. Trash Bin Eksternal
Terletak di disk eksternal Anda, biasanya diberi nama '**/media/y- our_id/your_disk/.Trash_1000**', dimana your_id sesuai dengan nama login Anda.

## Membersihkan cache aplikasi dan thumbail

Setiap aplikasi mempunyai caranya sendiri untuk mengelola cache-nya sendiri: beberapa membersihkannya secara sistematis ketika ditutup, yang lain menyimpan datanya di folder /tmp, yang akan dibersihkan selama sesi logout, yang lain menyimpan semua informasinya dalam folder tertentu.

Setiap kali Anda membuka folder yang berisi gambar atau video, thumbnail dibuat untuk mewakili file grafik tersebut. Thumbnail ini disimpan dalam folder tertentu untuk digunakan kembali, daripada dipaksa untuk menghitung ulang setiap kali Anda mengakses file semacam ini.

Berikut command line untuk membersihkan cache aplikasi dan thumbnail

    rm -Rf ~/.cahce/*
    rm -Rf ~/.thumbails

# Installing external“.deb” packages

**![](https://lh7-us.googleusercontent.com/IMKXXJlk1266wbAawgtQmbShVe5Y_xfQLlpBKM-V_mWgSln0z14EL1uG4gKiOZ0kSqZcYvfq3c_QARflxZTSWQSG8SY33-QHoKhf6SH7PSKQOo8rwEY4aoPbV8NkRqAywZlsOXm1RAGTRmJiFH6jV7Q)**

GDebi adalah utilitas grafis yang memungkinkan instalasi paket eksternal berformat “.deb”, sekaligus mengelola dependensinya. Untuk menginstalnya, cari “gdebi” di manajer paket favorit Anda (Synaptic, Discover, Software) atau lebih sederhana dari terminal dalam mode administrator menggunakan “su”

- Terminal

    apt update && apt install gdebi

- Installation in terminal mode with Dpkg

    dpkg -i package_name.deb
    apt install depedency_1 depedency_2
    dpkg -i package_name.deb
    dpkg --purge package_name //untuk menghapus

# Installing Flatpak applications

**![](https://lh7-us.googleusercontent.com/NGunKgx2ArYdUb7bIhoQFrzOkcHH3UGosMSjCEOgGgjnjwLqbKDZ6fQKswmJYpM-uTm5oURBcnW-r8YeTF_yqaMXkZ6rZ86Uer0_1XqKJRNBnZ1I3tqw9c_0A2yEKEbUcksC54jrFV-maRqXdgfTVpA)**
Flatpak (https://docs.flatpak.org/en/latest/getting-started.html) adalah sistem aplikasi virtualisasi untuk distribusi GNU/Linux. Tujuannya adalah untuk menyediakan lingkungan “sandbox” yang aman, terisolasi dari seluruh sistem, di mana pengguna dapat menjalankan aplikasi yang tidak divalidasi oleh repositori distribusi (misalnya, versi pengujian).

Manage Flatpak applications from your terminal
**![](https://lh7-us.googleusercontent.com/6iqp2fgTMHoKGCPTpXStye_Taract1Z40vyt87qF1Sj8S2i-9VUzVPAOHoHi3MKMQupY7p5VRTY9ReSLILub-1UqiffhyX5NtqZ4UuRktlFKj2ciNTYmiGL2c1_SiDxjXCcskXnCmf4JfFQd2EG4rMY)**
