# Job Control

Job control adalah kemampuan dalam sistem Unix dan Unix-like yang memungkinkan pengguna untuk mengelola proses-proses yang berjalan dalam shell.

Dengan job control, pengguna dapat menjalankan proses di latar belakang, menghentikan proses yang sedang berjalan, dan mengontrol proses-proses lainnya.

Ini memungkinkan pengguna untuk menjalankan tugas-tugas secara efisien dan fleksibel.

# Latihan Praktikum

1.Eksekusi seluruh profile yang ada :

a. Edit file profile /etc/profile dan tampilkan pesan sebagai berikut :

echo “Profile dari /etc/profile”

b.Ganti "username" dengan nama anda , lalu edit semua profile yang ada yaitu :
/home/username/.bash_profile

/home/.username/.bash_login

/home/username/.profile

/home/username/.bashrc

Ganti nama /home/mahasiswa dengan nama anda sendiri. 

Pada setiap file tersebut, cantumkan instruksi echo, misalnya pada /home/ mahasiswa/.bash_profile :
echo “Profile dari .bash_profile”
Lakukan hal yang sama untuk file lainnya, sesuaikan tampilan dengan nama file yang
bersangkutan.

![image](https://github.com/FahriAl-Hafiz/Laporan-praktikum-5-SistemOperasi/assets/126375451/319909d1-3df8-4cba-b1d6-791e44634966)

c. Jalankan instruksi subtitute user, kemudian keluar dengan perintah exit sebagai berikut:

    $ su mahasiswa 
    $ exit

![image](https://github.com/FahriAl-Hafiz/Laporan-praktikum-5-SistemOperasi/assets/126375451/0e2662ef-ed51-47bb-8bce-ba21dc850570)

kemudian gunakan opsi – sebagai berikut :
    
    $ su – mahasiswa
    $ exit

![image](https://github.com/FahriAl-Hafiz/Laporan-praktikum-5-SistemOperasi/assets/126375451/24d83d8e-63bb-45cf-81f3-ebe7922d85e2)

perbedaan antara keduanya ialah :

su username untuk pindah user tanpa masuk ke lingkungannya sedangkan 

su - username masuk dengan mengaktifkan lingkungan dari user tsb

2. Prompt String (PS)
a. Edit file .bash_profile, ganti prompt PS1 dengan ‘>’. Instruksi export diperlukan dengan
parameter nama variable tersebut, agar perubahan variable PS1 dikenal oleh semua shell

        PS1="> "
        export PS1

b. Eksperimen hasil PS1 :

![image](https://github.com/FahriAl-Hafiz/Laporan-praktikum-5-SistemOperasi/assets/126375451/64bcbc33-42d1-40cd-90af-a3de89d91768)

3. Logout

Edit file .bash_logout, tampilkan pesan dan tahan selama 5 detik, sebelum eksekusi logout
        
        Echo “Terima kasih atas sesi yang diberikan”
        Sleep 5
        clear

![image](https://github.com/FahriAl-Hafiz/Laporan-praktikum-5-SistemOperasi/assets/126375451/c34d5739-1582-4c7c-adaa-b69acbade138)

4. Bash script
a. Buat 3 buah script p1.sh, p2.sh, p3.sh dengan isi masing-masing :

        p1.sh
        #! /bin/bash
        echo “Program p1”
         ls –l
p2.sh
      
      #! /bin/bash
      echo “Program p2”
      who

p3.sh
      
      #! /bin/bash
      echo “Program p3”
      ps x

![image](https://github.com/FahriAl-Hafiz/Laporan-praktikum-5-SistemOperasi/assets/126375451/e27b9369-2259-466b-9cd4-b4cb687b4550)

      
b. Jalankan script tersebut sebagai berikut :

    $ ./p1.sh ; ./p3.sh ; ./p2.sh
    $ ./p1.sh &
    $ ./p1.sh $ ./p2.sh & ./p3.sh &
    $ ( ./p1.sh ; ./p3.sh ) &

![image](https://github.com/FahriAl-Hafiz/Laporan-praktikum-5-SistemOperasi/assets/126375451/9ce33c64-65e4-4e56-b260-53ffe673e5cc)

5. Jobs
a. Buat shell-script yang melakukan loop dengan nama pwaktu.sh,
setiap 10 detik, kemudian menyimpan tanggal dan jam pada file hasil.

        #!/bin/bash
        while [ true ]
        do
        date >> hasil
        sleep 10
        done

![image](https://github.com/FahriAl-Hafiz/Laporan-praktikum-5-SistemOperasi/assets/126375451/d22be7a4-b199-4d4f-920a-07ed35388a1d)

b. Jalankan sebagai background; kemudian jalankan satu program (utilitas find) di background
sebagai berikut :
      
      $ jobs
      $ find / -print > files 2>/dev/null &
      $ jobs

![image](https://github.com/FahriAl-Hafiz/Laporan-praktikum-5-SistemOperasi/assets/126375451/cd554322-3c9d-4e1a-bae5-22c5c3ed897b)

c. Jadikan program ke 1 sebagai foreground, tekan ^Z dan kembalikan program tersebut ke
background
      
      $ fg %1
      $ bg

d. Stop program background dengan utilitas kil
      
      $ ps x
      $ kill [Nomor PID]

![image](https://github.com/FahriAl-Hafiz/Laporan-praktikum-5-SistemOperasi/assets/126375451/2a70ddd5-b054-4bf7-9188-33a2adb91125)


6. History

a. Ganti nilai HISTSIZE dari 1000 menjadi 20
      
      $ HISTSIZE=20
      $ history

![image](https://github.com/FahriAl-Hafiz/Laporan-praktikum-5-SistemOperasi/assets/126375451/abddc3b3-787f-4721-b88e-471f62496d51)

b. Gunakan fasilitas history dengan mengedit instruksi baris ke 5 dari instruksi yang terakhir
dilakukan

      $!-5

![image](https://github.com/FahriAl-Hafiz/Laporan-praktikum-5-SistemOperasi/assets/126375451/ada940af-bb33-407d-bc2d-32322072d93a)

c. Ulangi instruksi yang terakhir. Gunakan juga ^P dan ^N untuk bernavigasi pada history bufer

      $ !!

d. Ulangi instruksi pada history bufer nomor 150

      $ !150

e. Ulangi instruksi dengan prefix “ls”
      
      $ !ls
![image](https://github.com/FahriAl-Hafiz/Laporan-praktikum-5-SistemOperasi/assets/126375451/7f339608-c4e7-48ea-b164-84c4a6fa2991)




