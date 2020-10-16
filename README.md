# Jarkom_Modul1_Praktikum_D15
Praktikum mata kuliah Jaringan Komputer Informatika ITS 2020 Kelompok D15
- Ammar Alifian Fahdan (05111840000007)
- Lii'zza Aisyah Putri Sulistio (05111840000073)

Kendala: terjadi kegagalan dalam mengunduh file .pcapng sampai beberapa kali

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
Filter dengan `http contains "Authorization: Basic"`

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96202957-dba72580-0f8a-11eb-9a79-ae3daa5ef86d.png">


### 5. Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!
- Filter dengan `http contains "aku.pengen.pw"`
- Username dan password bisa didapatkan di header Authorization

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96203065-21fc8480-0f8b-11eb-9ce1-c2a62f6dfacc.png">

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96203088-2fb20a00-0f8b-11eb-8551-be9f9003cb4b.png">

### 6. Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).
- ZIP: Filter dengan `ftp contains "Answer.zip`, dapatkan responnya dengan membuka command response frame. Follow TCP stream dan simpan dalam bentuk raw.
- Password : Filter dengan `ftp contains "zipkey.txt"`, dapatkan responnya dengan membuka command response frame. Password ada di Line-based text data.

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96208975-d3ee7d80-0f98-11eb-91ae-9fa7c20feadc.png">

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96208991-d7820480-0f98-11eb-918a-99c5b1c1905b.png">


### 7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut.Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"
- .zip memiliki ciri khas yaitu menyimpan nama file (bukan isi file) secara plain text di dalam filenya
- Maka cukup filter dengan `ftp-data contains "Yes.pdf"`
- Dapatkan responnya dengan membuka comman response frame
- Follow TCP stream dan simpan dalam bentuk raw
- Ekstrak file zip yang didapatkan dan buka PDF yang ada di dalamnya

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96209292-6ee75780-0f99-11eb-8223-a3a50a375ed1.png">


### 8. Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!
- Filter dengan `ftp contains RETR`
- Objek yang diunduh adalah `Readme dan license.txt`

<img width="803" alt="Screen Shot 2020-10-16 at 10 24 45" src="https://user-images.githubusercontent.com/58472359/96209486-eae19f80-0f99-11eb-8c66-6ef0d60c696c.png">

### 9. Cari username dan password ketika login FTP pada localhost!
- Filter dengan `ftp contains "USER" or ftp contains "PASS"`
- Username: `dhana`
- Password: `dhana123`

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96209620-42800b00-0f9a-11eb-9a56-fef98b587f80.png">

### 10. Cari file .pdf di wireshark lalu download dan buka file tersebut! clue: "25 50 44 46"
- Filter dengan `frame contains 25:50:44:46`
- Follow TCP stream dengan filter `tcp.stream eq 15`
- Dapatkan paket yang mengandung magic bytes seperti pada clue (25 50 44 46)
- Save As raw dan hapus bagian response header dengan menggunakan hex editor (seperti Bless)

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96209740-870ba680-0f9a-11eb-82a1-a38f19d3670b.png">

## B. Capture Filter
### 11. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
Filter dengan `port 21`

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96209794-adc9dd00-0f9a-11eb-9434-283766734f0a.png">

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96209805-b4585480-0f9a-11eb-8225-6d15cb194172.png">


### 12. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!
Filter dengan `tcp src port 80`

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96209847-cafeab80-0f9a-11eb-8837-3cadbacb8686.png">

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96209852-ce923280-0f9a-11eb-9a3a-19efb0e58eb2.png">


### 13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
Filter dengan `dst port 443`

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96209893-e5d12000-0f9a-11eb-85f6-d13e06ccff22.png">

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96209899-ec5f9780-0f9a-11eb-87f3-91921532ab37.png">


### 14. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
Filter dengan `src net 192.168.43.240`

<img width="268" alt="image" src="https://user-images.githubusercontent.com/58472359/96209940-0bf6c000-0f9b-11eb-8682-af9356dd6fd7.png">

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96209947-0dc08380-0f9b-11eb-986b-e69ab3866324.png">

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96209953-10bb7400-0f9b-11eb-8f14-853dcef87740.png">


### 15. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!
Filter dengan `dst host monta.if.its.ac.id`

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96209989-25980780-0f9b-11eb-8ff5-aee245b84338.png">

<img width="451" alt="image" src="https://user-images.githubusercontent.com/58472359/96209995-27fa6180-0f9b-11eb-9225-2c49720188b0.png">
