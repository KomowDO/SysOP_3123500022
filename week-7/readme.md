<div align="center">
  <h1 style="text-align: center;font-weight: bold">Praktikum 7<br>SysOp Proses dan Manajemen Proses</h1>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : </h3>
  <p style="text-align: center;">
    <strong>Muhammad Arief Wicaksono Putra Santoso (3123500022)</strong>
  </p>
<h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
  <hr><hr>
</div>

# Daftar Isi
1. Dasar Teori
2. Fork
3. Tugas
4. Kesimpulan

# Dasar teori
### Process - Fork - Multithread
Setiap program atau bagian dari program yang sedang dieksekusi oleh CPU disebut dengan proses. Proses dapat berjalan secara foreground atau background. Untuk melihat seluruh proses yang sedang berjalan gunakan perintah $ ps -e . Bisa juga menggunakan perintah $pstree | more untuk melihat secara detil proses yang sefan berjalan dengan format tree.

Setiap proses akan memilik PID (Process ID). Apabila dibutuhkan Sebuah proses bisa memiliki proses anakan. Dalam hubungan tersebut proses dapat diibaratkan seperti orang tua (parent) dengan anak (child) yang turun temurun.

Setiap proses memiliki parent dan child.
Setiap proses memiliki ID (pid) dan parent ID (ppid), kecuali proses init atau systemd.
ppid dari sebuah proses adalah ID dari parent proses tersebut.
fork digunakan untuk menduplikasi proses. Proses yang baru disebut dengan child proses, sedangkan proses pemanggil disebut dengan parent proses.

Exec adalah function yang digunakan untuk menjalankan program baru dan mengganti program yang sedang berlangsung. exec adalah program family yang memiliki berbagai fungsi variasi, yaitu execvp, execlp, execv, dan lain lain.

wait adalah function yang digunakan untuk mendapatkan informasi ketika child proses berganti state-nya. Pergantian state dapat berupa termination, resume, atau stop.

# Fork Parent - Child Process
#### -Buat tulisan tentang konsep fork dan implementasinya dengan menggunakan bahasa pemrograman C! (minimal 2 paragraf disertai dengan gambar)
Jawab:
Konsep fork dalam sistem operasi adalah mekanisme untuk menduplikasi proses yang sedang berjalan. Proses yang dihasilkan disebut sebagai child process, yang merupakan salinan dari parent process. Proses ini memiliki PID (Process ID) yang unik dan PPID (Parent Process ID) yang merujuk pada PID dari parent process. Fork memungkinkan eksekusi program secara paralel dan independen.

Dalam implementasi fork, setiap proses memiliki hubungan hierarki seperti orang tua dan anak. Misalnya, jika sebuah main process melakukan fork, maka akan tercipta parent process dan child process. Child process ini akan memiliki PPID yang sama dengan PID dari parent process. Fungsi ini sering digunakan dalam pemrograman untuk menciptakan proses baru dan memanfaatkan multithreading.


## Contoh :
![ss](img/1.png)

## Output :
![ss](img/2.png)

## Peta logika
![ss](img/p2.png)


### -Akses dan clonning repo : https://github.com/ferryastika/operatingsystem.git

![ss](img/3.png)

### -Deskripsikan dan visualisasikan pohon proses hasil eksekusi dari kode program fork01.c, fork02.c, fork03.c, fork04.c, fork05.cdan fork06.c.

## Fork01.c
![ss](img/4.png)

### Output
![ss](img/5.png)

### Deskripsi
Deskripsi Program:

1. Deklarasi variabel mypid bertipe pid_t dan myuid bertipe uid_t untuk menyimpan PID dan UID proses.
   
