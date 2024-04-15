<div align="center">
  <h2 style="text-align: center;font-weight: bold">Praktikum 5<br>Instalasi dan Konfigurasi Web Server, Database Server, dan Mail Server</h2>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h4 style="text-align: center;">Disusun Oleh :</h4>
  <p style="text-align: center;">
    <strong>Muhammad Iqbal Rahmatullah (3122500014)</strong>
  </p>
<h4 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h4>
  <hr>
</div>

# Daftar Isi

| Nomor | File                                                                        |
| ----- | --------------------------------------------------------------------------- |
| 1     | [Konfigurasi NTP Server](#NTP-Server)                                       |
| 2     | [Konfigurasi Web Server](#Apache-2-dan-PHP-FM)                              |
| 3     | [Konfigurasi Database Server](#MariaDB-&-PhpMyAdmin)                        |
| 4     | [Konfigurasi mail server](#Email-System)                                    |
| 5     | [Final Check All Services](#Final-Check-All-Services)                       |
| 6     | [Test Email With Email Client - Thunderbird](#Thunderbird-Email-GUI-Client) |
| 7     | [Konfigurasi roundcube](#Roundcube-Webmail)                                 |

---

# NTP Server

1.  Lakukan instalasi paket layanan sinkronisasi waktu → `sudo apt install systemd-timesyncd`
    ![](https://lh7-us.googleusercontent.com/6qleLCOU0C-XRDxe3zLvHnDiFJ917MNCcD7pEo61Dw96SX8jrRl8fTVWke2Nc2L0rS1kBskI4jSWCycbxvPYOUqCEuDPZucaXkuF2PE3DdLIN_F1SXaQMMZGO3kcFcIBq4niRT5z5uUmawXLQYXPu2c)

2.  Melakukan konfigurasi timezone ke Asia/Jakarta → `sudo timedatectl set-timezone Asia/Jakarta`
    ![](https://lh7-us.googleusercontent.com/rOXhxbNI8SHYFRXT8rdmvYEVOuTUFF7lVWV8gmJQDbHdFe3TWW2q7_6bmh8fXn-YPHWiOLYS4Q9X-oNmpkxUwP2kK7eLcV6ekicLBKHfsJixBn7-2YUj7P6dcfr6E9HLmjo9uWk6Ylym8jh3OAhGndw)

3.  Melakukan konfigurasi Real Time Clock (RTC) untuk merefer ke UTC (Coordinated Universal Time) → `sudo timedatectl set-local-rtc false`
    ![](https://lh7-us.googleusercontent.com/bIkpcLHm7RBijMqfGHCkyFRxYasff7Cev6rCQwSaaXueiGCrHR4ccDDhghHLaghKIesSPj03nn1OmuYjBNvL8He5eJDFMUhmpSt8J1CZ1jibqBdxfdVKmHryF2-zkeykJqBSX6IZnrbshjYxVQPTgZU)

4.  Mengaktifkan NTP Client untuk sinkronisasi waktu → `sudo timedatectl set-ntp true`
    ![](https://lh7-us.googleusercontent.com/gj2HsoGlXCysy5WVz-Pw--j6Wzq63sR84sz2I_63ratnau_-3J_Uz6RiL3AtUE9XBqEoGBriOqO4f8kDlzai-p-j2rA2xkiwOZuHuKxrOHLNfrY3QE0lNzVCMERfwSJkH0TJxa27TI0TDs4lMElFu9k)

5.  Menyunting file timesyncd.conf untuk mengarah ke NTP server terdekat untuk mendapatkan waktu delay terpendek. Biasanya setiap organisasi atau negara mempunyai NTP Server sendiri → `sudo nano /etc/systemd/timesyncd.conf`
    ![](https://lh7-us.googleusercontent.com/yAdhF6YQo5xMxEZtilqbrfY9P0j3LxhcsLH9KLzytX-RR6z-wsMozgZjFJYOidQO8qnralz3KrRdJQ9e3B-BQoQ3F1d5aIHFwqx6twqm_usNUh5O71HtJHbaf8xTRYlm5ZE1TCDH5cxYlrmVv-8hIT8)

6.  Restart layanan sinkronisasi waktu dan pastikan layanan berjalan dengan benar

        `sudo systemctl restart systemd-timesyncd`

    ![](https://lh7-us.googleusercontent.com/0a43wTugP6VRjsObjNVWwzSkPQT0ZtEUFKaXKHsUkmPItaWJXlI037QEgbAGf5d0a9ZfZDwXA7koNGn7MgSx4VPxHIHePOtCzgiEik-9ciLyRSM_vU9gjMOsDmMwhEsOJ821t96f4xd7V-2zxn3Gh3Q)

Mengecek status layanan sinkronisasi waktu → `sudo systemctl status systemd-timesyncd`

![](https://lh7-us.googleusercontent.com/jcM01gH78CjV42dCYfjL1KdvQGdnniFXFShaSJaXK0pQate5MBFKnY7vAY7zvz9Hi_RRQUakc7cdZQ4J99myrJHC3GSCjaxgfAEyCKK0fx54pIBD8a-4LEVbAosqHO9Z6zUrpNu1mpNyk6PcAzLw3gI)

Dapat dilihat status active(running)

7.  Lakukan pengecekan kesesuaian tanggal system dengan perintah → `timedatectl`
    ![](https://lh7-us.googleusercontent.com/wWdwg45Q8R7waJsyFtje0GrtTdTeP8FdspXXx0CVtGtGYj-gPu3gHLLqSLHbaVAwKd_9B7sjkrLKx9WXIB_tsslV8unuP9iAz5vocijGtH8L2U4WVTulAIngG5AkqulW3Q3-3DCq2B-hASY6E03ylqM)

Menampilkan status sinkronisasi waktu pada sistem dengan server NTP (Network Time Protocol) → `sudo timedatectl timesync-status`

![](https://lh7-us.googleusercontent.com/EVtpIXdIxnrECvLBWBiiBlS6RzJRXkPVWbVzqMhYLknu93NRNhCgMZlarVfBfXGN_kjO3cxqnK6A-ZAs120br886fCaVecsKD06eV5y3LJzOdsev_HEpk50G0xrPLB3g-2sR1PoXR1E8MPXWyWEohok)

Bisa dilihat sudah tersambung ke NTP 0.id.pool.ntp.org, dan memiliki delay waktu yang terbilang cukup kecil yaitu +- 30ms

# Apache 2 dan PHP-FM

## Install Apache2

1.  Install Apache2 → `sudo apt -y install apache2`
    ![](https://lh7-us.googleusercontent.com/yPRgzue3LlmHlYK80FLg67hetTgbTr6eQqmcLQWBKNvRi_JjuwbWY1RQ8hbzYbdTy-I6-39LWRH_Qv88iDvONmWQFNJsUIkH1xHfq-6v2pnlcAZjB8E61lqiErxT7BuVnSkdCsul-gQf8M6KTJGwrlQ)

2.  Melakukan konfigurasi Apache2

- `sudo nano /etc/apache2/conf-enabled/security.conf`  
  ![](https://lh7-us.googleusercontent.com/1kDyox1QDjasYUQeBz-zwWkPyDjvpprl5NztbVrDniu1c6C2FD-7-GNjwtz3XEZYatj6ItSGDVdz65Pj7Oj3MHtrbsCfwGbLs-cwxUpetjPQOULVqeSKOCfDn7XBSvgY4fBF3KadFjqw9r4GPIoDWeU)
  Mengganti line 12 --> `ServerTokens Prod` --> berarti Apache hanya akan menampilkan informasi identifikasi server yang minimal dalam header responsnya.

- `sudo nano /etc/apache2/mods-enabled/dir.conf`
  **![](https://lh7-us.googleusercontent.com/ghGzLTUJWc4Q1bi4a1kc9STJ42eDKi6DZ9Zs38ywcYCkJFS5DemZCiUUkknjA05NbH-IyFpYXdXj7Mh5tDf6w36HQAqic9oNQceE44zWRJ3kZdcf-hoxH3-7T0vR-nceZAcgWQvxiFXgF7F5-wtthsQ)**
  Menambahkan nama file yang hanya bisa diakses dengan nama direktori, yaitu index.html, index.htm, dan index.php

- `sudo nano /etc/apache2/apache2.conf`
  ![](https://lh7-us.googleusercontent.com/_yv7tyJrD1AFsDNP8BLQk66BKoggkRmn58lwGId757PEPOkSBKpetmE2wJTlFDb6Bg4omZiyc_szw5yJyrj809SCfP6TKRhPr5hRBNtlMQ3lxij8_C9CBWWFWPWClczE491zmZB_JGr-XaAL4PbR_hM)
  Line 70 --> Menambahkan specify server name

- `sudo nano /etc/apache2/sites-enabled/000-default.conf`
  ![](https://lh7-us.googleusercontent.com/-wcmCatN08B4XYHJZhS-C7v2P0-4WzPeeKjDTKjkzSSuiN_S6DuhRxKBE1xfj9tt-a-UAQDqsw0PInJl2Q6d_KVo4KOSrB_dMnoOXeAtP4p5ZVenVOD8AD4LTvyBo7SEWQKcdPyUBCMANObMWINxbew)
  Mengganti line 11 --> Mengganti webmaster's email

- `systemctl reload apache2`
  ![](https://lh7-us.googleusercontent.com/B0d5ABd9RrigZfXfaEDDSDqkw-f4n7ISVcFiX18iPt7S-nmYFYOSkn2cWZpnQqt0guXC0A2o2FH6zIecmOnaqqNoMXO-e3tZ5rcfLDY-7qJhoNtDt55QPN4pFJFbdoGDQ7FWwsOY2-Wp4rlBeatMtTc)
  Melakukan reload layanan apache

3.  Melakukan test ke web browser
    ![](https://lh7-us.googleusercontent.com/HA_mby_9MPuJGVOA1Z9jfVVC_32BSZW0Bwo3mvrIHy6dDZXzvnVlZNRHDSKzI62XUlr5uEfeVfdw_W4VRFhSfcgbHSNdWf8e9tNdUy_eOKohanq1ddtKYt9nWF3FtJbMuPW1C0RGuzE_ZKzkWz-nBLc)

## Install PHP 8.2

1.  Melakukan install PHP versi 8.2 beserta modul mbstring dan paket pear --> `sudo apt -y install php8.2 php8.2-mbstring php-pear`
    ![](https://lh7-us.googleusercontent.com/jSI55JxmuQIQfLxmLA_35vKQoPW_6-TFpbmwtVPsldye6Qi1aANPJxTsUQCohmhvLnmH0YG-0QYchkLNV2-pa1kHL9oqFC1vywyHBpM8sMsm7c_4SXNPYFyKVucesvk0hCq85Epd15bP9PmDVHx8JuM)

2.  Mengecek php version → `php -v`
    ![](https://lh7-us.googleusercontent.com/8DzWnJS6jmbixnT0Nbjk3HKCO7vjd8a4URKv8GQR_6wUntC8tc_2ExkKoarafpqJ2yReElMz9DmWNLrfdE44vERMQURXyQxfouG0heWsZ2EWvNMucjtascrjihLHpRuwoR3u0CwQa7oilOKlhryxBGs)
    Karena sudah muncul version dari php, berarti php telah berhasil terinstall

3.  Melakukan test terhadap php  
     - `nano php_test.php`
    ![](https://lh7-us.googleusercontent.com/9Va3jOzWvk9YuC1F4WUPGWxhabvia438yX-TNFUdZOurNKlG9bdqj3OspjQg-mPXDnRRAIHpH0gTB0q3HK5WoGd3WMjwuhL829cEIlf6WppD--uHcR8_Ph3n61r9dEYSzOicAo3EvKFseeqn2XOsJSs)
    Membua file php_test.php, yang akan mencetak ouytput dari `php -i` ketika dijalankan

        - Jalankan `php php_test.php | head`

    ![](https://lh7-us.googleusercontent.com/w4nO2axRyOQBFzpUo1a9zQQPkopPrbdlSYU7WeAckLVesMnyPCwe16EYMPUUVkLMOytX1yv7cT3WJrpjNmiHouI7IA2sN6_GUu4SAKFtNzTgPgg-R2Aa6A6NkX9K40AclNhrahc_iUDLkes_TYRsIQo)
    Akan menampilkan output dari `php -i` yaitu menampilkan informasi terkait konfigurasi PHP

4.  Melakukan Install PHP-FM → `sudo apt -y install php-fpm`
    ![](https://lh7-us.googleusercontent.com/qPLJPnb-5aI3R-tjGyrgp3CiTazxhcEhT9HBqAb9xpvFZXXz_BAQ0pGcEIQ3DO0SuouQAtdTMFvPOTatoNcJQ3j5lm9tkpvJ1Ppao94v8Fepx4Ihn_NxAQkuM_OieVR19eAJ-TG7dkwPVlKNn4r8Ces)

5.  Mengkonfigurasi PHP-FM pada file konfigurasi Apache - `sudo nano /etc/apache2/sites-available/default-ssl.conf`
    ![](https://lh7-us.googleusercontent.com/w3b01aUlV2lF0W0pbBb5bBVAu5aiagPdsEv_7sXEZ2WPvVamIV7ct4fcnc_A7ZxiKvyetUicxezFn-eoDSBiEFjDtMOi0DeJjldayTPXipwEtBYXcwIHYErmE3RZFa3XgQTLahcVU0zzB9ihbAvk3bM)
    Menambahkan diantara tag < VirtualHost> - < /VirtualHost> yaitu mengatur Apache HTTP Server agar dapat meneruskan permintaan PHP ke PHP-FPM (PHP FastCGI Process Manager)

        -   `sudo a2enmod proxy_fcgi setenvif`

    ![](https://lh7-us.googleusercontent.com/WmVoeFWb6fOQEvReD76TJxKG7Eu1h80w1A7jxl2sO2zQ3LFiGIoZnx5zfC4Wc6yr7WDw2-MRpGF_G_4ia6jJo2NvarZLbeRRo49f0hr8gglaXDRxr-pQpcxz0peHpoT0k5fHrLiBfRYFaGtauFcrTEY)
    digunakan untuk mengaktifkan modul-modul proxy_fcgi dan setenvif dalam server Apache.

        -   `sudo a2enconf php8.2-fpm`

    ![](https://lh7-us.googleusercontent.com/xsuvRRiiW6qemXu8Hxv4rFsTSISrpKFt0wtZJzryk5RcGz7LwwvocdsaRZo5wPbMbO79oOXYzzC9G7YtLQfrl1O33lzZAZsEDH2b-6rZ4Aa1sUZvlaZbK7FtOqa1t6AcujCcjFM9C_eUN6GJ-G43_Ys)
    digunakan untuk mengaktifkan modul-modul php8.2-fpm

        -   `sudo systemctl restart php8.2-fpm apache2`

    ![](https://lh7-us.googleusercontent.com/9hmkEdJ1n2zq8Hb2pbiriZafkM9jbyRJtxGNayhK59DO1Xii9aBIa6N2m0wxDmIgdApM1exJ9laaXlNuuq2VsgLEJKdpTiZaSbExteioVOjVCgj31zjfWN44XzRqkK96MKo1Eg-Kl0E2Bh_f0LJUrhs)
    Melakukan restart service php8.2-fpm dan apache2

6.  Melakukan test validasi terhadap PHP-FM dengan membuat file info.php di root document → `sudo nano /var/www/html/info.php`
    ![](https://lh7-us.googleusercontent.com/Lm7xKooM6638JonSPl-vTjB6bK36PI9CpmlJPuR0spPK4qZDAUXn1lZVnsgs4vfe3wF3OjBvoGM9Kpmsj7Y8xh7Mrttj8tA010YSywBVEr2E2-1POaz7-6nK5YDtAdvMVLqEuzHuttvhTVMEmyM2_Ro)
    Membuat file info.php yang nanti nya outputnya akan menjalankan command `phpinfo()`

7.  Melakukan test di browser, membuka file info.php di browser
    ![](https://lh7-us.googleusercontent.com/aq_QFqAYicQmDwXtLwCfwlEEisEQ6coWDj1LhGgRK9htHsd8Pe8TwACMJxU9C84xjpR8ikWPUtw2ITTXaWdblLFL_zC7eU4Ux9WL3akOft8HuzPYYYx3a-2g37gYYhveM3etlnE6fXResG0FReL-_TM)
    Jika berhasil, maka akan menampilkan semua informasi terkait php.

# MariaDB & PhpMyAdmin

## Install MariaDB

1.  Melakukan install mariadb-server --> `sudo apt -y install mariadb-server`
    ![](https://lh7-us.googleusercontent.com/kcomOm3lYn6OXKIxlwrHF52WVTRFcJtkdcKBvLMyxvlsFJ1sI7rcMbhx0NZwLoazo5lwk3cGPWSV8yix2rbeHc2Q6eGSRQX6FvBHQfKp0ZCb0Ga038m0dXJTSrgC5UyiXgK7Wss9CsTt35RP9t00yG8)

2.  `sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf`
    ![](https://lh7-us.googleusercontent.com/ELp1gab-RkacelpMrH9OAHlP1R0Y4AqIbU4xQOKVJ05JUWZm806KtH6E5Jy4WfQ7mZnoV3aLrpjUduOjHcBoprblPLhIcmpVce2i6F6kI0fMDRzw3lTBL3_MhlL5vFAfxJ5w6XJj6OwJPsuvT1NcgKw)
    Pada line 95 --> Mengkonfirmasi default charset menggunakan utf8mb4.

3.  `sudo systemctl restart mariadb`
    ![](https://lh7-us.googleusercontent.com/6vK4Aayg029w1lggwplMXAPx4l2mNiWhE6-G7a7XV7xAUX96zUsrtXdkZ7Z2Ll6-OJkX4tM-Xa8k5dWK2FvncTaehjkR0gTRa_zvhIVwFdIPfddzzJzeIZQaLBP3aZzuk7Jt1mlgqmdXsA1Sh1PWtgQ)
    Melakukan restart service mariadb

4.  Inisial Konfigurasi dan testing database MariaDB Server - `sudo mysql_secure_installation`
    ![](https://lh7-us.googleusercontent.com/118a_bF7cu1QHoeBaTGxpxRf9UgrQC9OqNURl2-GgjF6JbjUZ6MfSPf838hXm6o_JFgYo84ugqZYIem44h99P6snXeN31AXH0DLlacWoloXOn5utlznneSKs28WU46jCOwqCr3x21ndDh1pgpxvH3zY)
    Melakukan beberapa tindakan keamanan standar dalam instalisasi MariaDB, Ditahap ini akan di beri beberapa pertanyaan keamanan. Seperti set MariaDB root password, remove anonymous users, dll.

        -   Connect to MariaDB → `sudo mysql`

    ![](https://lh7-us.googleusercontent.com/pjQ_jPvlijB9V_eaDBwm0yq8KavIXuE3psrbE9LITLeM5ZEJXC21P1u0eSNO4ubtn5FushTIUrz_Ijr4s8rtVYOZM8uufwsb5ihiwbQ1RsW4h28Sgdj8ca5T96JP2GZI1_dxFpppKQMuFbuHs8tkjrk)

        -   Menampilkan hak akses yang dimiliki oleh user root → `show grants for root@localhost;`

    ![](https://lh7-us.googleusercontent.com/wqYBleVwNd7daDArUTa5Xb3HH-0tBKnJe2tZkuWXCSakxe2mudfPyeRnX63dpsMJeM4N-DLvrm3pJe1KkuXSic9vsPEM9yAxhBvpFTpjz7GnJcjyGs0rFW1bCoRauTk3e6ArIwp4PexXEr83BP7Q2lc)

        -   Menampilkan semua daftar user → `select user,host,password from mysql.user;`

    ![](https://lh7-us.googleusercontent.com/7peYP_dBTyQIqttro1-LBcipIsuKwOhOAwev80Jn3_mzzdIik3DET7TNxxfsGObUIBN8nj5J03v3KX5BqJjQSY7oV-pdl7IbYOh6b-HjmxXDhT5HjpuFe8gQLXEZxhJ0jhXjE7-6PBGu0-BKSwZK29g)

        -   show database list → `show databases;`

    ![](https://lh7-us.googleusercontent.com/Rqmu93wCWwLk5UCf0XBay0LtTU8x3oWHQwDWji6iF5PyAT5LY9bd74yxG1J_zNc1PgLs4Pe4wV9ddR7aFhH4i20EULEU-dPWQaIu8gOk3K7GMwG12fu1eLb2gPHyhf4TTERUmW-RcSYa_lmBVYg0-Tk)

        -   create test database → `create database test_database;`

    ![](https://lh7-us.googleusercontent.com/6leKRqEirGNiKZ0WNBI736LyGekfTmdjLz0I4KvWv-OgQgNqU6m44_Ci4EI8iY0hzlLqEr080wxPnnSNw40oeLorYrTY6ODbiPIgUgwMqdX4gi6QA9Hm8sj0waqEPYUCwNmkIL7OE93YVtjkg0jIllc)

        -   create test table on test database → `create table test_database.test_table (id int, name varchar(50), address varchar(50), primary key (id));`

    ![](https://lh7-us.googleusercontent.com/MCkYThec9M5wSHOoLdZMNSUPMKMWszR2Loa2v_bX67jPACcnsmWu350sI4vXU9wUcKPCf5ubYJk7479RzOzwJQVd4_X63aJtr0q6or1Sdy1N8ulnrVPyXlAXBh0XSQGAe_q4j5iUR84pNLnahEQuFTA)

        -   insert data to test table → `insert into test_database.test_table(id, name, address) values("001", "Debian", "Hiroshima");`

    ![](https://lh7-us.googleusercontent.com/4mHwV4LrDf07eq4EQ7du0ZxmUB5DkKfGVpElN6ePIQ_D17507YFJp2Cvm9qnhG0lhq-EXeLKw8ij4qOVPZ5lnTqk3V2HEA79R9MQtt59T6dBF2EPQQv6tVET-fa1ZnsKZUe70Ex3RXLAQOVxR8vWl14)

        -   show test table → `select * from test_database.test_table;`

    ![](https://lh7-us.googleusercontent.com/HwLv4uDoEsqFTmlP_pnIcXCReRkfZphAomC7B2lAi_kfrafcrRxisk1ZZMw9lM1pkNV49Y2S3Hv94g2QtH6zCXmIvNkrDilK_a-tHZpGKZ97Ns82ftcNq1zFiNP0B3oN_AG3kDzNIBXrBQ5meyoqTus)

        -   delete test database → `drop database test_database;`

    ![](https://lh7-us.googleusercontent.com/tC0xMfa9wykkGAFDFAwKbQINlmda42UQ4_6bc6gQSTJ7_bQSkGPs9G27yxkA3080-ABDyJpLngsTjS_oCZ8-AGUw7ADe4CdUhhMFOLGq2L_xmXkLf988G-pk6TECXz53EVAlRZPG5ZY5qj58-wapxio)

## Install PhpMyAdmin

1.  Melakukan install phpmyadmin --> `sudo apt install phpmyadmin`
2.  Pilih Apache2 sebagai web server
    ![](https://lh7-us.googleusercontent.com/VhdtO-UsnJoAdnw6S1jbR1WGAFqSuQU2EdworaJyKJofo1oUkUrulYfY1rDGVN3Cpb5g4K-xEJPre4w-9_6HGXDO5S7xQYuz4vVR_S5cKaW_HsaKYm2y-6Oc3kMjPDOziR3fGrFw1i-IfXlZPnnBPHk)

3.  Pilih **yes** agar konfigurator melakukan langkah-langkah yang diperlukan untuk membuat database dan pengguna khusus untuk phpMyAdmin agar dapat berfungsi dengan baik.
    ![](https://lh7-us.googleusercontent.com/870jIAjhDSUmOmyVHQsgOziF6nv_JlLpSIXcWxun9V92nqg1uR2ggWy7v54nvNubchWFDxQ4qazQqN633NOw3yRhJsWUBfDKT3cibXv6OABIgJAiNTE9qTzL46Ne_tlp7n-YGWoeynkQRDwZP-XWn9c)

4.  Masukkan password phpmyadmin
    ![](https://lh7-us.googleusercontent.com/zpjFnz0DCIpPOnfDCtc-knR5lgEweTdSfftEwma2SsB1ht18alsw021exj4rsG2P1GR_tviMw49LzHqZgeuAtihetZDcSNv0s-XKlQ7Biae4rafeBhvWH-GXp_cPDyhDIxFZ13pZz9Xo_-6BF30MLZk)
    ![](https://lh7-us.googleusercontent.com/H1DH_9Vg04HJe41y0J2GvWWOSuhq89_TO_7MVj8n6vOQQYY_u_RTG26L8v-qQmga8nQT3hRd8zGi40Qd8xy2hiRImHWcyRni4Ayfpt_-piW_H7CfYBEsOQa3xFXsVbkzUHmVasSpJN8tbK74YDOAhD8)

5.  Menambahkan konfigurasi phpmyadmin di apache2 → `sudo nano /etc/apache2/apache2.conf`
    ![](https://lh7-us.googleusercontent.com/HVmfT-HHm8jb5GjUNBnf0uevRD9PH7bLfdBTXJdqtnOPQeEnlk1fUMEjzC9dwHCV26ljYCjjWvINGvLD0XeYLailzX_2yFTyzuHMwbC5NO4RHj1UQ7gGR7nCKD8O8cI8em22wHAA4oV3Nwi5bCuvjTQ)
    Mendaftarkan file `/etc/phpmyadmin/apache.conf`

6.  Coba membuka phpmyadmin di web browser![](https://lh7-us.googleusercontent.com/G3geOVQoCPMwWwCdhpWQZ4twRF8dWLlDdcsoePqJOV8eKB-s7ykgb10i28iUoyiEGNos22joqXlSRHrO3wBTJPS-oi5S-W4rQ2Eq5R8ThF0ncN3vivlf_eLQ_Dixg137QWe1cPH-iF9WpOisI2tQMYg)
    ![](https://lh7-us.googleusercontent.com/gXmrhrPPQFbAmUilNYDwmXXG8mSjNJJPNONzs44GHdlGN2TA07EusypO3EwJmJr_FFIcJSDZfx5leqoMAvn1fJzpzS-kNjuyCdNHt3jde93hNQthox3w-idOTtwPj2GZc5IrlSp1RCYIWjzVOPdos9g)

7.  Menambahkan privillege ke user phpmyadmin - Login ke mariadb → `sudo mariadb -u root -p`
        -   Lalu berikan hak akses penuh kepada user phpmyadmin → `GRANT ALL PRIVILEGES ON *.* TO 'phpmyadmin'@'localhost' IDENTIFIED BY 'password' WITH GRANT OPTION; FLUSH PRIVILEGES;`
    ![](https://lh7-us.googleusercontent.com/cnP0YjrKiKgKMsWlgwu5cfSAn_M-irr5aqKLBvIAq6f1KQQ3wDDuqmRzePNZmpyH_K0fw3A7ZbZWJpnOjnl8PhHPXDNENXOdTeMWR4UNmPXE7Eky7ymb2XLITID9LHfYhB_7XLDy8d5BsR0AXzTnTJE)
    ![](https://lh7-us.googleusercontent.com/cDSvQA67vuzC3vf6PYzQwGpeeSV1SoATvJQKBkAhht8wyoUBcqcFRYsDdLUCZTmsSf71QOhgFpw_JhLWUq9dJUgyUVt9jpZGN51We3GSGL5VNAF62-5-FmKzTBW-gMtvMHraYzQ_nOrMsekDpoc3ehs)
    Bisa dilihat sekarang user phpmyadmin, memiliki hak akses penuh seperti create database, dll.

# Email System

## POSTFIX : SMTP Server (TCP 25)

1.  Melakukan install postfix sasl2-bin --> `sudo apt -y install postfix sasl2-bin`
2.  Pilih no configuration, karena kita akan melakukan konfigurasi secara manual
    ![](https://lh7-us.googleusercontent.com/Of89nFxXsawcSJ_wtSKrmGu70e7nDpvVKMj6JPMUrR5GRPMH04vf0BNa5KLeb8rVJeFubH5FbDMOjXgKjfUMmitgnYri0o8ffp5FCxAJG-4by8QKMsMsmvWQ1vW09Me2jkr05B-kdPUfCVWhPL7w8LU)

3.  Mencopy file /usr/share/postfix/main.cf.dist ke /etc/postfix/main.cf --> `sudo cp /usr/share/postfix/main.cf.dist /etc/postfix/main.cf`
    ![](https://lh7-us.googleusercontent.com/V0EAEpGcFojZKIf_j861r_Lv_-LKyCI9GcSmY11cJl5E7Eps1rJlQP9UdnJKr_CXk1aP5R2XZgounDHRLGS_P9vaLnAhagYaP4Vb_qOIgYO6dUIpH-Ltj7QqeJV5XnIjvXCJJnVORakfSPf6OkSddVo)

4.  `sudo nano /etc/postfix/main.cf` - Uncoment line 82
    ![](https://lh7-us.googleusercontent.com/D-I7MSAjOVncJJRccRmO5Qe2Sg9OjauJJRLCiEhB41M-p9_RJqlWgVL_4P1V6BeTsioCIrDq_B8SHPz9RwKWwtsQ7oPP2IeB2gElkaIYeNA0dYQWtUlqUkLBa-mj5uB9XbHlZvtjdnAUIaVjJ-JhfdI)

        - Uncoment line 98 dan isi dengan email hostname kelompok6

    ![](https://lh7-us.googleusercontent.com/aFf_MrzQWLdv5o5Fq_GdasW5KklAXMrGFFdSwFYMSCNOSj-hoLPNtJ-nLN-YaJPK4jtrVBhRVMv395Iw2tQWiiI_yXkLX-Ja8jEjlpMhjNpcRoFgk_5Towi1xhHU9yD3Y0U69pXlCrnQRIhsn6FrroY)

        - Uncoment line 106 dan isi dengan hostname kelompok6

    ![](https://lh7-us.googleusercontent.com/x6SGeTJwt-IqCJ8xJEyiLrGfOBnT_WqQThaZTFMX-IeeuoN-PBukr4rmBGLUzdP4QZdA4FeX_g9i9YsXqYPRzCuEylZm4-NezEvEni5CBXzNLc2HNcOEIXPwdcpb9KhQg0-cRRqak-PAYktDfjloCa0)

        - Uncoment line 127

    ![](https://lh7-us.googleusercontent.com/8_pLVPlcEXBPsrugBZb5Q-dPuFSFMOWNyh3xYjBDYkM-_D3WYMqhEtoh4xmE4NtUwAYoEmbbDtKtoAJW7giI-ERYtnXMXi9EGLZ7SZg--sGGNltv78fnG-4eNR5agnQcud-ntSiKyHMHayCEE5oZCds)

        - Uncoment line 141

    ![](https://lh7-us.googleusercontent.com/wZMJjjr-KnLpl-RtJFGOFFTtpxkSaPLWTES8uHkU4XhzdwdG9qu4bUuZVW57o7QwUfTNKszuUzJd3M-pHTmMOSVHLeknYKV3enyfkrGhabJf886hTP-UjQlaVf3A_mgbjScEGtnCCwpy67OhWZ1mVeA)

        - Uncoment line 189

    ![](https://lh7-us.googleusercontent.com/7cQ5wQjhR5BWEuIBtiKGkjjcGyrN1hhoWFz7iancaTGgujny_EqrNZmi27LrmZQvf1ccg-d7tUNoXAKPxpyYTseIdduZzykDPHOHnAfp9nfnqj_-IhDnFHR22yW3DY-4fSUA8yZOnD6SiL-_njtQHUw)

        - Uncoment line 232

    ![](https://lh7-us.googleusercontent.com/l-_oxinoQ4X0e2RM7H89UBlBuhXmlT2oW6EmnxDZ2hq9OnX7GpWp3a_HkmLr5-gNOUgWfOrpUO4D4OZH9hxxWYkyZbwnMlQB4W0M-5ybOMa7OW_JjbUXAsXXSqjRkgC5V30-g53dYHQuh7UcVgy-2gA)

        - Uncoment line 277

    ![](https://lh7-us.googleusercontent.com/422izznfevPWdb-xE7o7L6vzAm7LdQDEpf0Rlr-mLiMBfYnfypu8lM2v-xbDFdvsV_Fbv4NWVrm-04Z8y533imhunVP_sQA_1G68QRNliKXodDONq9XnybcgKrkL7_aNx2mJwgXvS9glct_ar4nUTHI)

        - Uncoment line 294 dan tambahkan local network

    ![](https://lh7-us.googleusercontent.com/sMDGHVJyJcVSPi64jnnm4nsG8aDigk-wA5G7dvXDC5BUzP_XkcDzfExoQpxcSFO7hhv2ZE_qRbqQpISfTbsSG1P1TIy6Wfvai_7ZPg-ObT_aAE5FOu4Z8EJGRx2UOT-gZraoDyqUOvmZoI97fzQxvEA)

        - Uncoment line 416

    ![](https://lh7-us.googleusercontent.com/Yl4qRSNWuNk0xdwgitagD7UJ9YSJPJiKBOq1mZQSL7WP3N5C-_Z2ylRaYr9Aig2av0WVbZt6M-sWqAwYiFeg280iGD1nz4rv58NL1_lStn7XhPLQhpRAUZZSfjFlRmaw7LLl25d-vAL1WZxjLICsAwk)

        - Uncoment line 427

    ![](https://lh7-us.googleusercontent.com/pZKTlV8NNQq2hhiTzd3_bTrZvmm9sChPsBAU2lUm0QW0dHUGH9yIiRzbjLf-lHLAiZn_t_sHo5x6UrPkNp-oRalG2l3hhEBdag-jDE3FXp-EA7J_VbIJa9PACDGC21ZPT_iaFPxR1G73zYIrSWtMsAs)

        - Uncoment line 449

    ![](https://lh7-us.googleusercontent.com/x5iD9Y-a2dFxej0FHljLo2X6Zc0NodjD0m-KLvT2soDjSMvZ9Pl3YOfkrlEqIJwOxbKmdCqmqfXBeWmnUoEY1jJhMNq2_ZsA10XIcMsK18gLqSIDa65Bm_j7RcjAl6o1WooVCvQcPp30HuNsTuHpto0)

        - Comment line 558 dan tambahkan di line 589 konfigurais smtpd_banner

    ![](https://lh7-us.googleusercontent.com/x-7w6vSfby5LrUPS9vUCInjWbu45npgH19DJlxjV8FDHl0zTlw8Ag9zNydJRcC1cAq9t7GpzCsH98XyU8qMuVL_ru3B50HHi2fYzDNB-TI96ZdlZi9Q9H3w_dBvTOPiLRjcyzazLWgNY7LYHCzUl08I)

        - Tambahkan di line 659 sendmail_path

    ![](https://lh7-us.googleusercontent.com/lPylcnFzCiYFTqXUBqCDnU9PJvZFpPot3xNgEOkP5KUnxZfXSCW6ifKXuUbM3w6KOvnYHhUmMLERewoEZZKy6QCwQ-hurUDvhWJm2dnXh8ice4fhkmzomPhchVk-uqCYhCFsOmmQg-jrqUAvoU4mfQU)

        - Tambahkan di line 664 newaliases_path

    ![](https://lh7-us.googleusercontent.com/hn6GcxJhsbsTCCjANx9AiI5pYp-prsQroC37dvy2ROtqb-j9xwNMqJrpgHHuEmWu9OZ2WmXDkxJFourS8DK2Ic57GUIbRvdypDaODI36L2Gw_VMZUCbfQkCga7IWHhXacgi3rhS1OuSHZzyY1JlNMEI)

        - Tambahkan di line 669 mailq_path

    ![](https://lh7-us.googleusercontent.com/Nzr4EX_2Zdnb9l3-eMY0e0blYqY8BFu6l8f1g3QH4OP4slpULtd8HvX2a7dxwBSVN7M4zd0q_RHKCHUJcQxyLHxBCrilYjvG6-z0eZUBH9Nc376p0-0rcErkCT7U3fY_4c3sNd6HIE1QLUKTcNJDz9A)

        - Tambahkan di line 675 setgid_group![](https://lh7-us.googleusercontent.com/_C_01JLWHKSX0rNxDLyVJckReWvWqRe5cEBn4hWpoAL8XDJxJSmzG2sw7ZBkn5oNmvAoxQjTKeNzx5O9ch1Hv4LGjgNI-rfS_FyE5vCmGqG4mph3dslVEFTf84ky2Y9f6lc1OoxwblZuf8L4m08YdNE)

        - Comment line 679

    ![](https://lh7-us.googleusercontent.com/HJOE-gAMN01bQc1um1gUJBfqYy-sXTKD0kXnU3XmHcegdgmRd-BEjg19zDTPNxFExKOyJTOERdEqZ8xCwLMb_j3SGX2F9aOAwqjObuKR-Qdt_IqFrxg1y3heL-7ggBXMtAMQZKCxbK7Iy9bu7W3gtzU)

        - Comment line 683

    ![](https://lh7-us.googleusercontent.com/MsG-eVfnhCECLg0hVebr247yvBcd65EUmaxgNf5ryPK51iZOFah3Hige53XLfngUJF7dYNw3SMJMuj0y7J54cB0UFVBQy6Qj0pgcHJ01LfiDWfUlsKpPTQ6E07-KQ79e9nuWie2Gz2VvdP13dZQJzSw)

        - Comment line 688

    ![](https://lh7-us.googleusercontent.com/47jBF0uy-Yo0t37ZPf9EV8qWVdGu0cw1jwtrVKNXPxgNYvmme7NonJdFYfF4NfC5r8WK0ZRum3fMho8PRerLsGbC3Zizw1AoTKVAjMDh6R1m3UCpBE5q5qg5QahZY5od0S7jSqwZRV9XRLNkLnBPwII)

        - Comment line 692

    ![](https://lh7-us.googleusercontent.com/LTxOaNnnBiNcKF9QnjUnEh8_5gKIoBD8WAwPcFodWlSAdCTUswAHDI2iFOL_9oc_GVW1NZmPVcgjOpq9LcNrWgvDSxKXFszvFaEHO1RbZOjNW2FgYVdvKHdYYX4cjlzkodPDPQyg0_4eYO_-U6OtLuE)

        - Tambahkan internet protocol di line 692

    ![](https://lh7-us.googleusercontent.com/PvwO3IF3h-bdkk3fxevzraW_6TPuX0QJXPZUglRhbBIiK67uIQ2AiZyAsOmPmBnSsEqZDR9nciKF6iWQpnhhCbNes5XiLqYA4QI6k647XNI363h2iw2QazbkrzgHQHYz8IzViCVKFMB35t8puGQNtcM)

        - Menambahkan config di line terakhir. Yaitu mematikan SMTP VRFY command, require HELO command to sender hosts, Mengatur limit an email size, dan mengatur SMTP-Auth settings

    ![](https://lh7-us.googleusercontent.com/1sJsfUzTufKJkJZ0cQML9ccX4wOd6N8bOg_qgCoykUTjA2Ur9MNIDeMBATC9hbrJSlo7GbD1nO9xjOsGIRpOdFPYzICPa_Nyh5zzmAQe6vwilvsW7lPCO2W964ngD6cVK4_uNjalY7gsLRma7fPsarA)

5.  Meng-update database alias untuk sistem postfix --> `sudo newaliases`
    ![](https://lh7-us.googleusercontent.com/gHd4ggZIUgmoq1wUOUujzM5Vw3yBtYQhZv-nRQ_rFOT6F_AmIfruDvuSDMUNMqRcVCIMZ_zAS_yHf2Fmced82tai9e-mRPnjrf5uqU9ovMdK9bn4pfRDYdFkKT0v9kIj8jQg0T_AdEcvgbHqtpo_tUA)

6.  Melakukan restart layanan postfix --> `systemctl restart postfix`
    ![](https://lh7-us.googleusercontent.com/bXXqd7RYLVUOOmnV3iavykYYxya3fQT3Iwjy89N1svFEAy9DYfQrHGpo5f5tlvfo9Rl0uoHeSFEgnSHIx5K6_NcBcX_MV2SLuwxIVkYyMcIvfxq5bf0WnRts5oHifYCOcBF9369MV-R_Uxr0sHBagGg)

7.  Menambahkan konfigurasi anti spam

    - `sudo nano /etc/postfix/main.cf`
      **![](https://lh7-us.googleusercontent.com/i4TDaCYXocL81KZWbIRk1b2N_QaO3ZC8jE8z8uBtBb7He6_CJzsSBWv21mZqaaj8hI4JGHdLmuPbzVRRDujpv4Dj9_3PnCp3IRRd_Qw52w3jH6eh_Uh-nMv6gIAE8y6S2BoYgsLHNHo2s6JZuNROV50)**

    - Melakukan restart layanan postfix --> `sudo systemctl restart postfix`
      **![](https://lh7-us.googleusercontent.com/3q-v8W1b7uZV-aagH7pN9t57FNlJbb5dhGhc_p_DpF5gJpt5k-c38RmnV_Q6vVpwS0WlcxWC0LUvtLJgJRL2EOODM-RYE8HYhTNiRobKiYLuLDrD945nKmRBlTlN_dUjutebfT5dFjokQVzi2QZseZM)**

## Install **DOVECOT : IMAP4 (TCP 143) and POP3 (TCP110)**

1.  Melakukan install dovecot-core, dovecot-pop3d, dovecot-imapd --> `sudo apt -y install dovecot-core dovecot-pop3d dovecot-imapd`
    ![](https://lh7-us.googleusercontent.com/60foy-32uMUEs1s8scAdFFeShwLPt1cLZ9IktRZBH0arOHy87pEz0gTJePSTwdhp1SrhM-6_LiiCpGsvq30XbpQHZzOwZimwhYCpZ_na_qWG4pz7NOz37zFBmXv6ufne77ct1fqdzAK8IB6LgiSoNeM)

2.  `sudo nano /etc/dovecot/dovecot.conf`
    ![](https://lh7-us.googleusercontent.com/7JVOEiccAjtBjO0gCpkUriRORqGo2EvlnlyyRT6JkpFHXbk4b8_WIpGvY08dmo4xynQb5oSeIh2NA3Z-onR_i6nYdy2QTULDI_7eYZvrgdz7qatcbKuqb536ycgd3-uUFtjJmahNL81KGp-vnJHoLik)
    Uncoment line 30 agar Dovecot mendengarkan koneksi pada semua antarmuka jaringan yang tersedia.

3.  `sudo nano /etc/dovecot/conf.d/10-auth.conf`
    **![](https://lh7-us.googleusercontent.com/yEcFYS9_sD3XG8UNCtbBPD2_l7smwo6MdJ36ex1p3zQHbaGXokTfhaAmPz46YgH2utFjYln9flCxwmI72TcY8EgLxl3KyI0RgELsHl4b-vs4X01Fc0KJVQotwHHg21Cgo4ZhLL_ifmUUzJSzL9gvhMc)**
    Uncoment line 10 dan izinkan plain text auth - Tambahkan auth_mechanisms di line 100
    ![](https://lh7-us.googleusercontent.com/eGrekjSb1G2HTc2nIVXr-sonw36vhkuJ2tPMiVlANM_gH-rctbq-jujFI4KZH7tafcu7RO9V6Z5TBhQYpEogA8GEOZ_7ZAZoPORDa1tPXh5oGRJ1Op5uFtpiW3P3cvrXR5s1tNSTkf-R7XJm50dTR4M)

4.  `sudo nano /etc/dovecot/conf.d/10-mail.conf`
    ![](https://lh7-us.googleusercontent.com/sIFiykOh0elE4--tCA8d2C2VzarpfF6SUY82xgtJlCI3jZNu85ieXF5DpnkIau_I5dGUQoPOsGrZC9NGTiewFqrdqz5o8Byd8Eu--iZ634xPshVN3fWIwYRiRMNMRNYhAQ76qppcIuosgTBl2damHSo)
    Ubah mail location di line30 menjadi Maildir

5.  `sudo nano /etc/dovecot/conf.d/10-master.conf`
    ![](https://lh7-us.googleusercontent.com/t5t5_zeyMuBRz-S7qxqpEAs34686pZpeDKBYeHMo9MmwG48uknHrUJCft6n2afVP1RJwRTzmstG4Kq5om2mEPo69oTj_jtoVWVCI5rf5gv-BFruj04UCj-uqUPobL3MEzBEhZZvP7ryiXSP2JtYktIk)
    Tambahkan Postfix smtp-auth di line 107 - 109

6.  Restart layanan dovecot --> `sudo systemctl restart dovecot`
    ![](https://lh7-us.googleusercontent.com/Cxa-5xPz15HyvxzyjeACHYfhnkQgBUrZHnQYvv4S6K8uYxVscJCYLhhO52vR7-neUGFinhp423SejQ7wQOOMTMEJkRKe2iIKYaSaEZZTw2Pm0895aA3qRYPRQ7E-EcwIHUq-EK2fJ5MIwCxX4bgytO0)

# Final Check All Services

1.  `netstat -a| grep LISTEN`

![](https://lh7-us.googleusercontent.com/3YwkjGltGhYoyafwBKGZNM0_-0PFJCUM_ac_71GtI6sv7M0fHlXyXaoA7prHyveItbBqarnJD9tHxk24bOw8pbEIC8dPCSi0RRsBnjac4WQ0ZG6hxFo8ey96EZK6Yf2kPAMC_gyW9EJ7CYWePqyzxWM)
Akan terlihat hasilnya dengan status Server (LISTEN) : MariaDB(MySQL), IMAP, POP3, DNS(domain - http), IMAPS, POP3S, SSH, Postfix (SMTP)

2. Melakukan Cek terhadap Layanan Posfix `telnet mail.kelompok6.local 25`
   ![](https://lh7-us.googleusercontent.com/9A42b1pZqc-knVQM_wG7iLAyo5H5n5D0Ez-kuL-DrBrU3Y-3KwMPdXHuyOqw7sl-sOGJ28wUqgL-DVdF7F5sB6_R7cU2PxJXXBpVpo9tZTeQ80Z-5OwVIGVZI64GKo8flQndMiDujoYm8HTXWYrHNPg)
   Memeriksa apakah server mail.kelompok6.local dapat menerima koneksi pada port 25. Lalu menhalankan command `ehlo mail.kelompok6.local` yang digunakan untuk memberikan informasi tentang kemampuan server, seperti fitur-fitur yang didukung atau batasan konfigurasi.

# Thunderbird Email GUI Client

1.  Melakukan install Thunderbird melalui flatpak --> `flatpak install flathub org.mozilla.Thunderbird`
    ![](https://lh7-us.googleusercontent.com/P3PdoskhMBpv_iXPTfVwmkmA3fRF9S-rtH2n14jm1G6f95dgF0nX76sjAl-8osZDwfXLcaE0EsPSdFNwiLVVbCr5kSHv0Bf6z20OKQh7YdpLLk0IJyyeJYUs9z4h-r5iSYV40aH_cxykkKE_pyDelPY)

2.  Menginstall thunderbird GUI dari https://flathub.org/apps/org.mozilla.Thunderbird
    ![](https://lh7-us.googleusercontent.com/EsBbYbTt9r4gmAi23dxA6Cgw1HLqwFWSW8md9VOYCDzgzmLlP18vWqnINANuRLdZf6LeBhtlpTj6-S0b5GuKOD8yu4bLVOqoxpD16piaDqAdVb-j16q8ZOppBADTHLtamiz6-L91w4ahCyilNiCn-f0)

3.  Menambahkan 2 akun email ( yaitu user iqbal dan root )
    ![](https://lh7-us.googleusercontent.com/lfyTInAcG6FoGMRGzOuYdUd2kZYkejbYHedaopOWR-G7OYLBQXyytJJGzFjYPa00zrkJVMTDaKSrem2u2oS6OsXEKmz0fhUb5DIuWCQbAps1R02-i_saF98KviOLaTqFQ1xskf8mLIdJaQ7wVOd5tl8)

4.  Mencoba saling send email - User root mencoba send email ke user iqbal
    ![](https://lh7-us.googleusercontent.com/-_5qIrNmzdMSeQ1Mt01gWlB3VpA-Cygjq1-DRO4OvE9cZ1IduXbBXLBZlfxbTBzFNpg6Ur1CUKU1xl5Dofn56GIbBc5-wSUJelJJNKWiSLWpAnmSKvWK5Jum8GzSBjWW3xguerTAwEOEgpe6c-zywpY)

        - User iqbal mengek email yang diterima

    ![](https://lh7-us.googleusercontent.com/QLLzwnUOlggbKeZpSF7ffhjT2zSvG226OOES7FBVKnClmB2CJjps_MElTpn6xxcNyxlKVp3hlrySCdVOnt6p6CPK0ImsY7-1P9TxuG8btFZvS27iODc1oeKy7ynNRg4UD09YTq0IpN6nkGJIr8Nxcgo)

**Additional :** Untuk melakukan penambahan akun email anda dapat melalui terminal dengan command yang sama saat melakukan penambahan user. `sudo adduser <namauser>`. Nantinya anda akan disuruh mengisi informasi terkait user tersebut.

# Roundcube Webmail

1.  Membuat database yang nantinya digunakan untuk roundcube
    ![](https://lh7-us.googleusercontent.com/5k5EgJ6SXa2bICivQOI-TzOYoSrKnOanGyR3MBjRgLz3T2fjMtMpSw_gZ4BSWlwyHeeibhVwA_pKpmsQVPWBIrcUXXuSFtIUYnGEnjMB8HTbRxntUnD175kEpVp4HmNTg39ysc9YzMD_F1K0OZ9jYFw)

2.  Melakukan Install dan konfigurasi RoundCube - Melakukan install roundcube -->`sudo apt -y install roundcube roundcube-mysql`
    pilih no karena akan melakukan konfigurasi secara manual
    ![](https://lh7-us.googleusercontent.com/TINoKCaSQQsb2OqeetJytZPZGZBhCL6dGA3Pj8y7aDmOAJm7AFt9Bkc6UIUEhg21e2I0lFEai4hIqRXrWRsDeJpHXi5vDgyBL3rUPi4d301acKgO4ZOtRRqhEousLd6TKc0ks1q1dd6fKMpIpT8PAvY)
    ![](https://lh7-us.googleusercontent.com/BGc4usb6eCIoZ-IfCQRhufLAEzasb0IugvMqXOdhbqoZvmmgAclzLl7Mn1hFgs_97R8gomiOydAlAZCAPoorRHHPkNnUWVw3IVGbUDLdKBxdK-isLTsdus3-7-oTcQ2ccKzJSqiK1crGynNxjcehNXE)

3.  Masuk ke directory roundcube --> `cd /usr/share/dbconfig-common/data/roundcube/install`
    ![](https://lh7-us.googleusercontent.com/aIfwgSnY7bRw3EP2-acRk-0F7bUQ2wo_7THrLoZHHb3X-irR9pgYdIuUmjSi33jMILCnjDrz3mhdwtRu0qzD4XL1fS6Tlz3VoJcYwBLauvlSRrhJsubZ605khONfdIXp6-D9bCZMGEPY06jTAtJondQ)

4.  Mengimpor file mysql ke dalam database roundcube dengan menggunakan akun pengguna (-u roundcube) dan database (-D roundcube) yang sesuai. --> `sudo mysql -u roundcube -D roundcube -p < mysql`
    dan masukkan password mariaDB user roundcube (password)  
    ![](https://lh7-us.googleusercontent.com/qSGfRglKbGLYrEhwS9vb3ibpXW1bOBFZMa_FK-_RWcB2vqBjPD8NC1bpyKa-rXXXGRaPl9Isef_i-2AxB-pIFZn_t4vdpfDPPWYBoHqxhQKVkSbzgVDWWH4xjT0ec_lw6VJFZ4ykbXCv77iNIQmtDpc)

5.  Melakukan set database informasi --> `sudo nano /etc/roundcube/debian-db.php`
    ![](https://lh7-us.googleusercontent.com/GaZwkOVRMU3u63yT7hFeI2yt0mUF7p0T4tZT-aDujz6h7qc0UcCdv2ncKEXbO1prXswUY54ZQsUJnmJs16HU15my0J8US3W40ENlAX-FBbPt3vbC3locP6K71JcflGOWjVLiXKM_9tR2sGjmqWS9v1g)

6.  `sudo nano /etc/roundcube/config.inc.php`
    ![](https://lh7-us.googleusercontent.com/_ZjP-ZobdKXoVFC0nsjev0W55INBCz5XH8v4qtGaGZjmPtplNOhH6Enl3-fgjXEhMV-PXZ1qEPpYv2gt5TyA65ah77VKizCWlxhLFNMMqKDknMs478fZPjFBHzCg7WA1Y1v0mBWUepiymr5Wx7OPbvI)
    Melakukan konfigurasi imap_host, smtp_host, smtp user dan password

7.  `sudo nano /etc/apache2/conf-enabled/roundcube.conf`
    ![](https://lh7-us.googleusercontent.com/riXtwlzl_5qUwhbNoM8D3mZ6FcXbnwu6Pf-7T2IOA8FCFTa8m0_T3xzoQm1frYSuDI70o0l5UuYCdEw0LluSdI8ZP9MvcO7mRPdp0Bgtf_83F89jLjo2w9D3VjbIsAMw960JBGo18Xo_aBfuJFLrOr4)
    Mengatur agar ketika membuka path /roundcube di domain kita, akan di arahkan ke dirctory /var/lib/roundcube.

8.  Melakukan restart service apache2 --> `sudo systemctl restart apache2`
9.  Mencoba membuka roundcube di web browser (domain/roundcube)
    ![](https://lh7-us.googleusercontent.com/L0YFvvFyVgoe3fx1zZ1DHdbfCONnmjRx8_fJr892_LEn4Ez1Do_VFtP6IeWIQWbro_ztF-wBnIgawy2R_dUl1EDAsuRvOqt5dryB5DB-mSdWO0hYaZ7CkC-zgrl8MbSP5tWkLmjMCkqQPyad5DlFxdo)
    ![](https://lh7-us.googleusercontent.com/6hUxPu1aarWs1VmMUN9gL-nPumJqjJOKNTYSOukBbTS9mteTWukdl6ZEnntpaAjZ7tmU4Rr8imcsJKSYAMbqgbA_bqxxBraFZ0Q2gqqoZ55sIy3ZXQgfPvD46xJfEmElKds--oPHoJKyo_Wi7LCASFI)

10. Mencoba send email
    User 1 mengirim email ke user iqbal
    ![](https://lh7-us.googleusercontent.com/oy316tB8VPy8isUXUB6QMa0oRwuPBCi3eqNuUw29uhhG4Kt5qmL4qBLrBhBjMEqJ5fpj8XBHeDNbM7vtgHKLker6TCDGFhDzR6F_UbvwIZ_Mub47ImIxldMftH98FX8TXBsEbHlZSL4xF9LmY1zCDMI)
    Pesan berhasil terkirim :
    ![](https://lh7-us.googleusercontent.com/4rKsUrROFbxk5aAanBzqOazqy9wRA7cVDkfDUr57zrjC2iUr6lWSBC-miT2oXVywqoNAz_Y4Hxf0lRR9l0rv_JTu2-4gQrh_Zh_BioFfL4c9qT-b4GjJ99PQ1h_mPvD7MntQZOf2ayzCBELyyuiyufo)
    User iqbal mengecek email yang diterima :
    ![](https://lh7-us.googleusercontent.com/npAQ_MMpP7vt4suY4vOEur4XcSEQG-pr9UHl4rMkTHxBFyrhzfBQE1HM-dzwRIgpOf04L1V5zv2PUYHDUBxh_fFXE894er4lfLGsPFafIL5hNI3IW4e0vwW19WXCVl10nha4GdfxJOyROqotp2u3EJI)
