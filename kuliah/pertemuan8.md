Diandita Wira Puspita
1144028
D4 Teknik Informatika 3C
Politeknik Pos Indonesia


SISTEM INFORMASI GEOGRAFIS
KONFIGURASI MAP PROXY





Pengertian Proxy
Proxy server adalah sebuah komputer server atau program komputer yang dapat bertindak sebagai komputer lainnya untuk melakukan request terhadap content dari internet.

Cara Kerja Proxy
Cara kerja proxy server adalah client yang tersambung dengan proxy dan meminta layanann tertentu seperti file, koneksi, akses web page. Proxy server yang digunakan akan mengevaluasi permintaan layanan tersebut sesuai dengan aturan filternya. Sebagai contoh, proxy server dapat menyaring traffic berdasarkan IP (Internet Protocol) address. Jika permintaan ini divalidasi oleh filternya, makanya proxy akan menyediakan apa yang diminta dan meminta dengan menyambung ke server yang diminta dan meminta layanan dari server tersebut untuk clientnya.

Konfigurasi Proxy
1.   Pertama kita install paket Squidnya

#apt-get install squid

2.      Setelah melakukan penginstalan kita masuk ke file squid.conf dengan perintah :

#nano /etc/squid/squid.conf

Lalu perintah selanjutnya kita harus mencari dan mengedit konfigurasi didalam sqiud.conf biar mudah anda dapat menekan ctrl+w (search/where is) cari tulisan dubawah ini dan diedit sesuai dengan perintah yang saya berikan.

Code:

- http_port 3128                        ( tambahkan tulisan 'transparent' di belakangnya )

- cache_mem 8 mb   ( hilangkan tanda pagar didepannya dan angka delapan diganti dengan 64 mb )  
 
- cache_swap_low 90                ( hilangkan tanda pagar didepannya )

- cache_swap_high 95               ( hilangkan tanda pagar didepannya )

- cache_mgr admin@proxy     ( hapus tanda pagar didepannya, dan ditambahkan  admin@(domain   kamu)               menjadi cache_mgr admin@(domain kamu) 

- visible_hostname  ( dan cari tulisan '# none' dibawahnya, lalu dihapus dan di tulis visible_hostname        proxy@(domain kamu)

3.      Cari tulisan acl CONNECT (ditambahkan dibawahnya)

Code:

- acl blacklist url_regex -i "/etc/squid/blacklist.txt"      ( letak file blacklist )

- acl url dstdomain "/etc/squid/url.txt"                           ( letak file url.txt )

- acl lan src 192.168.10.0/24( ip ini disesuaikan dengan ip lan yang akan berhubungan dengan client )

- http_access deny blacklist

- http_access deny url

- http_access allow lan

lalu save konfigurasi dengan menekan ctrl+o (enter) ctrl+x (enter) lalu buat file --- -blacklist.txt & url.txt dengan perintah

4.      Buka file blacklist dan url

#nano /etc/squid/blacklist.txt

( masukan tulisan yang akan diblokir misal "facebook"

#nano /etc/squid/url.txt

( masukan domain yang akan diblokir misalnya "kaskus.co.id"

5.      Lalu restart paket squid dengan perintah

#/etc/init.d/squid restart

untuk melihat settingan squid sudah benar atau belum kita dapat mengetikan perintah

#squid -z

(jika muncul "Creating Swap Directori" maka konfigurasi squid telah selesai. Jalan kembali pake squid dengan perintah).

6.      Lalu konfigurasi iptables pada rc.local untuk memforward port 80 ke port squid 3128, dengan perintah:

# nano /etc/rc.local

iptables -t nat -A PREROUTING -p tcp -d 0/0 --dport 80 -j REDIRECT --to-ports 3128


Kesimpulan
Proxy server adalah sebuah komputer server atau program komputer yang dapat bertindak sebagai komputer lainnya untuk melakukan request terhadap content dari internet.

Saran
Sebaiknya sebelum kita melakukan konfigurasi pada proxy maka kita harus belajar lebih mengenai konfigurasi proxy terlebih dahulu.

Referensi
Monitoring Proxy Server Secara Monitoring Proxy Server Secara Realtime Realtime, M.Fendi Kurniawan : 2009

Scan
https://drive.google.com/open?id=0B17w878LGlWFT1RaQzBkcFRrWTg
https://drive.google.com/open?id=0B17w878LGlWFT3htTE1yNTdaWE0 










