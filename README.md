
# About Debian 12

Debian adalah sebuah sistem operasi berbasis Linux yang berisi perangkat lunak bebas dan sumber terbuka untuk komputer. Debian, yang dikembangkan oleh komunitas sukarelawan dari seluruh dunia, menekankan kebebasan perangkat lunak, kestabilan, dan keamanan. Sistem manajemen paket Debian, yang dikenal sebagai "dpkg" dan "APT", menawarkan berbagai paket perangkat lunak yang dapat diinstal dan dikelola.


## Proses Booting

Proses booting adalah proses awal saat sebuah komputer atau perangkat sistem dimulai dan memuat sistem operasi serta perangkat lunak yang diperlukan untuk menjalankan perangkat tersebut. Berikut adalah langkah-langkah umum dalam proses booting sebuah komputer:

1. Power On: 
Komputer dinyalakan atau direstart.

2. POST (Power-On Self-Test): 
Pada tahap ini, BIOS (Basic Input/Output System) atau UEFI melakukan beberapa pemeriksaan untuk memastikan bahwa perangkat keras dasar berfungsi dengan baik. Ini termasuk menguji memori, menguji perangkat keras seperti drive disk, keyboard, dan mouse, serta mengecek keberadaan dan keutuhan BIOS atau UEFI itu sendiri.

3. Inisialisasi Perangkat Keras: 
Setelah melewati POST dengan berhasil, BIOS atau UEFI mulai menginisialisasi perangkat keras seperti kartu grafis, disk drive, dan perangkat lainnya. Proses ini melibatkan pengenalan perangkat keras yang terpasang dan menyediakannya untuk sistem operasi untuk digunakan.

4. Boot Loader: 
Setelah inisialisasi perangkat keras selesai, BIOS atau UEFI mencari boot loader di media penyimpanan yang telah ditentukan, biasanya hard drive atau SSD. Jika ada beberapa sistem operasi yang terinstal, pemuat boot, seperti GRUB (Grand Unified Bootloader) untuk sistem Linux, memungkinkan pengguna untuk memilih sistem operasi mana yang akan dimuat. Selanjutnya, loader boot memuat kernel sistem operasi yang dipilih ke dalam memori.

5. Kernel Pemuatan: 
Kernel sistem operasi, seperti kernel Linux, dimuat ke dalam memori setelah boot loader memilih sistem operasi yang akan dimuat. Manajemen perangkat keras, alokasi sumber daya, dan menjalankan berbagai tugas yang diperlukan untuk menginisialisasi sistem adalah semua tanggung jawab kernel.

6. Process Init: 
Proses inicialisasi diluncurkan setelah kernel dimuat. Proses init, yang berjalan setelah kernel, bertanggung jawab untuk menginisialisasi sistem dan menjalankan proses yang diperlukan.

7. Ruang Pengguna: 
Setelah proses init selesai, sistem operasi memulai menjalankan berbagai proses di ruang pengguna. Ini termasuk layanan sistem, program pengguna, dan, jika diperlukan, antarmuka grafis.

8. Prompt Login atau GUI: 
Pada akhirnya, pengguna dapat melihat prompt login untuk sistem berbasis teks atau antarmuka grafis (GUI) jika diaktifkan, dan memulai sesi dengan masuk ke dalam sistem.
## Installation
1. Masuk ke link downloaad virtualbox dan klik download
![App Screenshot](img/install-vm/1.jpeg)

2. Pilih sesuai **Sistem Oprasi Device** anda,
![App Screenshot](img/install-vm/2.jpeg)

3. Buka **VirtualBox** anda, dan klik **yes**
![App Screenshot](img/install-vm/3.jpeg)

4. klik **Next**
![App Screenshot](img/install-vm/4.jpeg)

5. Lanjut Klik **Instal** 
![App Screenshot](img/install-vm/5.jpeg)

6. Tunggu hingga proses selesai
![App Screenshot](img/install-vm/6.jpeg)

7. Selanjutnya klik **Finish**
![App Screenshot](img/install-vm/7.jpeg)

8. Anda berhasil masuk ke **VirtualBox**, klik icon + **Add** 
![App Screenshot](img/install-vm/8.jpeg)

