# Jarkom_Modul1_Praktikum_D15
Praktikum mata kuliah Jaringan Komputer Informatika ITS 2020 Kelompok D15
- Ammar Alifian Fahdan (05111840000007)
- Lii'zza Aisyah Putri Sulistio (05111840000073)

## A. Display Filter
### 1. Sebutkan webserver yang digunakan pada "testing.mekanis.me", dapatkan webserver yang digunakan di Header.
- Follow request ke testing.mekanis.me dengan `http.host == "testing.mekanis.me"`
- Jawaban `nginx/1.14.0(Ubuntu)`

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96201512-fa0b2200-0f86-11eb-95eb-4a59e7b7c1ed.png">


### 2. Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!
Gunakan File &#8594; Export Objects &#8594; HTTP, Save All, cari file Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg.

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96201754-9a614680-0f87-11eb-80d5-36533cc71831.png">


### 3. Cari username dan password ketika login di "ppid.dpr.go.id"!
- Filter dengan `http.host == "ppid.dpr.go.id" and http.request.method == "POST"`
- Dapatkan username dan password di HTML Form URL Encoded
- Username: `10pemuda'
- Password: `guncangdunia`

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96202749-3be99780-0f8a-11eb-8a1e-b36ee6376d6d.png">


### 4. Temukan paket dari web-web yang menggunakan basic authentication method! Filter dengan http contains "Authorization: Basic"
### 5. Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!
### 6. Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).
### 7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut.Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"
### 8. Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!
### 9. Cari username dan password ketika login FTP pada localhost!
### 10. Cari file .pdf di wireshark lalu download dan buka file tersebut! clue: "25 50 44 46"

## B. Capture Filter
### 11. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
### 12. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!
### 13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
### 14. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
### 15. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!
