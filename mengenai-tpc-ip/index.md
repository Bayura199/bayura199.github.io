# Mengenal TCP/IP: Fondasi Komunikasi Jaringan


<!--more-->

<p align="center"><em>Sumber gambar: menggunakan.id</em></p>

---

## Mengenal TCP/IP: Fondasi Komunikasi Jaringan

Transmission Control Protocol/Internet Protocol (`TCP/IP`) merupakan kumpulan protokol komunikasi yang menjadi dasar dalam `pertukaran data` antar perangkat di jaringan komputer, baik jaringan lokal maupun internet.

Struktur protokol ini mendefinisikan bagaimana data dibagi, dialamatkan, dikirimkan, dirutekan, dan diterima di jaringan.

---

## Pengertian TCP/IP

TCP/IP terdiri dari dua komponen utama:

- **Transmission Control Protocol (TCP)** berfungsi `memecah data` menjadi paket-paket kecil dan memastikan agar data dikirim secara utuh dan berurutan.
- **Internet Protocol (IP)** bertugas menangani `pengalamatan` dan `pengiriman` paket ke tujuan yang benar berdasarkan alamat IP.

Keduanya bekerja sama untuk memastikan komunikasi data berjalan dengan andal.

{{< admonition info "Catatan" >}}
Setiap perangkat dalam jaringan yang menggunakan protokol IP memiliki alamat unik yang disebut `IP address`.
{{< /admonition >}}

---

## Sejarah Singkat

Konsep TCP/IP dikembangkan pada awal 1970-an oleh DARPA sebagai bagian dari proyek ARPANET. Pada tahun 1983, TCP/IP diadopsi sebagai standar protokol jaringan dan menjadi dasar dari perkembangan internet modern.

---

## Struktur Layer TCP/IP

Model TCP/IP dibagi menjadi `empat lapisan`, masing-masing dengan fungsi spesifik:

| Lapisan | Fungsi | Protokol Contoh |
|---------|--------|-----------------|
| Application | Menyediakan layanan jaringan untuk aplikasi | HTTP, FTP, SMTP |
| Transport | Mengatur komunikasi data antara host | TCP, UDP |
| Internet | Menentukan alamat dan rute pengiriman data | IP, ICMP |
| Network Access | Menangani akses fisik ke media jaringan | Ethernet, Wi-Fi |

Setiap lapisan memiliki protokol yang mendukung fungsi komunikasi pada tingkatan tersebut.

---

## Mekanisme Kerja

Saat perangkat melakukan permintaan data, prosesnya berjalan sebagai berikut:

1. Komputer tanya ke DNS: "IP-nya google.com berapa ya?"

2. Dapat IP-nya, misalnya `142.250.200.14`.
3. **TCP** membagi request itu menjadi paket-paket.
4. **IP** mengarahkan paket itu ke server Google.
5. Server Google merespons, dan datanya dirakit lagi jadi halaman web.

---

## Perbandingan TCP dan UDP

| Aspek | TCP | UDP |
|-------|-----|-----|
| Koneksi | Menggunakan koneksi (connection-oriented) | Tanpa koneksi (connectionless) |
| Keandalan | Menjamin data sampai dengan urutan yang benar | Tidak menjamin keutuhan atau urutan data |
| Penggunaan | Web, email, file transfer | Streaming, voice call, game online |

---

## Port dan Protokol dalam TCP/IP

Berikut adalah beberapa protokol umum dalam suite TCP/IP:

| Port No | Protocol | Service       | Remark                                |
|:-------:|:--------:|:-------------:|----------------------------------------|
| 21      | TCP      | FTP           | File Transfer Protocol                 |
| 23      | TCP      | Telnet        | Remote access                          |
| 25      | TCP      | SMTP          | Simple Mail Transfer Protocol          |
| 53      | UDP      | DNS           | Domain Name System                     |
| 80      | TCP      | HTTP          | Hypertext Transfer Protocol            |
| 110     | TCP      | POP3          | Post Office Protocol v3                |
| 123     | UDP      | NTP           | Network Time Protocol                  |
| 137     | TCP      | NetBIOS-ns    | NetBIOS – Name Service                 |
| 161     | UDP      | SNMP          | Simple Network Management Protocol     |
| 3128    | TCP      | HTTP - Proxy  | Web cache (default by Squid)           |
| 8080    | TCP      | HTTP - Proxy  | Web cache (custom port, umum digunakan)|

{{< admonition info "Catatan" >}}
Port `80` dan `443` adalah yang paling sering diakses pengguna secara tidak langsung saat menggunakan `web browser`. Port 8080 juga sering digunakan saat server ingin menghindari konflik dengan `port default`.
{{< /admonition >}}

---

## Kesimpulan

TCP/IP merupakan komponen fundamental dalam komunikasi data digital. Protokol ini menyediakan arsitektur terbuka yang memungkinkan berbagai jenis perangkat dan sistem untuk saling berkomunikasi, baik dalam skala lokal maupun global.

Pemahaman terhadap konsep TCP/IP menjadi langkah awal dalam mendalami jaringan komputer secara lebih lanjut.

---
