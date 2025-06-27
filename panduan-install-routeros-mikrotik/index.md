# Panduan Install RouterOS Mikrotik Pada Virtual Box


<!-- more -->
Belum punya RouterBoard, mau coba buat lab? Tenang, kamu tetap bisa `belajar` MikroTik tanpa harus keluar `biaya` besar. Dengan bantuan `VirtualBox` dan `RouterOS`, kamu bisa bikin `lab virtual` sendiri di laptop. Praktis banget buat latihan konfigurasi dan ngasah skill jaringan.

Di panduan ini, kamu bakal diajak `step-by-step` untuk install RouterOS MikroTik di VirtualBox, mulai dari persiapan sampai bisa login dan mulai ngoprek. Simpel, jelas, dan cocok banget buat pemula yang pengen mulai belajar dunia jaringan. 
<p align = "center"><strong>Yuk ah cusss...!!</strong></p>

---
## Persiapan

Pastikan kamu sudah memiliki hal berikut:
- Mikrotik RouterOS 

- Winbox 
- Virtual Box

{{< admonition info >}}
Kamu bisa download `RouterOS` dan `Winbox` pada laman resmi Mikrotik [disini](https://download.mikrotik.com/routeros/7.19.2/mikrotik-7.19.2.iso)
{{< /admonition>}}

---
## Instalasi
Buka virtual box lalu klik icon `New` dan isi nama, type dan version (pastikan 64-bit) lalu klik finish.
![](/images/add.png "Add VM Baru")

Lalu kita masukan `DVD ISO` mikrotik yang telah didownload tadi, jika sudah klik `Mount and Retry Boot`. Jika sudah, maka tampilan akan mengarah ke software installation. Disini kita bisa bebas memilih fitur apa saja yang ingin di download.
![](/images/software-installation.png "Software instalation")
{{< admonition info>}}
- Gunakan `arrow key` pada keyboard untuk mengarahkan
- Gunakan `space` pada keyboard untuk memilih/menghapus fitur
- Tekan `a` pada keyboard untuk pilih semua fitur 
- Tekan `i` pada keyboard untuk melakukan proses install
- Tekan `q` pada keyboard untuk membatalkan proses install
{{< /admonition>}}

Setelah tahap install selesai, dan terdapat pesan `"Press ENTER to Reboot"`, lepaskan DVD ISO yang supaya instalasi tersimpan dan tidak berulang. Pada menu Devices > Optical > Remove Disk Form... Setelah di lepas, klik `ENTER` dan tunggu sampai menampilkan laman `login`.
![](/images/forcemount-after-install.png "Lepas DVD ISO")
{{< admonition info>}}
- Jika `lupa` melepaskan DVD ISO, kamu bisa melakukan `instalasi ulang`.
- **username : admin <br> password : (kosong)**
{{< /admonition>}}

Setelah login, kamu akan diminta konfirmasi `lisensi`. Jika tidak punya, ketik `n` lalu `ENTER` dan masukan `password baru`.
![](/images/confim-lisence.png "Confirm license")

Supaya RouterOS kita bisa `remote` Winbox, tambahkan IP pada ether 1 dan lihat apakah sudah tersimpan.
```cli
ip address add address=192.168.x.x/24 interface=ether1
ip address print
```
![](/images/add-ip.png "Add Address")
Sampai disini, seharusnya Mikrotik kita sudah dapat di `remote` oleh winbox, jika `tidak terbaca` pada `Neigborsh`, login manual dengan memasukan `ip, username dan password` yang sudah dibuat.
![](/images/remote-winbox.png "Remote winbox")

---
## Hasil
Setelah login, akan terdapat informasi mengenai RouterOS. Karena RouterOS kita free, maka untuk dia berada di level 0 dan hanya berlaku selama 1 hari. Kamu bisa cek info level RouterOS pada menu `System > License`
![](/images/winbox.png "winbox")

--- 
Baca juga [Panduan Install Agent]({{< relref "../panduan-avaya/index.md" >}})

---
