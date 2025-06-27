# Panduan Setup dan Permasalahan Umum Avaya 1608-I  (IP Phone seri 1600)

Avaya 1608-I adalah IP Phone seri 1600 yang umum digunakan untuk sistem komunikasi VoIP berbasis `Avaya Communication Manager` atau IP Office. Pada artikel kali ini akan membahas panduan `setup` perangkat Avaya 1608-I, mulai dari langkah awal instalasi hingga konfigurasi dasar yang perlu diperhatikan. Selain itu, artikel ini juga akan mengulas beberapa `permasalahan umum` yang sering terjadi pada perangkat Avaya 1608-I, seperti error jaringan, konflik IP, tidak bisa login, lengkap dengan solusi praktis untuk mengatasinya.

<!--more-->
## Persiapan Setup
Menyiapkan `perangkat` dan `jaringan` sebelum proses konfigurasi.
1. Siapkan `kabel` LAN yang sudah terhubung ke `switch` jaringan dan adaptor untuk Avaya.
2. Pastikan terdapat `IP kosong` untuk IP Avaya (jika menggunakan static).
3. Ketahui `IP server` (CallSelv), `IP Router`, `Extention` dan `password.`
{{< admonition info "Cek Ip Kosong">}}
Anda bisa menggunakan perintah di `CMD` untuk melihat `IP kosong` dalam jaringan anda.
```
arp -a
```
Setelah itu ping IP yang tidak terdaftar dan pastikan **`RTO/Destination host unreachable`**. Hal ini menandakan IP Kosong/belum terpakai. `Konfirmasi` kepada `pihak terkait` untuk menggunakan IP yang dipilih sebagai IP Avaya.
{{< /admonition>}}

---
## Masuk ke Boot Menu dan Setup
Setelah persiapan telah selesai, pastikan avaya sudah terhubung dengan jaringan.
{{< admonition info "Topologi" >}}
```
[Switch] --LAN--> Avaya
                    ↑
             Colokan Listrik
```
{{< /admonition>}}
Lalu masuk ke mode pengaturan awal untuk Setup Avaya
1. Saat `layar menyala` dan muncul tulisan `Press to program`, tekan tombol `*`.
2. Saat diminta password, masukan `*27238*` (default type 1608-I), lalu tekan `#`.
{{< admonition info >}}
`*` digunakan untuk:
- Masuk ke mode setup (Boot Menu),
- Hapus/Edit,
- Back/Kembali,
- Memasukan Titik,
- Mute Mikrofon (mode panggilan).

`#` digunakan untuk:
- Konfirmasi/Ok/Enter,
- Next step,
- Simpan dan Setuju,
- Dial number (ketik 1001# --> memulai panggilan ke ekstensi 1001).
{{< /admonition>}}
3. Pilih `IP Addressing` dan pilih `Static` lalu isikan:
- IP Address (yang sudah didapat (arp-a)).
- IP Server (Callselv) --> Alamat IP Office (`server avaya`).
- IP Router.
- Subnet Mask.
- Default Gateway.
- Extension Number dan Password.
4. Next sampai terdapat pesan `Save and Restart?` (Yes/No).

---
## Done~~
{{< figure src="/images/setup-done.jpg" width="300px" >}}
<br>

---
## Permasalahan Umum Dan Solusi
### 1. Stuck di “Discovering…”
**Penyebab** : DHCP server tidak tersedia/kabel LAN ruksak/port switch mati.
<br>
`Inti penyebab` : Akses ke server terputus.

**Solusi** :  
- Ping `IP Router`, jika `RTO` maka permasalahan ada pada `Router` --> `Hubungi` pihak terkait.
- Ping `IP Router`, jika `TTL` maka permasalahan ada pada `LAN` yang digunakan --> `Ganti` kabel LAN.

### 2. Address/IP Conflict
{{< figure src="/images/ip-conflict.jpg" width="300px" >}}
**Penyebab** : Terdapat `2 perangkat` yang memakai `IP sama.` <br>
**Solusi** : `Ganti IP` pada perangkat yang bermasalah.
{{< admonition note "Catatan">}}
Langkah-langkah ganti IP `sama` seperti saat akan setup avaya.
{{< /admonition>}}

### 3. Tidak Bisa Login ke Server, Extension Kosong

**Penyebab** : Extension salah, Konfigurasi tidak sesuai.
<br>
**Solusi** : Pastikan Extension, password, alamat server benar.


