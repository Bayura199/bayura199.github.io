# Mikrotik | User Login Management - Group


<!--more-->
Tahu kah kamu kalau di MikroTik kita bisa bikin `banyak user` dengan akses yang berbeda-beda? Jadi nggak semua orang harus pakai akun admin. Fitur ini berguna banget buat `membagi` tugas, `menjaga` keamanan, dan `memudahkan` pengelolaan jaringan, apalagi kalau mulai ada tim atau teman yang bantuin.

Dengan fitur ini, kita bisa bikin beberapa user login dengan `hak akses` yang berbeda-beda. Ada yang cuma bisa lihat konfigurasi, ada juga yang bisa setting, bahkan akses penuh. Gampang banget, tinggal atur aja lewat `group` yang disediain MikroTik.

Yuk, kita pelajari bareng gimana cara nambah user dan atur hak aksesnya di MikroTik!

## Apa Itu User Login di Mikrotik?
`User login` di MikroTik adalah akun yang digunakan untuk `mengakses` sistem RouterOS. Akses ini bisa dilakukan lewat:
- Winbox

- WebFig
- Terminal (SSH, Telnet, Serial)

Setiap `user` bisa dibatasi hak aksesnya menggunakan sistem `group`. `Manajemen user` dapat dilakukan dengan:
- **GROUP** --> profil pengelompokan user,` menentukan previlage` yang bisa diperoleh suatu user.
- **User** --> merupakan `login` (username & password) dari suatu user.
{{< admonition info>}}
Sesi user yang sedang melakukan koneksi ke router dapat dilihat pada menu `System > Users > Active Users`.
{{< /admonition>}}

## Pengenalan User Group di Mikrotik
MikroTik menyediakan 3 group default yang sudah punya hak akses masing-masing:

| Nama Groups | Akses yang Diberikan                                               | Cocok untuk         |
|:-----------:| ------------------------------------------------------------------ |:-------------------:|
| full        | Semua akses penuh (termasuk reboot, update, firewall)              | Admin jaringan      |
| write       | Akses untuk mengedit konfigurasi, tapi tidak bisa ganti user/group | Teknisi             |
| read        | Hanya bisa melihat konfigurasi, tidak bisa mengubah                | Monitoring, Auditor |

Groups dapat dilihat pada menu `system > user list > Groups`

![](/images/grups.png "Groups")

Berikut adalah `keterangan` dari policy/kebijakan terhadap group.

| Policy        | Keterangan                                                                    |
|:-------------:| ----------------------------------------------------------------------------- |
| **local**     | Untuk akses via terminal langsung (console) di perangkat (bukan remote).      |
| **telnet**    | Mengizinkan akses ke MikroTik via `Telnet`.                                 |
| **ssh**       | Mengizinkan login ke MikroTik lewat protokol `SSH`.                         |
| **ftp**       | Mengizinkan akses file via `FTP` ke router.                                 |
| **reboot**    | Bisa melakukan `reboot (restart)` perangkat.                                |
| **read**      | Hanya bisa `melihat konfigurasi`, tidak bisa mengubah apa pun.              |
| **write**     | Bisa mengubah konfigurasi, `tapi tidak bisa ubah user/group`.               |
| **policy**    | Bisa `mengatur user`, `group`, dan `policy`, termasuk buat user baru.           |
| **test**      | Bisa menjalankan perintah `test atau tool diagnose` di MikroTik.            |
| **winbox**    | Mengizinkan login dan akses lewat aplikasi `Winbox`.                        |
| **password**  | Bisa `mengubah password` user (termasuk miliknya sendiri).                  |
| **web**       | Bisa mengakses MikroTik lewat `WebFig` (web-based GUI).                     |
| **sniff**     | Bisa pakai tool `Packet Sniffer` di MikroTik.                               |
| **sensitive** | Bisa melihat info sensitif seperti `secret, password, dan log detail`.      |
| **api**       | Mengizinkan akses MikroTik lewat `API` (buat integrasi atau scripting).     |
| **romon**     | Bisa mengaktifkan dan pakai fitur `RoMON` (Router Management over Network). |

{{< admonition info>}}
Group secara `default` telah mempunyai `kebijakan` terhadap `hak akses` sistem, namun disini kamu diperbolehkan melakukan `customize` hak akses sendiri sesuaikan kebutuhan. 
- Centang/hapus centang untuk melakukan filter akses sistem.
{{< /admonition>}}


## Tambah User 
Kamu juga bisa `menambahkan user` dengan `group tertentu` untuk mengakses sistem, sebagai contoh disini saya akan menambahkan akun untuk `anak magang` yang hanya dapat `melihat sistem` dan hanya dapat `login dengan IP` tertentu. 
![](/images/user-add.png "Users add")

## Kesimpulan
Dengan fitur `User & Group` di MikroTik, kamu bisa mengatur siapa yang bisa `mengakses router` dan seberapa besar `kontrol` yang mereka punya. Ini penting banget untuk `menjaga` keamanan dan efisiensi pengelolaan jaringan, apalagi kalau sudah melibatkan banyak orang.

Jangan lupa, selalu sesuaikan hak akses dengan kebutuhan. Jangan kasih akses `full` ke sembarang orang ya ges ya..!