9. Isikan **Nama**, dan masukan file **iso**
![App Screenshot](img/install-vm/10.jpeg)

10. Atur Base Memory menjadi **4096mb**, dan processor menjadi **2 CPU**, klik **next**
![App Screenshot](img/install-vm/11.1.jpeg)

11. Selanjutnya atur Djsk Size menjadi **25GB**, dan klik **next**
![App Screenshot](img/install-vm/12.jpeg)

13. Klik **FInish**
![App Screenshot](img/install-vm/14.jpeg)

14. Pilih English lalu klik **continue**
![App Screenshot](img/install-deb/a.png)

15. pilih **other**
![App Screenshot](img/install-deb/b.png)

16. Pilih **Asia**
![App Screenshot](img/install-deb/c.png)

17. Pilih **Indonesia**
![App Screenshot](img/install-deb/d.png)

18. Pilih **United States**
![App Screenshot](img/install-deb/e.png)

19. Pilih **American English**
![App Screenshot](img/install-deb/f.png)

20. Tunggu hingga proses selesai
![App Screenshot](img/install-deb/g.png)

21. Tuliskan **Hostname** anda
![App Screenshot](img/install-deb/h.png)

22. klik **continue**
![App Screenshot](img/install-deb/i.png)

23. Buat **Password** anda, setelah itu klik **continue**
![App Screenshot](img/install-deb/j.png)

24. Tulis **Nama Lengkap** anda
![App Screenshot](img/install-deb/k.png)

25. Tuliskan **Username** untuk **account** anda
![App Screenshot](img/install-deb/l.png)

26. Tulis **root password lalu** tekan **continue**
![App Screenshot](img/install-deb/9.png)

27. Pilih sesuai **zona waktu** anda
![App Screenshot](img/install-deb/n.png)

28. Pada **Particion method** pilih **manual**
![App Screenshot](img/install-deb/12.png)

29. Pilih sesuai gambar dibawah
![App Screenshot](img/install-deb/14.png)

30. pilih option **yes**, lalu kilik **continue**
![App Screenshot](img/install-deb/15.png)

31.pilih sesuai gambar dibawah
![App Screenshot](img/install-deb/16.png)

32. Pilih **swao areas**, setelah itu klik **continue**
![App Screenshot](img/install-deb/37.png)

33. Pilih opsi **Done setting up the partition**
![App Screenshot](img/install-deb/38.png)

34. Pilih **Finish**
![App Screenshot](img/install-deb/39.png)

35. Pilih **yes**,lalu klik **continue**
![App Screenshot](img/install-deb/40.png)

36. Tunggu hingga proses selesai
![App Screenshot](img/install-deb/41.png)

37. Pilih **no**
![App Screenshot](img/install-deb/42.png)

38. Pilih option **Indonesia**, lalu klik **continue**
![App Screenshot](img/install-deb/43.png)

39. Pilih **kebo.pens.ac.id**
![App Screenshot](img/install-deb/44.png)

40. Klik **continue**
![App Screenshot](img/install-deb/45.png)

41. Tunggu hingga proses selesai
![App Screenshot](img/install-deb/46.png)

42. Pilih option **No**
![App Screenshot](img/install-deb/47.png)

43. Tunggu hingga proses selesai
![App Screenshot](img/install-deb/48.png)

44. pilih option sesuai dengan gambar dibawah ini
![App Screenshot](img/install-deb/49.png)

45. Tunggu hingga proses selesai
![App Screenshot](img/install-deb/50.png)

46. Pilih option **yes**, lalu klik **continue**
![App Screenshot](img/install-deb/51.png)

47. Pilih opsi **/dev/sda (ata-VBOX_VBf5fb021a-7667d996)**
![App Screenshot](img/install-deb/52.png)

48. Klik **continue**
![App Screenshot](img/install-deb/53.png)

49. Setelah selesai maka tampilan anda akan seperti dibawah ini
![App Screenshot](img/install-deb/54.png)


## Link Download

[Link download debian 12](https://www.debian.org/download)

[Link download virtualbox](https://www.virtualbox.org/wiki/Downloads)

[Link download VMware fusion](https://customerconnect.vmware.com/downloads/details?downloadGroup=FUS-1350&productId=1375&rPId=110933)