2. Dilakukan iterasi sebanyak 3 kali menggunakan loop for.
Pada setiap iterasi:
a. Variabel mypid diisi dengan nilai PID dari proses saat ini menggunakan fungsi getpid().<br>
b. Informasi tentang proses dicetak ke layar menggunakan cout, termasuk PID, PPID (dengan menggunakan fungsi getppid()), dan UID (dengan menggunakan fungsi getuid()).<br>
c. Program dijeda selama 3 detik menggunakan fungsi sleep(3).

### Pohon Proses 1
![ss](img/1.1.png)


## Fork02.c
![ss](img/6.png)

### Output
![ss](img/7.png)

### Deskripsi
Deskripsi Program:

1. Deklarasi variabel childpid bertipe pid_t untuk menyimpan PID dari proses anak.<br>
2. Variabel x diinisialisasi dengan nilai 5.<br>
3. Dilakukan pemanggilan fork() untuk membuat proses anak.<br>
4. Selama program berjalan, dilakukan loop tak terbatas (while (1)) untuk mencetak informasi tentang PID dari proses saat ini (dengan menggunakan getpid()) dan nilai variabel x yang terus bertambah setiap dua detik.<br>
5. Program akan berjalan tanpa henti hingga dihentikan secara manual.

### Pohon Proses 2

![ss](img/1.2.png)

## Fork03.c
![ss](img/8.png)

### Output
![ss](img/9.png)

### Deskripsi
Deskripsi Program:

1. Deklarasi variabel childpid bertipe pid_t untuk menyimpan PID dari proses anak.<br>
2. Pemanggilan fork() untuk membuat proses anak.<br>
3. Dilakukan loop for sebanyak lima kali iterasi.<br>
4. Pada setiap iterasi, program mencetak informasi tentang PID dari proses saat itu menggunakan getpid(), dan kemudian program dijeda selama 2 detik menggunakan fungsi sleep(2).<br>
5. Setelah lima iterasi selesai, program akan berakhir.

### Pohon Proses 3
![ss](img/1.3.png)


## Fork04.c
![ss](img/10.png)

### Output
![ss](img/11.png)

### Deskripsi
Deskripsi Program:

1. Deklarasi variabel child_pid bertipe pid_t untuk menyimpan PID dari proses anak, variabel status untuk menyimpan status keluaran dari proses anak, dan variabel wait_result bertipe pid_t untuk menyimpan hasil dari fungsi wait().<br>
2. Pemanggilan fork() untuk membuat proses anak.<br>
Jika nilai child_pid adalah 0, maka kode dalam blok if dijalankan oleh proses anak.<br>
a. Proses anak mencetak informasi tentang PID dan PPID-nya.<br>
3. Jika nilai child_pid lebih besar dari 0, maka kode dalam blok else if dijalankan oleh proses induk.<br>
a. Proses induk mencetak informasi tentang PID-nya dan PID proses anak.<br>
4. Jika nilai child_pid kurang dari 0, maka pesan kesalahan akan dicetak dan program keluar menggunakan exit(1).<br>
5. Setelah itu, kedua proses (induk dan anak) akan mencetak pesan yang menunjukkan bahwa mereka sedang berjalan.

### Pohon Proses 4
![ss](img/1.4.png)

## Fork05.c
![ss](img/12.png)

### Output
![ss](img/13.png)

### Deskripsi
Deskripsi Program:

1. Deklarasi variabel child_pid bertipe pid_t untuk menyimpan PID dari proses anak, variabel status untuk menyimpan status keluaran dari proses anak, dan variabel wait_result bertipe pid_t untuk menyimpan hasil dari fungsi wait().<br>
2. Pemanggilan fork() untuk membuat proses anak.<br>
3. Jika nilai child_pid adalah 0, maka kode dalam blok if dijalankan oleh proses anak.<br>
a. Proses anak mencetak informasi tentang PID-nya.<br>
b. Proses anak menjalankan perintah ls -l /home menggunakan fungsi execl(). Jika execl() berhasil, maka kode setelahnya tidak akan dieksekusi karena proses anak telah digantikan dengan proses ls -l /home.<br>
c. Jika execl() gagal, maka pesan kesalahan akan dicetak dan proses anak akan keluar menggunakan exit(1).<br>
4. Jika nilai child_pid lebih besar dari 0, maka kode dalam blok else if dijalankan oleh proses induk.<br>
a. Proses induk mencetak informasi tentang PID-nya dan PID proses anak.<br>
5. Jika nilai child_pid kurang dari 0, maka pesan kesalahan akan dicetak dan program keluar menggunakan exit(1).<br>

