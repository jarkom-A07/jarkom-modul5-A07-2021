**PRAKTIKUM JARKOM MODUL 5**

Kelompok A07:

1.  Arkan Aulia Farhan (05111940000128)

2.  Muchamad Maroqi Abdul Jalil (05111940000143)

3.  Syamil Difaull Haq Sukur (05111940000196)

Soal praktikum:

Setelah kalian mempelajari semua modul yang telah diberikan, Luffy ingin
meminta bantuan untuk terakhir kalinya kepada kalian. Dan kalian dengan
senang hati mau membantu Luffy.

(A) Tugas pertama kalian yaitu membuat topologi jaringan sesuai dengan
    rancangan yang diberikan Luffy dibawah ini:

![](./images/media/image1.png)
Keterangan : Doriki adalah DNS Server

Jipangu adalah DHCP Server
Maingate dan Jorge adalah Web Server
Jumlah Host pada Blueno adalah 100 host
Jumlah Host pada Cipher adalah 700 host
Jumlah Host pada Elena adalah 300 host
Jumlah Host pada Fukurou adalah 200 host

(B) Karena kalian telah belajar subnetting dan routing, Luffy ingin
    meminta kalian untuk membuat topologi tersebut menggunakan teknik
    CIDR atau VLSM. setelah melakukan subnetting,

(C) Kalian juga diharuskan melakukan Routing agar setiap perangkat pada
    jaringan tersebut dapat terhubung.

(D) Tugas berikutnya adalah memberikan ip pada subnet Blueno, Cipher,
    Fukurou, dan Elena secara dinamis menggunakan bantuan DHCP server.
    Kemudian kalian ingat bahwa kalian harus setting DHCP Relay pada
    router yang menghubungkannya.

1.  Agar topologi yang kalian buat dapat mengakses keluar, kalian
    diminta untuk mengkonfigurasi Foosha menggunakan iptables, tetapi
    Luffy tidak ingin menggunakan MASQUERADE.

2.  Kalian diminta untuk mendrop semua akses HTTP dari luar Topologi
    kalian pada server yang merupakan DHCP Server dan DNS Server demi
    menjaga keamanan.

3.  Karena kelompok kalian maksimal terdiri dari 3 orang. Luffy meminta
    kalian untuk membatasi DHCP dan DNS Server hanya boleh menerima
    maksimal 3 koneksi ICMP secara bersamaan menggunakan iptables,
    selebihnya didrop.

Kemudian kalian diminta untuk membatasi akses ke Doriki yang berasal
dari subnet Blueno, Cipher, Elena dan Fukuro dengan beraturan sebagai
berikut

4.  Akses dari subnet Blueno dan Cipher hanya diperbolehkan pada pukul
    07.00 - 15.00 pada hari Senin sampai Kamis.

5.  Akses dari subnet Elena dan Fukuro hanya diperbolehkan pada pukul
    15.01 hingga pukul 06.59 setiap harinya.

Selain itu di reject

6.  Karena kita memiliki 2 Web Server, Luffy ingin Guanhao disetting
    sehingga setiap request dari client yang mengakses DNS Server akan
    didistribusikan secara bergantian pada Jorge dan Maingate

Luffy berterima kasih pada kalian karena telah membantunya. Luffy juga
mengingatkan agar semua aturan iptables harus disimpan pada sistem atau
paling tidak kalian menyediakan script sebagai backup.

Jawaban:

**TOPOLOGI**

Membuat topologi sesuai gambar

![](./images/media/image23.png)

**SUBNETTING**

Melakukan Subnetting pada topologi yang dibuat

![](./images/media/image14.png)

**KONFIGURASI IP**

Melakukan konfigurasi IP pada Foosha

![](./images/media/image13.png)

Melakukan konfigurasi IP pada Water7

![](./images/media/image11.png)

Melakukan konfigurasi IP pada Guanhao

![](./images/media/image25.png)
Melakukan konfigurasi IP pada Doriki

![](./images/media/image3.png)

Melakukan konfigurasi IP pada Jipangu

![](./images/media/image8.png)

Melakukan konfigurasi IP pada Blueno

![](./images/media/image6.png)

Melakukan konfigurasi IP pada Cipher

![](./images/media/image21.png)

Melakukan konfigurasi IP pada Elena

![](./images/media/image18.png)

Melakukan konfigurasi IP pada Fukuro

![](./images/media/image4.png)

Melakukan konfigurasi IP pada Jorge

![](./images/media/image9.png)

Melakukan konfigurasi IP pada Maingate

![](./images/media/image17.png)

**DHCP**

konfigurasi DHCP Server (Jipangu)

![](./images/media/image22.png)

![](./images/media/image27.png)

Konfigurasi DHCP Relay (Water7, Foosha, Guanhao)

![](./images/media/image12.png)

1.  **Memberikan akses keluar topologi**

Menjalankan perintah iptables di Foosha

![](./images/media/image7.png)

Melakukan testing di Cipher

![](./images/media/image15.png)

2.  **Mendrop semua akses HTTP dari luar**

Menjalankan perintah iptables di Doriki dan Jipangu

![](./images/media/image5.png)

Melakukan testing pada Cipher

![](./images/media/image24.png)

3.  **Membatasi akses sebanyak 3 kali ke Doriki dan Jipangu**

Menjalankan script pada Jipangu dan Doriki

![](./images/media/image2.png)

Melakukan testing pada 4 client sekaligus

Ketika 3 ping bisa

![](./images/media/image29.png)

4 ping, tidak bisa

![](./images/media/image30.png)
