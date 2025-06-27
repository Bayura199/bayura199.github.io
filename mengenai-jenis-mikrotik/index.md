# Mengenal Jenis MikroTik | RouterOS - RouterBOARD | Apa Bedanya dan Kapan Digunakan?


<!-- more -->

MikroTik memiliki dua jenis utama yang sering digunakan dalam dunia jaringan komputer, yaitu RouterOS dan RouterBOARD. Keduanya memainkan peran penting dalam manajemen jaringan, namun memiliki fungsi dan bentuk yang berbeda. Untuk memahami perbedaan serta kapan sebaiknya menggunakan salah satu dari keduanya, mari kita bahas satu per satu.

## RouterOS Mikrotik 
RouterOS adalah `sistem operasi` berbasis `Linux` yang dikembangkan oleh MikroTik. Sistem operasi ini dirancang khusus untuk keperluan routing, firewall, bandwidth management, VPN, dan berbagai fitur jaringan lainnya. RouterOS bisa diinstal di komputer biasa (PC) dan memiliki fitur yang `melebihi` sebuah `“router”`.

### Fitur Unggulan RouterOS:
- User Management (DHCP, Hotspot, Radius, dll).

- Routing (RIP, OSPF, BGP, RIPng, OSPF V3).
- Firewall & NAT (fully-customized, linux based).
- QoS/Bandwidth limiter (fully customized, linux based).
- Tunnel (EoIP, PPTP, L2TP, PPPoE, SSTP, OpenVPN).
- Real-time Tools (Torch, watchdog, mac-ping, MRTG, sniffer).

### Mengenal Sistem Lisensi RouterOS
RouterOS `tidak bisa` digunakan secara penuh tanpa lisensi. MikroTik menggunakan `sistem lisensi` berbayar yang dibagi menjadi beberapa level. Masing-masing level memiliki `batasan` dan `fitur` yang berbeda.

| Level Number                  | 0 (Trial Mode) | 1 (Free Demo)          | 3 (WISP CPE) | 4 (WISP)  | 5 (WISP)  | 6 (Controller) |
|-------------------------------|:--------------:|:-------------:         |:------------:|:---------:|:---------:|:--------------:|
| **Price**                     | no key         | registration required  | not for sale | $45       | $95       | $250           |
| **Wireless AP mode (PtMP)**   | 24h trial      | -                      | no           | yes       | yes       | yes            |
| **PPPoE tunnels**             | 24h trial      | 1                      | 200          | 200       | 500       | unlimited      |
| **PPTP tunnels**              | 24h trial      | 1                      | 200          | 200       | 500       | unlimited      |
| **L2TP tunnels**              | 24h trial      | 1                      | 200          | 200       | 500       | unlimited      |
| **OVPN tunnels**              | 24h trial      | 1                      | 200          | 200       | unlimited | unlimited      |
| **EoIP tunnels**              | 24h trial      | 1                      | unlimited    | unlimited | unlimited | unlimited      |
| **VLAN interfaces**           | 24h trial      | 1                      | unlimited    | unlimited | unlimited | unlimited      |
| **Queue rules**               | 24h trial      | 1                      | unlimited    | unlimited | unlimited | unlimited      |
| **HotSpot active users**      | 24h trial      | 1                      | 1            | 200       | 500       | unlimited      |
| **User manager sessions**     | 24h trial      | 1                      | 10           | 20        | 50        | unlimited      |
| **Bonding interfaces**        | 24h trial      | 1                      | unlimited    | unlimited | unlimited | unlimited      |
| **RADIUS**                    | 24h trial      | -                      | unlimited    | unlimited | unlimited | unlimited      |

