# MikroTik | Backup dan Restore Konfigurasi RouterOS


<!--more-->

Kamu tau ga kalau `backup` ataupun `restore` sistem itu `penting banget` buat ngejaga konfigurasi MikroTik kamu tetap `aman`? Bayangin aja kalau `router` tiba-tiba error, ke-reset, atau harus ganti perangkat — tanpa backup, semua setting yang udah kamu buat bisa `hilang` begitu aja.

Dengan fitur ini, kamu bisa `menyimpan` semua konfigurasi penting dan `mengembalikannya` kapan aja. Cocok banget buat jaga-jaga sebelum `upgrade` firmware, reset router, atau sekadar `clone` konfigurasi ke perangkat lain.

## Jenis Backup di MikroTik
MikroTik punya dua cara utama untuk backup:
<!-- buat tabel ya -->
Jenis Backup	Format File	Bisa Dipakai di Router Lain?	Keterangan
Backup	.backup	❌ Tidak disarankan	Backup biner (terikat hardware)
Export	.rsc	✅ Bisa	Berisi script konfigurasi (teks)

🛠️ Cara Backup
🔹 Metode 1: Backup File .backup
bash
Copy
Edit
/system backup save name=config-backup
Hasilnya: file config-backup.backup akan tersimpan di Files.

🔹 Metode 2: Export File .rsc
bash
Copy
Edit
/export file=config-export
Hasilnya: file config-export.rsc akan tersimpan di Files dan bisa dibuka dengan teks editor.

🔁 Cara Restore
🔹 Dari File .backup
bash
Copy
Edit
/system backup load name=config-backup.backup
Router akan restart otomatis setelah restore.

🔹 Dari File .rsc
Upload file .rsc ke router (via Winbox > Files).

Jalankan perintah:

bash
Copy
Edit
/import file-name=config-export.rsc
⚠️ Pastikan konfigurasi sebelumnya sudah di-reset dulu untuk mencegah konflik setting.

💡 Tips & Rekomendasi
Selalu backup sebelum:

Reset konfigurasi

Upgrade RouterOS

Menyalin konfigurasi ke router lain

Simpan file backup di tempat aman, bisa di PC, flashdisk, atau cloud.

Gunakan .rsc kalau ingin lebih fleksibel dan portabel.

✅ Kesimpulan
Backup dan restore di MikroTik itu mudah dan sangat penting untuk mencegah kehilangan konfigurasi. Gunakan jenis backup yang sesuai dengan kebutuhanmu. Jangan tunggu error baru backup ya bro, mending sedia payung sebelum hujan 😎



![Performance](/images/ram.png "Task Manager")
