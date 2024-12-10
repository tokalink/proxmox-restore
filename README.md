# proxmox-restore
Kondisi jika Hdd Host error dan ingin mengembalikan hdd vm
Langkah 3: Tambahkan Storage LVM di Proxmox GUI
Masuk ke GUI Proxmox.

Tambahkan Storage:

Datacenter > Storage > Add.

Pilih LVM dan isikan detail volume group (VG) yang terdeteksi, misalnya HDD01.

Langkah 4: Verifikasi Storage di Proxmox
Setelah storage LVM ditambahkan, verifikasi bahwa volume logis sudah tersedia di Proxmox.

```
lvscan <br>
vgscan <br>
vgchange -ay <br>
<br>
lvdisplay <br>
<br>
lvdisplay /dev/HDD01/vm-302-disk-0
<br>
qm set 302 --scsi0 /dev/HDD01/vm-302-disk-0

```
<br>