### Pohon Proses 5
![ss](img/1.5.png)

## Fork06.c
![ss](img/14.png)

### Output
![ss](img/15.png)

### Deskripsi
Deskripsi Program:

1. Deklarasi variabel child_pid bertipe pid_t untuk menyimpan PID dari proses anak, variabel status untuk menyimpan status keluaran dari proses anak, dan variabel wait_result bertipe pid_t untuk menyimpan hasil dari fungsi wait().<br>
2. Pemanggilan fork() untuk membuat proses anak.<br>
3. Jika nilai child_pid adalah 0, maka kode dalam blok if dijalankan oleh proses anak.<br>
a. Proses anak mencetak informasi tentang PID-nya.<br>
b. Proses anak menjalankan program lain (dalam contoh ini "fork03" dengan argumen "goose") menggunakan fungsi execl(). Jika execl() berhasil, maka kode setelahnya tidak akan dieksekusi karena proses anak telah digantikan dengan program "fork03".<br>
c. Jika execl() gagal, maka pesan kesalahan akan dicetak dan proses anak akan keluar menggunakan exit(1).<br>
4. Jika nilai child_pid lebih besar dari 0, maka kode dalam blok else if dijalankan oleh proses induk.<br>
a. Proses induk mencetak informasi tentang PID-nya dan PID proses anak.<br>
5. Jika nilai child_pid kurang dari 0, maka pesan kesalahan akan dicetak dan program keluar menggunakan exit(1).<br>
6. Setelah itu, kedua proses (induk dan anak) akan mencetak pesan yang menunjukkan bahwa mereka sedang berjalan.<br>

### Pohon Proses 6
![ss](img/1.6.png)


# Tugas
### Buatlah program perkalian 2 matriks [4 x 4] dalam bahasa C yang memanfaatkan fork().

## Code
![ss](img/t2.png)
![ss](img/t2.1.png)




## Output
![ss](img/t1.png)

### Analisa Kode

1. Fungsi Perkalian Matriks: Fungsi perkalian() digunakan untuk melakukan perkalian matriks. Matriks hasil dideklarasikan dalam fungsi utama, kemudian diisi oleh fungsi perkalian().<br><br>

2. Fungsi Cetak Matriks: Fungsi cetak() digunakan untuk mencetak matriks ke layar.<br><br>

3. Fungsi main():<br>

a. Menginisialisasi dua matriks a dan b dengan nilai sampel (matriks identitas untuk b).<br>

b. Membuat matriks kosong hasil untuk menyimpan hasil perkalian.<br>

C. Proses Fork (pid = fork()): Membuat Child Process.<br>

-. Jika fork gagal, pesan kesalahan dicetak dan program keluar.<br>

d. Child Process (pid == 0):<br>

-. Memanggil fungsi perkalian untuk menghitung perkalian matriks dan menyimpan hasilnya di hasil.<br>

-. Mencetak "Hasil Child Process:" dan kemudian memanggil fungsi cetak untuk mencetak hasil hasil.<br>

e. Parent Process (pid > 0):<br>

-. Menunggu Child Process selesai menggunakan wait(NULL).<br>

-. Mencetak "Hasil Parent Process:" dan kemudian memanggil fungsi perkalian.<br>

-. Memanggil fungsi cetak untuk mencetak hasil hasil (hasil yang sama dicetak oleh Child Process).<br>

### Visualisasi Proses Fork
![ss](img/1.7.png)