{{< admonition info "Info Gaiss">}}
- Setelah RouterOS diaktifkan dengan lisensi, kamu bisa menggunakannya `selamanya` tanpa batas waktu.
- Semua lisensi mendukung `penggunaan interface sebanyak apapun`, seperti Ethernet, wireless, VLAN, dll.
- `Satu lisensi` hanya bisa digunakan untuk `satu perangkat `atau instalasi RouterOS saja. Tidak bisa dipakai di banyak perangkat.
- Kamu bebas `update versi` RouterOS kapan saja secara `gratis`, `kecuali` lisensi demo (`Level 1`), upgrade tidak bisa dilakukan mulai versi 7.8 ke atas.
{{< /admonition>}}

### Dimana bisa mendapatkan RouterOS?
Kamu bisa mengunduh RouterOS pada laman resmi [Mikrotik](https://mikrotik.com/download), lalu cari RouterOS v7 `Stable` bagian `X86 CD Image`.
![](/images/x86-download.png "RouterOS - CD Image")
<br>

## RouterBOARD Mikrotik
RouterBOARD adalah `perangkat keras` (`hardware`) yang diproduksi oleh MikroTik dan sudah terinstal RouterOS di dalamnya. RouterBOARD tersedia dalam berbagai model dan ukuran, mulai dari yang kecil seperti RB941 (hAP Lite) untuk kebutuhan rumahan, hingga CCR (Cloud Core Router) untuk kebutuhan jaringan skala besar.

### RouterBOARD - Type 
RouterBoard memiliki sistem kode tertentu, contohnya
![](/images/rb.png "RouterBoard - Type")
> Kode lain ada di belakang type seperti
> - **U** dilengkapi port USB
> - **A** - Advanced, biasanya diatas lisensi level 4
> - **H** - Hight Performance, processor lebih tinggi
> - **R** - dilengkapi wireless card embedded.
> - **G** - dilengkapi port ethernet Gigabit
> - **2nD** – dual channel

### Keunggulan RouterBOARD MikroTik
RouterBOARD adalah perangkat jaringan yang dirancang khusus oleh MikroTik, dan sudah dilengkapi dengan sistem operasi RouterOS di dalamnya. Inilah beberapa keunggulan utama yang membuat RouterBOARD jadi pilihan favorit banyak teknisi jaringan:
- **Desain Ringkas dan Hemat Daya** <br>
RouterBOARD memiliki bentuk yang kompak dan minimalis, sehingga tidak memakan banyak ruang saat dipasang di meja kerja, rak server, atau di dinding. Selain itu, konsumsi dayanya sangat rendah, cocok untuk penggunaan 24 jam non-stop tanpa khawatir boros listrik.

- **Tidak Perlu Instalasi Sistem Operasi** <br>
Semua RouterBOARD sudah langsung dilengkapi dengan RouterOS yang pre-installed. Artinya, kamu tidak perlu lagi repot-repot melakukan instalasi manual—tinggal nyalakan, konfigurasi, dan langsung bisa digunakan.

- **Plug and Play** <br>
RouterBOARD dirancang untuk kemudahan penggunaan. Kamu cukup menyambungkannya ke listrik dan jaringan, lalu konfigurasi lewat Winbox, WebFig, atau terminal. Sangat cocok untuk teknisi lapangan yang butuh kecepatan dan efisiensi.

- **Stabil untuk Penggunaan Jangka Panjang** <br>
Karena merupakan perangkat khusus jaringan, RouterBOARD punya stabilitas tinggi. Tidak seperti PC yang rawan panas atau crash, RouterBOARD bisa berjalan terus-menerus tanpa gangguan, bahkan dalam lingkungan berat sekalipun.

- **Varian Port dan Fitur Sesuai Kebutuhan** <br>
MikroTik menyediakan banyak model RouterBOARD, dari yang kecil seperti hAP Lite untuk kebutuhan rumahan, hingga CCR (Cloud Core Router) untuk jaringan berskala besar. Masing-masing dilengkapi fitur dan jumlah port yang bisa disesuaikan dengan skala penggunaan.

<br>

## Kapan Harus Menggunakan RouterOS vs RouterBOARD

| Situasi / Kebutuhan| Gunakan RouterOS| Gunakan RouterBOARD                                                                  |
|----------------------------------------------------------|-----------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|
| Ingin router dengan spesifikasi tinggi & bisa dikustom| ✅ Bisa instal di PC/server dengan spesifikasi sendiri                            | ❌ Hardware sudah tetap, tidak bisa dikustom                                          |
| Punya perangkat lama/PC bekas                            | ✅ Bisa dimanfaatkan untuk jadi router dengan RouterOS                            | ❌ Tidak relevan, karena RouterBOARD adalah perangkat baru                           |
| Belajar jaringan atau simulasi lab                       | ✅ Sangat cocok untuk eksperimen dan pelatihan                                     | ❌ Kurang fleksibel untuk simulasi yang kompleks                                     |
| Ingin solusi cepat & langsung pakai                     | ❌ Perlu instalasi dan konfigurasi dari awal                                      | ✅ Sudah siap pakai (plug & play)                                                    |
| Stabil untuk penggunaan jangka panjang                   | ✅ Tergantung hardware PC                                                         | ✅ Dirancang khusus untuk tahan lama & stabil                                        |
| Gunakan di lingkungan virtual (VM, cloud, dll.)          | ✅ Bisa dijalankan di VirtualBox, Proxmox, VMware                                 | ❌ Tidak bisa dijalankan di lingkungan virtual                                       |
| Butuh instalasi ringan dan hemat daya                   | ❌ PC biasanya lebih boros daya                                                   | ✅ Sangat hemat daya                                                                 |
| Tidak ingin repot urus lisensi                          | ❌ Harus beli lisensi sesuai kebutuhan                                            | ✅ Lisensi sudah termasuk dalam perangkat                                            |
| Digunakan di rumah, kantor kecil, atau ISP               | ✅ Bisa, tapi butuh hardware yang sesuai                                           | ✅ Tersedia banyak model sesuai skala jaringan                                       |
| Penggunaan mobile / lapangan                             | ❌ Tidak praktis, butuh monitor & keyboard                                        | ✅ Ukuran kecil & mudah dibawa                                                       |

<br>

## Kesimpulan
MikroTik menyediakan dua solusi utama dalam dunia jaringan: `RouterOS` sebagai `sistem operasi` yang fleksibel dan bisa diinstal pada perangkat sendiri, serta `RouterBOARD`sebagai `perangkat keras` siap pakai yang sudah dilengkapi dengan RouterOS.

`Pemilihan` antara keduanya sangat bergantung pada `kebutuhan` jaringan, tingkat fleksibilitas, serta anggaran yang di miliki. Jika ingin kontrol penuh, fleksibilitas tinggi, dan sudah terbiasa dengan instalasi manual, maka RouterOS adalah pilihan yang tepat. Namun jika mencari perangkat yang praktis, efisien, dan siap digunakan tanpa ribet, maka RouterBOARD lebih cocok untukmu.

Baik RouterOS maupun RouterBOARD, `keduanya` menawarkan fitur-fitur canggih dan andal untuk membangun jaringan yang stabil, aman, dan optimal—mulai dari rumah, kantor kecil, sekolah, hingga lingkungan enterprise dan ISP.

Dengan MikroTik, kamu punya solusi yang lengkap dan bisa disesuaikan dengan segala skala penggunaan.

{{< admonition "tip">}}
RouterOS bisa dijalankan di berbagai platform virtualisasi loh gais, seperti 
- VirtualBox

- GNS3 (Graphical Network Simulator 3)
- VMware Workstation/ESXi
- Proxmox VE (KVM/QEMU)
- Cloud VPS (Azure, GCP, AWS, dll.)
<br>

<p align="center"><strong>So, yuk belajar networking..!</strong></p>

{{< /admonition>}}

Baca juga : 
<br>
[Panduan Install RouterOS Mikrotik Pada Virtual Box]({{< relref "../panduan-install-RouterOS-Mikrotik/index.md" >}})
<br>
[Panduan Install RouterOS Mikrotik Pada Virtual Box]({{< relref "../panduan-install-RouterOS-Mikrotik/index.md" >}})

