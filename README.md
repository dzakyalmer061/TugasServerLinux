# TugasServerLinux

Nama : Dzaky Almer Antoriq

NIM : 09011282328103

Kelas : SK3A

Mata Kuliah : Sistem Operasi

# Pengertian SSH

SSH atau Secure Shell merupakan protokol jaringan yang digunakan untuk mengakses dan mengelola perangkat atau sistem secara aman melalui jaringan ,terutama server yang menjalankan sistem operasi berbasis linnux. SSH juga memungkinkan pengguna untuk mengakses antarmuka command-line pada server jarak jauh,yang memberikan kontrol penuh atas sistem tersebut seolah sedang di akses secara langsung.

# Prosedur pemasangan

**1. Mengecek alamat IP Host server.**

Untuk mengecek ip addres kita bisa menggunakan command $ifconfig

![Cuplikan layar 2024-10-29 090849](https://github.com/user-attachments/assets/79ab7546-1df3-4182-a67c-b759a2c4ddab)

**2. Mengecek open port di host server**
dengan command $nmap pada linux kita dapat melihat open port yang ada pada host server

![Cuplikan layar 2024-10-29 091825](https://github.com/user-attachments/assets/3e5da2fa-8d93-4663-834b-2b6f5336366c)

**3. Melakukan konek pada port**

untuk melakukan koneksi pada port kita bisa menggunakan protokol SSH dan melukan koneksi ke port default port 22 dengan command $ssh -p 22

![Cuplikan layar 2024-10-29 092137](https://github.com/user-attachments/assets/1fed9efc-cb05-4e65-8a90-272f6234cd39)

![Cuplikan layar 2024-10-29 092153](https://github.com/user-attachments/assets/5fd78ae7-c7b2-4a69-9bf5-70d320ea14a4)

**4. Mengkonfigurasikan port 40 ke host server**

untuk memodifikasi port ke 40,dapat di gunakan command $sudo su untuk masuk ke mode super user 

**5. Modifikasi ssh_config**

untuk memodifikasi ssh_config kita akan mengcopy file ssh_config terlebih dahulu,lalu kita bisa menggunakan command 

 $ cp/etc/ssh/ssh_config /etc/ssh/ssh_config.backup

 dan

 $ nano /etc/ssh_config
 
ketika membuka file ssh_config ubah port 22 menjadi 40

![Cuplikan layar 2024-10-29 092352](https://github.com/user-attachments/assets/f6e250b0-8137-4a58-b301-5389a92a5087)

setelah mengubah port menjadi 40 maka kita harus mengaktifkan perubahan pada port sistem dengan command berikut :

$ufw allow 40/tcp

$ufw enable

![Cuplikan layar 2024-10-29 092723](https://github.com/user-attachments/assets/f0cc3198-99af-45d2-8189-0ccb86e4b862)

**6. Pemeriksaan Status dan Restart Layanan SSH**

![Cuplikan layar 2024-10-29 092846](https://github.com/user-attachments/assets/87de32ed-cfa5-4ed5-9ec4-b98d06ecb8a8)

**7. Mengkoneksikan dengan port 40**

untuk mengkoneksikannya kita bisa menggunakan command $ssh -p 40 usernamehost@ipaddress

![Cuplikan layar 2024-10-29 093051](https://github.com/user-attachments/assets/44d0e7da-ddca-4642-8822-7c176983ad51)

![Cuplikan layar 2024-10-29 093112](https://github.com/user-attachments/assets/c2e59414-ee75-49cd-8580-b79a05983cff)
