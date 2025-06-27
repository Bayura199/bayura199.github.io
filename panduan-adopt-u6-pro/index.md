# Panduan Adopt & Setting Access Point UniFi U6-Pro ke UniFi Controller

Perangkat UniFi U6-Pro adalah access point dari `Ubiquiti` yang mendukung <a href="https://www.intel.co.id/content/www/id/id/gaming/resources/wifi-6.html" target="_blank">WiFi 6</a> dan banyak digunakan di jaringan perusahaan atau institusi. Untuk bisa mengelola dan memantau perangkat ini, kita perlu melakukan proses `adoption` ke UniFi Controller (UniFi Network Application).

Berikut langkah-langkahnya secara urutan teknis dan lengkap:

---

<!--more-->

### Pastikan Jaringan Tersedia
Sebelum melakukan proses adopt, pastikan hal ini sudah tersedia:
1. Sudah tersedia `UniFi Controller` berjalan di `server`.
2. `Server Controller` dan UniFi U6-Pro berada dalam `satu` jaringan (subnet).
3. Tersedia `switch PoE` untuk memberi daya ke U6-Pro (karena U6-Pro membutuhkan power via Ethernet). Jika tidak ada, gunakan PoE Injector / PoE Adapter.
{{< admonition info "Alur Koneksi PoE Injector" >}}
```
[Switch Biasa] --LAN--> [PoE Injector] --PoE--> [UniFi U6-Pro]
                               ↑
                         Colok listrik
```
{{< /admonition >}}

---
### Hubungan UniFi U6-Pro ke Switch dan Cek IP
1. `Colokkan` kabel LAN dari U6-Pro ke port PoE switch atau PoE Injector yang `terkoneksi` dengan jaringan `LAN` yang memiliki DHCP Server aktif.
{{< admonition info>}}
Tujuannya agar perangkat UniFi bisa `mendapatkan` IP address secara dhcp/otomatis
{{< /admonition >}}
2. Cek IP Address via `CMD`
{{< admonition info "CMD">}}
```
arp -a
```
Contoh hasil
![](/images/arp-a.png "CMD")
{{< /admonition>}}

---
### Akses UniFi via SSH (Putty)
Akses UniFi via SSH digunakan untuk `mengarahkan` perangkat ke `UniFi Controller` (set-inform), melakukan reset, pengecekan status, dan lain sebagainya. Dalam kasus ini, kita akan `set-inform`.
1. Buka aplikasi `Putty`, isi `IP` dari U6-Pro (misalnya 192.168.43.47) dan port SSH default `22`, lalu Open.
![](/images/putty.png "SSH")
2. Setelah terkoneksi, login menggunakan `akun default` UniFi 
{{< admonition note "Akun Default">}}
username : **ubnt** <br>
password : **ubnt**
{{< /admonition>}}
3. Masukan perintah `inform` dengan ketik
{{< admonition tip "Putty" >}}
```ssh
set-inform http://192.168.1.1:8080/inform
```
Gantilah 192.168.1.1 dengan IP dari UniFi Network Controller (UniFi Manager) kamu.
Perintah ini akan mengarahkan perangkat untuk mengirimkan permintaan adoption ke controller.
{{< /admonition>}}

---
### Setting UniFi di Web UniFi Controller
Setelah proses adopt via ssh dilakukan, lakukan:
1. `Akses` web UniFi Manajer melalui browser. 
```
http://192.168.1.1:8080
```
2. Login dengan akun `admin`
3. Pada menu `network`, akan tersedia UniFi yang telah mengirimkan request adopt via ssh. Klik adopt. 
![](/images/network-u6.png "UniFi Manager")
4. Setelah perangkat berhasil di-adopt, kamu bisa mengubah `settingan` perangkat UniFi agar bisa lebih dikenali. Adapun `saran` setting perangkat antara lain:
{{< admonition tip "Setting Perangkat" >}}
- **Nama Perangkat** --> Guna mempermudah manajemen/monitoring AP
-  **IP menjadi static** (set ip, subnet, gateway, DNS) --> Agar lebih stabil dan mencegah loss IP
{{< /admonition>}}

---
### Done~~
