# Praktikum Modul 1 20 September 2021
## Anggota Kelompok B07 ##

Salman Damai Alfariq 05111940000159
Ridho Ajiraga Jagiswara 05111940000170
David Ralphwaldo Martuaraja 05111940000190

### 1. Sebutkan webserver yang digunakan pada "ichimarumaru.tech"!

### 2. Temukan paket dari web-web yang menggunakan basic authentication method!

### 3. Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!  

### 5. Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap

### 6.   Mencari username dan password ketika melakukan login ke FTP Server
Untuk mendapatkan username dan password digunakan `ftp.request.command == USER || ftp.request.command == PASS` pada display picture

![image](https://user-images.githubusercontent.com/75240358/134755868-323453f5-56fc-40fd-b75c-6ccd0617443f.png)

### 7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")
a. Memasukkan `ftp-data contains “Real.pdf”` pada input display filter.

![image](https://user-images.githubusercontent.com/75240358/134755974-d2b87d93-ec86-4431-baa7-202113d123a8.png)

b. Melakukan follow TCP Stream pada paket data tersebut.

![image](https://user-images.githubusercontent.com/75240358/134756049-482b3ad5-754c-424f-93d8-30c9c8af2e2f.png)

c. Menampilkan data raw dengan memilih opsi Raw pada dropdown Show data as.

![image](https://user-images.githubusercontent.com/75240358/134756056-88d50871-6370-4dc7-bc3f-2179e6138f1b.png)

d. Kemudian mensave data menjadi file .zip

e. Hasilnya

![image](https://user-images.githubusercontent.com/75240358/134756086-97b55d3c-9647-4429-bab6-9f31bbaaeddd.png)
![image](https://user-images.githubusercontent.com/75240358/134756091-e943fec4-3c4b-4386-8aca-d45a4a694130.png)

### 8. Mencari paket-paket yang menuju FTP tersebut
Untuk mendapatkan paket-paket yang menuju ke server FTP digunakan `ftp.request.command == STOR` pada input display filter

![image](https://user-images.githubusercontent.com/75240358/134756250-d43fb583-b01f-4896-a677-108996b987eb.png)


### 9.	Dari paket-paket yang menuju FTP terdapat indikasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut.
a. Memasukkan `ftp-data.command contains "secret.zip"` pada input display filter

b. Melakukan follow TCP Stream pada paket data secret.zip

![image](https://user-images.githubusercontent.com/75240358/134756245-29276cec-3f91-4f17-be83-de6da8afd811.png)

c. Kemudian pilih Raw pada dropdown Show data as dan setelah itu save filenya dengan nama ‘secret.zip’.

![image](https://user-images.githubusercontent.com/75240358/134756283-cd073b4a-deac-472c-a7fc-5767a831541c.png)
![image](https://user-images.githubusercontent.com/75240358/134756295-272a1e37-0dbb-4280-92d8-3ecd754c8994.png)

d. Berikut adalah isi dari file secret.zip

![image](https://user-images.githubusercontent.com/75240358/134756301-fbc9d621-c39e-44a1-8588-77cb035a4d38.png)

### 10. Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"
a. Pertama masukkan `ftp-data.command contains "history.txt"` pada input display filter.

b. Setelah itu melakukan follow TCP Stream pada file ‘history.txt’

![image](https://user-images.githubusercontent.com/75240358/134756333-dd1ba495-9bd5-4be4-a78e-6a3b7884f11d.png)

c. Pilih opsi ‘Raw’ pada dropdown ‘Show data as’ dan melakukan save file dengan name ‘history.txt’

![image](https://user-images.githubusercontent.com/75240358/134756344-244436fe-f764-4b1a-aa0e-764390075998.png)

d. Dari isi file ‘history.txt’, diketahui bahwa password untuk Wanted.pdf disimpan pada file ’bukanapaapa.txt’

![image](https://user-images.githubusercontent.com/75240358/134756362-bd237d75-242e-4b48-8a2a-7222280c8907.png)

e. Kemudian dilakukan follow TCP Stream pada paket data ’bukanapaapa.txt’. Diperoleh password untuk file Wanted.pdf, yaitu **d1b1langbukanapaapajugagapercaya**

![image](https://user-images.githubusercontent.com/75240358/134756394-16917bdf-5e61-4642-a85b-730922c55c05.png)

f. Buka file Wanted.pdf dengan menggunakan password tersebut. Berikut hasilnya.

![image](https://user-images.githubusercontent.com/75240358/134756555-cbdfb810-345d-4ea3-90e3-bb105290e440.png)

### 11. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!   

### 12. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21! 

### 13. Filter sehingga wireshark hanya mengambil paket yang menuju port 443!  

### 14. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!

### 15. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
