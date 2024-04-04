# Laporan Resmi Praktikum Jarkom - Modul 1 - IT07 - 2024

## Pendahuluan

Pada Modul 1 ini, praktikum dilaksanakan melalui platform CTFd dengan tampilan platform adalah sebagai berikut

![Tampilan Platform CTFd](./Media/Screenshot%202024-04-01%20151353.png)

Terdapat 10 soal CTF dengan setiap soalnya diharuskan untuk mencari sebuah flag unique yang didapatkan dengan menjawab pertanyaan setiap soal berdasarkan data permintaan soal. Data didapatkan berdasarkan hasil analisis pada sebuah file `.pcap / .pcapng` (disediakan pada setiap soal) menggunakan tool wireshark.

## Pembahasan Soal

IT07 berhasil menjawab 7 dari 10 soal dengan benar, namun terdapat dua soal tambahan yang juga berhasil ditemukan jawabannya setelah waktu habis, kedua soal tersebut juga akan ditambahkan pada pembahasan soal ini. Berikut merupakan pembahasannya

### Soal 01 - evidence

![Soal Evidence](./Media/soal-evidence.png)

#### Langkah Pengerjaan

### Soal 02 - ATM or ATP or FTP ? 🤔

![Soal ATM or ATP or FTP](./Media/soal-atm.png)

#### Langkah Pengerjaan

1. Buka wsl lalu masukan nc nya untuk melihat soal yang ingin ditanyakan. Disini ditanyakan password yang berhasil didapatkan oleh hacker setelah melakukan bruteforce login.
   ![ATP1](./Media/atp1.png)

2. Buka file soal lalu lakukan filter dengan command `ftp && ip.src==10.15.40.20` untuk melihat paket-paket yang berasal dari ip tersebut.
   ![ATP2](./Media/atp2.png)

3. Cari hingga menemukan tulisan `Login sucessful`
4. lalu klik follow tcp stream untuk melihat isi datanya. disitu akan terlihat password yang digunakan
   ![ATP3](./Media/atp3.png)

5. Tuliskan jawaban yang didapat ke terminal lalu akan didaptkan flagnya.
   ![ATP4](./Media/atp4.png)

### Soal 03 - How Many packets?

![Soal How Many packets?](./Media/soal-packets.png)

#### Langkah Pengerjaan

### Soal 04 - trace him

![Soal trace him](./Media/soal-tracehim.png)

#### Langkah Pengerjaan

1.  Buka wsl lalu masukan nc nya untuk melihat soal yang ingin ditanyakan. Disini, kita disuruh untuk melacak ip attacker tersebut.
    ![trace1](./Media/trace1.png)

2.  Buka file soal lalu lakukan filter di wireshark dengan command `ftp && ip.dst==10.15.40.20` untuk melihat paket-paket yang menuju ip tersebut.
    ![trace2](./Media/trace2.png)

3.  Disitu terlihat bahwa source IP nya adalah `10.30.3.4`.
    ![trace3](./Media/trace3.png)

4.  Dengan begitu, kita sudah mendapatkan Ip penyerang tersebut. Masukan jawabannya ke terminal dan flagnya akan ditemukan.
    ![trace4](./Media/trace4.png)

### Soal 05 - creds

![Soal creds](./Media/soal-creds.png)

#### Langkah Pengerjaan

### Soal 06 - malwleowleo

![Soal malwleowleo](./Media/soal-malwleo.png)

#### Langkah Pengerjaan

1. Buka wsl lalu masukan nc nya untuk melihat soal yang ingin ditanyakan. Disini, kita disuruh untuk mencari nama malware yang dikirim oleh attacker ke korban.
   ![Malwleo1](./Media/malwleo1.png)

2. Buka file soal lalu lakukan filter di wireshark dengan command `ftp && ip.dst==10.15.40.20` untuk melihat paket-paket yang menuju ip tersebut.
   ![Malwleo2](./Media/malwleo2.png)

3. Cari nama file malware yang dikirimkan oleh attacker, disini didapatkan nama filenya adalah `m4L1c10us_W4re.c`
   ![Malwleo3](./Media/malwleo3.png)

4. Masukan jawabannya ke terminal dan flagnya akan ditemukan.
   ![Malwleo4](./Media/malwleo4.png)

### Soal 07 - whoami

![Soal whoami](./Media/soal-whoami.png)

#### Langkah Pengerjaan

1. Buka wsl lalu masukan nc nya untuk melihat soal yang ingin ditanyakan. Disini, kita disuruh untuk mencari nama attacker yang sudah melakukan serangan tersebut.
   ![Whoami1](./Media/whoami1.png)

2. Untuk mencari nama attacker tersebut, kita perlu mendownload file malware yang telah dikrimkan oleh attacker.
   ![Whoami2](./Media/whoami2.png)

3. Buka file .c yang sudah didowload tadi lalu akan didapatkan teks yang terenkripsi dalam format base64, yaitu `SGVsbG8gbXkgbmFtZSBpcyBQYXVsIEF0cmVpZGVzCg==`.
   ![Whoami3](./Media/whoami3.png)

4. Open browser untuk decode teks dengan format base64 tersebut. Lalu akan didapatkan nama attackernya, yaitu _Paul Atreides_
   ![Whoami4](./Media/whoami4.png)

5. Masukan nama attacker ke dalam terminal lalu dapatkan flagnya.
   ![Whoami5](./Media/whoami5.png)

### Soal 08 - secret

![Soal secret](./Media/soal-secret.png)

#### Langkah Pengerjaan

1. Buka wsl lalu masukan nc nya untuk melihat soal yang ingin ditanyakan. Disini, kita disuruh untuk mencari pesan yg dikutip oleh attacker.
   ![secret1](./Media/secret1.png)

2. Download file lainnya yang dikirim oleh attacker selain file malware. Disini ditemukan file `mirza.jpg`.
   ![secret2](./Media/secret3.png)

3. Setelah mendownload, buka filenya lalu akan ditemukan pesan dalam tanda kutip, yaitu "MIO MIRZA".
   ![secret3](./Media/secret4.jpg)

4. Masukan jawaban yang telah didapatkan ke terminal lalu dapatkan flagnya.
   ![secret4](./Media/secret5.png)

### Soal 09 - fuzz

![Soal fuzz](./Media/soal-fuzz.png)

#### Langkah Pengerjaan

### Soal 10 - malwaew

![Soal secret](./Media/soal-malwaew.png)

#### Langkah Pengerjaan
