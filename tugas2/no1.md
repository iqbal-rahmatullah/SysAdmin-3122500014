
# Standart Structure Directory Debian
Sumber : [debianadmin.com](https://www.debianadmin.com/linux-directory-structure-overview.html)

##
**![](https://lh7-us.googleusercontent.com/_83QVhFiMOpH-Wq86vAa4rEXmar8pJ5S1nXUZf8XHZMrCl3BUEbbTyY1TDgIbAXXmET-rZJfILnUbR3OhSTQpCS9S_x2Ndf2p9XfWHoEkTVhIKXxb9_xhF0KiveiqZakKEVhmXWtJpxWVBDrB-LwUUc)**

    Penjelasan :

-   /root: Direktori beranda pengguna root (pengguna super atau administrator). Setiap pengguna mempunyai direktori home masing-masing, dengan root home terletak di /root.
    
-   /boot: Direktori ini berisi file yang diperlukan untuk mem-boot sistem operasi. Ini termasuk konfigurasi kernel, boot loader, dan file yang mendukung proses boot.
    
-   /dev: Direktori ini berisi file yang mewakili dan menyediakan akses ke perangkat di sistem. Contohnya termasuk /dev/sda di hard drive Anda dan /dev/tty1 di Terminal 1.
    
-   /etc: Direktori ini berisi konfigurasi sistem dan aplikasi. File konfigurasi di sini mengelola berbagai aspek sistem, seperti: B. Pengaturan jaringan, konfigurasi pengguna, dll.
    
-   /home: Direktori ini berisi direktori home pengguna biasa. Setiap pengguna memiliki direktori home di /home dengan nama yang sesuai dengan nama penggunanya.
    
-   /lib: Direktori ini berisi pustaka yang dibutuhkan oleh program yang berjalan pada sistem. Perpustakaan ini biasanya dinamis dan digunakan oleh aplikasi yang berbeda.
    
-   /media: Direktori ini biasanya digunakan untuk memasang sistem file sementara atau perangkat penyimpanan yang dipasang sementara.
    
-   /min: Direktori ini juga digunakan untuk memasang sistem file atau perangkat penyimpanan, namun lebih bersifat manual dan biasanya digunakan untuk perangkat yang dipasang secara manual oleh pengguna atau administrator sistem.
    
-   /opt: Direktori ini biasanya digunakan untuk menginstal aplikasi atau paket tambahan (opsional). Beberapa aplikasi mungkin memilih untuk diinstal di sini untuk memisahkannya dari instalasi sistem yang lebih mendasar.
    
-   /proc: Direktori ini menyediakan akses ke informasi dinamis tentang proses yang sedang berjalan pada sistem. Informasi ini dapat diakses dan diedit melalui file di /proc.
    
-   /run: Direktori ini berisi file yang menyimpan data runtime yang diperlukan oleh sistem dan aplikasi. Contoh data yang disimpan di sini mencakup informasi tentang proses dan sistem yang berjalan.
    
-   /sbin: Direktori ini berisi biner yang diperlukan untuk menjalankan dan memperbaiki sistem. Perintah penting yang biasanya diperlukan untuk pemeliharaan sistem dapat ditemukan di sini.
    
-   /srv: Direktori ini menyimpan data yang disediakan oleh server sistem. Direktori ini berfungsi sebagai tempat penyimpanan data yang diakses oleh server, seperti data website.
    
-   /storage: Direktori ini dapat berupa direktori khusus yang dibuat oleh user atau administrator untuk menyimpan data penyimpanan tambahan.
    
-   /sys: Direktori ini menyediakan akses ke konfigurasi dan informasi kernel Linux. File di /sys dapat digunakan untuk mengontrol dan memantau konfigurasi kernel secara dinamis.
    
-   /tmp: Direktori ini digunakan oleh berbagai program untuk menyimpan file-file sementara. Biasanya tidak ada resiko menghapus file di sini.
    
-   /usr: Direktori ini berisi berbagai program, perpustakaan, dan data yang digunakan oleh pengguna sistem. Isinya mirip dengan /bin dan /lib, namun lebih umum dan luas.
    
-   /var: Direktori ini berisi file-file yang sering berubah, seperti: B. Log sistem (/var/log), file spool printer (/var/spool), dan file cache.
