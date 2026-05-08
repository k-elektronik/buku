# Hacks, Leaks, and Revelations - Ringkasan Teknis

**Judul:** *Hacks, Leaks, and Revelations: The Art of Analyzing Hacked and Leaked Data*  
**Penulis:** Micah Lee  
**Penerbit:** No Starch Press  
**Tahun:** 2024  
**Domain:** Investigative data analysis, keamanan sumber, analisis dataset hasil hack/leak, command line, Python, structured data, OSINT, data journalism  
**Target pembaca:** jurnalis investigasi, peneliti, aktivis transparansi, analis data, praktisi keamanan informasi, dan pembaca teknis yang ingin menganalisis dataset besar secara aman  

---

## 1. Posisi Dokumen

Dokumen ini merangkum isi buku *Hacks, Leaks, and Revelations* dengan gaya teknis, langsung, dan bebas dari pola retoris. Fokus ringkasan adalah substansi teknis, proses investigasi, pengelolaan risiko, serta metode analisis dataset.

Buku ini membahas cara memperoleh, menyimpan, memverifikasi, mencari, memproses, dan menganalisis dataset hasil hack atau leak. Materi disusun sebagai tutorial praktis dengan latihan berbasis dataset nyata. Cakupan teknis meliputi keamanan sumber, keamanan penyimpanan, command line, Docker, Aleph, email dumps, Python, CSV, JSON, SQL, geolocation metadata, dan case study investigasi.

Buku ini menempatkan keamanan operasional sebagai komponen awal analisis data. Perlindungan sumber, minimisasi data trail, autentikasi dataset, redaction, dan pengamanan perangkat menjadi bagian dari metodologi kerja sebelum proses analisis dilakukan.

---

## 2. Tujuan Utama Buku

Tujuan utama buku ini adalah memberikan kemampuan teknis untuk menganalisis dataset besar dari sumber publik, hack, leak, arsip, atau whistleblower. Kemampuan tersebut mencakup:

- menerima dataset secara aman;
- menilai sensitivitas dataset;
- melindungi sumber dan tim investigasi;
- menyimpan dataset dengan kontrol keamanan yang sesuai;
- memverifikasi keaslian dataset;
- melakukan pencarian awal melalui command line;
- membuat dataset dapat dicari melalui Aleph;
- membaca dan mencari email dump;
- menulis script Python untuk otomatisasi investigasi;
- menganalisis format CSV, JSON, dan SQL;
- memetakan metadata lokasi;
- membangun tool investigasi khusus;
- menyusun temuan dari dataset ke dalam laporan publik.

---

## 3. Struktur Buku

| Bagian | Bab | Fokus Utama | Hasil Pembelajaran |
|---|---:|---|---|
| Part I: Sources and Datasets | 1-2 | Perlindungan sumber, keamanan dataset, akuisisi data | Pembaca memahami risiko awal sebelum analisis dataset |
| Part II: Tools of the Trade | 3-6 | Command line, server cloud, Docker, Aleph, email dump | Pembaca dapat melakukan eksplorasi dan pencarian dataset |
| Part III: Python Programming | 7-8 | Dasar Python dan otomasi analisis file | Pembaca dapat menulis script untuk memproses dataset besar |
| Part IV: Structured Data | 9-12 | CSV, BlueLeaks Explorer, JSON, SQL | Pembaca dapat menganalisis format data terstruktur |
| Part V: Case Studies | 13-14 | AFLDS dan leaked chat logs | Pembaca memahami penerapan metode pada investigasi nyata |
| Appendices | A-B | WSL dan web scraping | Pembaca memperoleh dukungan teknis tambahan |

---

## 4. Ringkasan Eksekutif

*Hacks, Leaks, and Revelations* adalah buku teknis tentang analisis dataset hasil hack dan leak untuk kebutuhan jurnalisme investigasi dan riset publik. Materi disusun dari aspek keamanan operasional sampai analisis data terstruktur. Pendekatan buku ini berbasis latihan langsung menggunakan dataset nyata.

Bagian awal membahas perlindungan sumber, komunikasi aman, penyimpanan dataset, klasifikasi sensitivitas data, autentikasi dataset, redaction, password manager, disk encryption, dan proteksi dari dokumen berbahaya. Bagian ini menjadi dasar kerja investigasi yang melibatkan data sensitif dan risiko terhadap sumber.

Bagian berikutnya membahas perangkat kerja teknis. Command line digunakan untuk menilai ukuran dataset, membuat inventory file, mencari keyword, memproses folder besar, dan menjalankan shell script. Docker digunakan untuk menjalankan software kompleks. Aleph digunakan untuk indexing, search, entity extraction, dan investigasi dataset besar. Email dumps dianalisis melalui format EML, MBOX, dan PST.

Bagian pemrograman memperkenalkan Python untuk otomasi investigasi. Pembaca mempelajari variable, string, list, loop, control flow, function, module, argument command line, filesystem traversal, dictionary, file I/O, dan pemrosesan struktur data. Materi ini diarahkan pada kebutuhan praktis, yaitu menganalisis dataset dengan jumlah file besar.

Bagian structured data membahas CSV, JSON, dan SQL melalui dataset BlueLeaks, Parler, dan Epik. Pembaca mempelajari cara membaca spreadsheet, membuat output HTML dari bulk email, membangun CSV baru, menggunakan jq untuk JSON, memfilter metadata video, menghitung jarak GPS, membuat KML, mengimpor data SQL, dan menjalankan query database.

Bagian case study membahas investigasi America’s Frontline Doctors dan leaked neo-Nazi chat logs. Dua bab ini menunjukkan penggunaan teknik command line, Python, structured data, autentikasi data, dan pelaporan investigatif pada kasus nyata.

---

## 5. Chapter-by-Chapter Summary

### Chapter 1 - Protecting Sources and Yourself

**Fokus:** perlindungan sumber, keamanan dataset, autentikasi data, redaction, disk encryption, malicious document handling.

Bab ini membahas risiko yang muncul saat bekerja dengan sumber, whistleblower, hacker source, dan dataset sensitif. Materi mencakup komunikasi aman, pengurangan digital trail, penyimpanan data berdasarkan tingkat sensitivitas, autentikasi dataset, redaction, request for comment, password manager, disk encryption, dan penggunaan Dangerzone untuk dokumen berisiko.

**Poin penting:**

- Perlindungan sumber perlu dimulai sebelum komunikasi pertama.
- Peneliti perlu mengurangi digital trail dari sisi sumber dan penerima data.
- Dataset perlu diklasifikasikan menjadi low, medium, atau high sensitivity.
- Low-sensitivity dataset dapat diproses dengan kontrol standar.
- Medium-sensitivity dataset perlu disimpan pada disk terenkripsi.
- High-sensitivity dataset perlu diproses dengan air-gapped computer.
- Autentikasi dataset perlu dilakukan sebelum publikasi.
- Redaction perlu mempertimbangkan risiko terhadap sumber dan subjek data.
- Dokumen dari sumber eksternal perlu diperlakukan sebagai potensi malicious document.

**Implikasi teknis:** investigasi dataset membutuhkan operational security, data handling policy, dan prosedur autentikasi sebelum analisis substansi.

---

### Chapter 2 - Acquiring Datasets

**Fokus:** akuisisi dataset, DDoSecrets, BitTorrent, Signal, PGP, Tor, OnionShare, SecureDrop, encrypted drives, VPS.

Bab ini membahas cara memperoleh dataset secara aman dari sumber publik atau sumber langsung. Materi mencakup Distributed Denial of Secrets, BitTorrent, BlueLeaks, komunikasi terenkripsi, PGP, Tor Browser, OnionShare, encrypted USB drive, virtual private server, dan whistleblower submission system.

**Poin penting:**

- Akuisisi dataset perlu mempertimbangkan keamanan sumber dan keamanan penerima.
- Dataset publik dapat diunduh dari platform arsip atau transparency collective.
- BitTorrent dapat digunakan untuk dataset berukuran besar.
- Signal mendukung komunikasi terenkripsi dengan sumber.
- PGP dapat digunakan untuk pesan dan file terenkripsi.
- Tor dan OnionShare mendukung anonimitas dan transfer file.
- SecureDrop sesuai untuk organisasi yang menerima leak dari sumber anonim.
- Media fisik seperti encrypted USB drive dapat digunakan pada kondisi tertentu.

**Implikasi teknis:** proses akuisisi dataset memerlukan pemilihan channel yang sesuai dengan sensitivitas data dan risiko sumber.

---

### Chapter 3 - The Command Line Interface

**Fokus:** shell, filesystem, command line, package manager, cURL, VS Code, shell script.

Bab ini memperkenalkan penggunaan command line untuk pengguna tanpa asumsi pengalaman sebelumnya. Materi mencakup shell, user, path, privilege, navigasi folder, man page, tab completion, quoting, package manager, cURL, editor teks, dan shell script.

**Poin penting:**

- Command line memberi kontrol yang efisien atas file dan folder.
- Path absolut dan relatif perlu dipahami sebelum analisis dataset.
- Package manager membantu instalasi tool investigasi.
- cURL dapat digunakan untuk mengambil konten web.
- Shell script membantu menjalankan urutan perintah secara konsisten.
- Penguasaan terminal menjadi dasar untuk analisis pada bab berikutnya.

**Implikasi teknis:** CLI menjadi fondasi untuk eksplorasi dataset besar, otomasi, dan penggunaan tool tanpa graphical interface.

---

### Chapter 4 - Exploring Datasets in the Terminal

**Fokus:** unzip, for loop, disk usage, pipe, sort, inventory file, grep, regex, VPS, SSH, byobu.

Bab ini membahas eksplorasi dataset melalui terminal. BlueLeaks digunakan sebagai contoh utama. Pembaca mempelajari unzip, organisasi file, perhitungan ukuran folder, pipe, sort, inventory file, hitung jumlah file, pencarian keyword dengan grep, regex, pencarian bulk, dan analisis remote melalui VPS.

**Poin penting:**

- Dataset besar perlu dinilai dari ukuran, jumlah file, struktur folder, dan jenis file.
- `du`, `sort`, dan pipe membantu memahami distribusi ukuran data.
- Inventory filename membantu pemetaan awal dataset.
- `grep` dapat digunakan untuk pencarian keyword dalam jumlah besar.
- Regex membantu pencarian pola.
- VPS dapat digunakan untuk analisis jarak jauh saat resource lokal terbatas.
- SSH key dan session manager mendukung kerja remote yang stabil.

**Implikasi teknis:** eksplorasi awal dataset perlu menghasilkan peta kerja dasar sebelum analisis lanjutan.

---

### Chapter 5 - Docker, Aleph, and Making Datasets Searchable

**Fokus:** Docker, container, Docker Compose, Aleph, indexing, search interface, dataset investigation.

Bab ini memperkenalkan Docker untuk menjalankan software kompleks secara terisolasi. Aleph digunakan sebagai platform untuk indexing dan pencarian dataset. Materi mencakup container, volume, environment variable, Docker Compose, deployment lokal Aleph, indexing folder BlueLeaks, status indexing, search, dataset, investigation, dan fitur tambahan Aleph.

**Poin penting:**

- Docker mempermudah instalasi tool yang memiliki banyak dependensi.
- Volume digunakan untuk menghubungkan file host ke container.
- Docker Compose membantu menjalankan multi-container application.
- Aleph dapat digunakan untuk membuat dataset besar dapat dicari.
- Indexing membantu pencarian dokumen, entity, dan hubungan antar data.
- Dedicated Aleph server diperlukan untuk kolaborasi atau dataset besar.

**Implikasi teknis:** dataset besar memerlukan search platform agar proses investigasi berjalan sistematis dan dapat direplikasi.

---

### Chapter 6 - Reading Other People’s Email

**Fokus:** email dump, EML, MBOX, PST, Thunderbird, search, Outlook, Aleph.

Bab ini membahas analisis email dump dari berbagai format. Materi mencakup struktur protokol email, EML, MBOX, PST, penggunaan Thunderbird, import email, quick filter, search messages dialog, Outlook, dan Aleph.

**Poin penting:**

- Email dump memiliki format teknis yang berbeda.
- EML menyimpan satu email per file.
- MBOX menyimpan banyak email dalam satu file.
- PST merupakan format Outlook.
- Thunderbird dapat digunakan untuk membaca dan mencari email dump.
- Aleph dapat digunakan untuk indexing dan pencarian email dalam dataset besar.
- Analisis email perlu memperhatikan metadata, lampiran, thread, sender, recipient, dan waktu.

**Implikasi teknis:** email dump perlu diproses dengan tool yang mendukung format asal data dan kebutuhan pencarian.

---

### Chapter 7 - An Introduction to Python

**Fokus:** instalasi Python, script, interpreter, variable, string, list, loop, control flow, function.

Bab ini memberikan dasar Python untuk pembaca yang perlu melakukan otomasi investigasi. Materi mencakup instalasi, script pertama, interpreter, komentar, operasi matematika, string, list, loop, comparison operator, if statement, nested block, logical operator, exception handling, function, default argument, return value, dan docstring.

**Poin penting:**

- Python digunakan untuk mengotomasi analisis dataset.
- List dan loop membantu memproses kumpulan item.
- Control flow membantu menerapkan kondisi seleksi.
- Exception handling membantu menangani data yang tidak konsisten.
- Function membantu membuat kode lebih terstruktur.
- Docstring membantu dokumentasi fungsi.

**Implikasi teknis:** dasar Python memungkinkan pembaca membuat tool analisis khusus untuk dataset yang memiliki struktur beragam.

---

### Chapter 8 - Working with Data in Python

**Fokus:** module, script template, os.walk, file traversal, Click, argument, dictionary, list, file I/O.

Bab ini mengembangkan dasar Python untuk bekerja dengan file dan struktur data. Materi mencakup module, template script, traversal folder dengan `os.walk()`, mencari file terbesar, third-party module, command line argument dengan Click, dictionary, list, data nested, mapping CSV dalam BlueLeaks, membaca file, dan menulis file.

**Poin penting:**

- `os.walk()` membantu memproses folder bertingkat.
- Command line argument membuat script dapat digunakan untuk dataset berbeda.
- Dictionary digunakan untuk menyimpan data dengan pasangan key-value.
- Struktur list dan dictionary sering muncul pada data hasil parsing.
- File I/O diperlukan untuk membuat output investigasi.
- Script perlu menghindari hardcoding agar dapat digunakan ulang.

**Implikasi teknis:** Python dapat mengubah analisis manual menjadi proses yang konsisten, dapat diuji, dan dapat diterapkan pada dataset besar.

---

### Chapter 9 - BlueLeaks, Black Lives Matter, and the CSV File Format

**Fokus:** CSV, spreadsheet, Python CSV processing, bulk email, HTML output, BlueLeaks sites.

Bab ini membahas format CSV dan penerapannya pada BlueLeaks. Materi mencakup penggunaan spreadsheet, struktur CSV, text editor, analisis fusion center, SAR, pembacaan dan penulisan CSV dengan Python, pemrosesan bulk email, HTML primer, pembuatan output HTML dari email, dan pembuatan CSV daftar situs BlueLeaks.

**Poin penting:**

- CSV merupakan format umum pada dataset hasil leak.
- Spreadsheet membantu inspeksi awal data tabular.
- Text editor membantu memahami struktur file secara langsung.
- Python dapat digunakan untuk membaca baris CSV dan menghasilkan output yang lebih mudah dibaca.
- Bulk email dapat dikonversi menjadi HTML untuk review.
- CSV baru dapat dibuat dari hasil ekstraksi data.

**Implikasi teknis:** analisis CSV perlu mencakup inspeksi manual, pemrosesan otomatis, dan transformasi output.

---

### Chapter 10 - BlueLeaks Explorer

**Fokus:** aplikasi investigasi khusus, struktur dataset, relationship, backend, frontend.

Bab ini memperkenalkan BlueLeaks Explorer, aplikasi khusus untuk investigasi BlueLeaks. Materi mencakup instalasi dengan Docker Compose, database initialization, struktur NCRIC, tabel, relationship, keyword search, definisi struktur JRIC, field type, relationship building, verifikasi data, backend, dan frontend.

**Poin penting:**

- Dataset kompleks dapat memerlukan aplikasi khusus.
- Struktur data perlu didefinisikan agar pencarian dan relasi dapat dipahami.
- Field type memengaruhi cara data ditampilkan dan dicari.
- Relationship antar tabel membantu analisis konteks.
- Backend dan frontend perlu dirancang berdasarkan kebutuhan investigasi.
- Verifikasi data tetap menjadi tahap penting.

**Implikasi teknis:** tool investigasi khusus dapat meningkatkan efektivitas analisis dataset yang memiliki struktur relasional atau semi-relasional.

---

### Chapter 11 - Parler, the January 6 Insurrection, and the JSON File Format

**Fokus:** JSON, Parler video metadata, GPS coordinates, jq, Python filtering, KML, Google Earth, ExifTool.

Bab ini membahas format JSON melalui dataset Parler. Materi mencakup asal dataset Parler, metadata video, sintaks JSON, parsing JSON dengan Python, exception handling, jq, pencarian video dengan GPS coordinates, filtering video tanggal 6 Januari 2021, koordinat latitude/longitude, konversi format GPS, perhitungan jarak, KML, Google Earth, dan ExifTool.

**Poin penting:**

- JSON sering digunakan untuk metadata aplikasi dan platform.
- Python dan jq dapat digunakan untuk parsing dan filtering JSON.
- Metadata lokasi dapat digunakan untuk analisis kejadian berbasis tempat dan waktu.
- Exception handling penting karena data JSON dapat memiliki field yang hilang atau tidak konsisten.
- KML dapat digunakan untuk visualisasi koordinat pada peta.
- ExifTool dapat digunakan untuk membaca metadata file media.

**Implikasi teknis:** JSON analysis dapat mendukung investigasi berbasis metadata waktu, lokasi, dan file media.

---

### Chapter 12 - Epik Fail, Extremism Research, and SQL Databases

**Fokus:** SQL database, relational model, MySQL, Adminer, query, JOIN, Epik dataset.

Bab ini membahas database SQL melalui dataset Epik. Materi mencakup relational database, client-server model, table, column, type, MySQL server via Docker, Adminer, INSERT, SELECT, JOIN, UPDATE, DELETE, MySQL CLI, import data, domain table, privacy table, hosting table, hosting_server table, dan analisis ownership domain.

**Poin penting:**

- SQL database menyimpan data dalam tabel yang memiliki relasi.
- JOIN digunakan untuk mengambil data dari beberapa tabel.
- Import dataset ke MySQL memungkinkan query yang lebih kuat.
- Database client membantu eksplorasi visual.
- CLI MySQL membantu analisis yang dapat direplikasi.
- Dataset domain dan hosting dapat digunakan untuk analisis ownership dan infrastruktur.

**Implikasi teknis:** pemahaman SQL diperlukan untuk menganalisis dataset hasil leak yang berasal dari aplikasi web, registrar, hosting provider, atau sistem internal.

---

### Chapter 13 - Pandemic Profiteers and COVID-19 Disinformation

**Fokus:** AFLDS, Cadence Health, Ravkoo, encrypted container, CSV/JSON analysis, revenue calculation, data authentication.

Bab ini merupakan case study investigasi America’s Frontline Doctors. Materi mencakup asal dataset, data Cadence Health dan Ravkoo, ekstraksi ke encrypted file container, analisis command line, pembuatan spreadsheet pasien, perhitungan revenue prescription, kategori obat, analisis patient data, identifikasi partner, pencarian pasien berdasarkan kota dan usia, autentikasi data, dampak setelah publikasi, HIPAA breach notification rule, dan congressional investigation.

**Poin penting:**

- Dataset investigasi dapat memiliki data pribadi yang sensitif.
- Encrypted container digunakan untuk pengamanan data selama analisis.
- CSV dan JSON dapat digabungkan untuk menghitung pola transaksi.
- Revenue calculation perlu didasarkan pada field harga dan jumlah.
- Segmentasi data dapat dilakukan berdasarkan obat, kota, usia, dan partner.
- Autentikasi data dilakukan sebelum temuan dipublikasikan.
- Laporan investigasi dapat memicu respons hukum, regulasi, atau politik.

**Implikasi teknis:** case study ini menunjukkan hubungan antara data handling, analisis struktural, autentikasi, dan pelaporan publik.

---

### Chapter 14 - Neo-Nazis and Their Chatrooms

**Fokus:** leaked chat logs, JSON, jq, timestamp conversion, username mapping, SQL database, web interface, DiscordLeaks.

Bab ini membahas analisis leaked chat logs dari kelompok neo-Nazi. Materi mencakup infiltrasi server Discord oleh antifascist, JSON chat logs, jq, konversi timestamp, pencarian username, Discord History Tracker, script pencarian JSON, desain SQL database, import chat log, web interface, DiscordLeaks, Patriot Front chat logs, dan dampak litigasi terkait Unite the Right.

**Poin penting:**

- Chat log memerlukan parsing terhadap user, message, channel, server, dan timestamp.
- JSON nested structure perlu dipetakan sebelum pencarian efektif dilakukan.
- Username mapping diperlukan untuk menghubungkan pesan dengan identitas internal dataset.
- SQL database membantu pencarian dan analisis skala besar.
- Web interface dapat membantu peneliti non-teknis mengeksplorasi data.
- Tool investigasi publik dapat mendukung pelaporan dan proses hukum.

**Implikasi teknis:** analisis chat log membutuhkan parsing struktur data, normalisasi identitas, query, dan interface pencarian.

---

### Appendix A - Solutions to Common WSL Problems

**Fokus:** Windows Subsystem for Linux, filesystem, disk performance, active dataset storage.

Appendix ini membahas masalah umum pada WSL. Topik mencakup Linux filesystem, disk performance, penyimpanan dataset aktif di Linux filesystem, dan penggunaan USB disk untuk filesystem Linux.

**Poin penting:**

- Performa disk pada WSL dapat memengaruhi analisis dataset.
- Lokasi penyimpanan file memengaruhi kecepatan operasi.
- Dataset aktif perlu ditempatkan pada filesystem yang sesuai untuk analisis.
- Pengguna Windows perlu mengikuti struktur kerja yang mengurangi masalah performa.

**Implikasi teknis:** pengaturan lingkungan kerja memengaruhi efisiensi analisis dataset besar.

---

### Appendix B - Scraping the Web

**Fokus:** legal considerations, HTTP requests, HTTPX, Beautiful Soup, Selenium.

Appendix ini membahas web scraping untuk membangun dataset dari web publik. Materi mencakup pertimbangan hukum, HTTP request, teknik scraping, HTTPX, parsing HTML dengan Beautiful Soup, dan browser automation dengan Selenium.

**Poin penting:**

- Web scraping perlu mempertimbangkan aspek hukum dan kebijakan situs.
- HTTPX dapat digunakan untuk mengambil halaman web.
- Beautiful Soup membantu parsing HTML.
- Selenium membantu otomatisasi browser untuk halaman yang membutuhkan interaksi.
- Scraping dapat digunakan untuk membangun dataset investigasi dari sumber publik.

**Implikasi teknis:** web scraping dapat mendukung pengumpulan data publik jika dilakukan dengan kontrol hukum, teknis, dan etika.

---

## 6. Konsep Teknis Penting

| Konsep | Penjelasan | Relevansi |
|---|---|---|
| Source protection | Praktik melindungi identitas dan keselamatan sumber | Menurunkan risiko terhadap whistleblower atau source sensitif |
| Digital trail minimization | Pengurangan log, metadata, dan riwayat komunikasi yang dapat mengarah ke sumber | Mengurangi risiko identifikasi sumber |
| Dataset sensitivity classification | Klasifikasi dataset berdasarkan risiko low, medium, high | Menentukan metode penyimpanan dan analisis |
| Dataset authentication | Verifikasi keaslian dataset sebelum publikasi | Menjaga akurasi dan kredibilitas investigasi |
| Redaction | Penghapusan atau penyamaran informasi sensitif | Mengurangi risiko terhadap sumber, subjek data, dan pihak terkait |
| Disk encryption | Enkripsi media penyimpanan internal dan eksternal | Melindungi data saat perangkat hilang, disita, atau dicuri |
| Malicious document handling | Sanitasi atau isolasi dokumen dari sumber eksternal | Mengurangi risiko malware |
| Command line analysis | Penggunaan terminal untuk eksplorasi, pencarian, dan otomasi | Efisien untuk dataset besar |
| grep and regex | Pencarian keyword dan pola teks | Mendukung triage data awal |
| VPS analysis | Analisis dataset pada server remote | Berguna saat resource lokal terbatas |
| Docker | Container untuk menjalankan software kompleks | Menyederhanakan setup tool investigasi |
| Aleph | Platform indexing dan pencarian dataset | Berguna untuk analisis dokumen dan entity |
| Email dump analysis | Analisis EML, MBOX, dan PST | Penting untuk investigasi komunikasi |
| Python scripting | Otomasi pemrosesan file dan struktur data | Mengurangi kerja manual |
| CSV processing | Pemrosesan data tabular | Umum pada leak dari database dan spreadsheet |
| JSON processing | Pemrosesan metadata dan struktur nested | Umum pada platform web dan aplikasi |
| SQL querying | Analisis database relasional | Penting untuk dump database aplikasi |
| Geospatial metadata | Analisis koordinat, jarak, dan visualisasi peta | Berguna untuk investigasi berbasis lokasi |
| Custom investigative tool | Aplikasi khusus untuk dataset tertentu | Mempercepat analisis kolektif |
| Web scraping | Pengumpulan data dari web publik | Mendukung pembuatan dataset riset |

---

## 7. Metodologi Investigasi yang Dapat Diambil

### 7.1 Tahap Persiapan

- Identifikasi sensitivitas dataset.
- Tentukan kebutuhan proteksi sumber.
- Pilih channel komunikasi aman.
- Siapkan media penyimpanan terenkripsi.
- Siapkan komputer kerja atau air-gapped computer sesuai risiko.
- Siapkan password manager dan update perangkat.
- Siapkan prosedur malicious document handling.

### 7.2 Tahap Akuisisi

- Pilih metode transfer dataset.
- Validasi hash atau metadata bila tersedia.
- Catat asal dataset dan batasan akses.
- Hindari upload dataset sensitif ke cloud tanpa enkripsi client-side.
- Pisahkan dataset mentah dari hasil analisis.

### 7.3 Tahap Autentikasi

- Bandingkan data dengan OSINT.
- Periksa metadata, format, timestamp, dan konsistensi struktur.
- Hubungi pihak terkait untuk request for comment jika aman.
- Gunakan subset data untuk cross-check.
- Dokumentasikan alasan keyakinan terhadap keaslian dataset.

### 7.4 Tahap Eksplorasi Awal

- Hitung ukuran dataset.
- Hitung jumlah file.
- Buat inventory filename.
- Identifikasi format file.
- Jalankan pencarian keyword awal.
- Pisahkan file relevan untuk analisis lanjutan.

### 7.5 Tahap Indexing dan Search

- Gunakan Aleph atau tool indexing lain.
- Index folder atau sub-dataset prioritas.
- Buat query pencarian berbasis entity, keyword, lokasi, organisasi, dan tanggal.
- Simpan hasil pencarian penting.
- Evaluasi relationship antar dokumen dan entity.

### 7.6 Tahap Pemrosesan Terstruktur

- Gunakan Python untuk parsing file.
- Gunakan CSV reader untuk data tabular.
- Gunakan jq atau Python JSON parser untuk JSON.
- Gunakan SQL untuk relational database.
- Buat output antara dalam format CSV, HTML, KML, atau database.

### 7.7 Tahap Analisis Temuan

- Validasi temuan dengan data lain.
- Catat query, script, dan versi dataset.
- Periksa risiko publikasi.
- Lakukan redaction bila diperlukan.
- Siapkan request for comment.
- Susun laporan dengan bukti yang dapat diverifikasi.

---

## 8. Relevansi untuk Cyber Intelligence

Buku ini relevan untuk cyber intelligence karena menjelaskan proses teknis untuk mengubah dataset besar menjadi temuan yang terstruktur. Konsep yang dapat digunakan dalam konteks cyber intelligence meliputi:

| Area Cyber Intelligence | Relevansi dari Buku |
|---|---|
| Source handling | Perlindungan sumber, komunikasi aman, minimisasi digital trail |
| Data acquisition | Transfer dataset, BitTorrent, OnionShare, SecureDrop |
| Data security | Enkripsi disk, air-gap, malicious document handling |
| Data authenticity | OSINT, cross-check, metadata validation |
| Large-scale triage | CLI, grep, regex, inventory file |
| Search infrastructure | Aleph, indexing, entity search |
| Communication analysis | Email dump, chat log, timestamp, sender-recipient relationship |
| Structured data analysis | CSV, JSON, SQL, Python |
| Geospatial intelligence | GPS metadata, distance calculation, KML |
| Investigation tooling | Custom web interface dan dataset-specific application |
| Reporting workflow | Redaction, request for comment, publication risk review |

---

## 9. Relevansi untuk Organisasi dan Tim Teknis

### 9.1 Untuk Jurnalis Investigasi

- Memberikan workflow teknis dari penerimaan data sampai publikasi.
- Menekankan keamanan sumber dan redaction.
- Menyediakan teknik untuk menganalisis data besar tanpa proses manual penuh.
- Memberikan contoh penggunaan data dalam laporan publik.

### 9.2 Untuk Security Engineer

- Memberikan kerangka operational security untuk dataset sensitif.
- Menunjukkan penggunaan encryption, isolation, dan tool hardening.
- Menjelaskan risiko malicious document.
- Menunjukkan cara membuat lingkungan analisis yang dapat direplikasi.

### 9.3 Untuk Data Analyst

- Memberikan proses analisis file, CSV, JSON, SQL, dan email.
- Menunjukkan penggunaan Python untuk otomasi.
- Memberikan contoh transformasi data menjadi output yang dapat dibaca.
- Menjelaskan pentingnya dokumentasi script dan argument command line.

### 9.4 Untuk Cyber Threat Intelligence Team

- Memberikan metode ingestion, indexing, dan pencarian dataset.
- Menunjukkan analisis entity, komunikasi, lokasi, dan relasi.
- Memberikan dasar untuk membangun investigative data platform.
- Mendukung pembuatan workflow untuk leak intelligence.

### 9.5 Untuk Legal, Compliance, dan Governance

- Menjelaskan pentingnya redaction dan request for comment.
- Menekankan klasifikasi sensitivitas dataset.
- Menunjukkan risiko PII dan data medis.
- Membantu penyusunan data handling policy untuk investigasi.

---

## 10. Risiko dan Batasan

| Risiko / Batasan | Penjelasan | Mitigasi |
|---|---|---|
| Risiko terhadap sumber | Publikasi detail tertentu dapat mengarah ke identitas sumber | Minimisasi digital trail, redaction, konsultasi hukum |
| Risiko hukum | Dataset hasil hack/leak dapat memiliki konsekuensi hukum | Konsultasi legal, pembatasan akses, dokumentasi proses |
| Risiko PII | Dataset dapat memuat data pribadi, medis, atau finansial | Klasifikasi sensitivitas, redaction, secure storage |
| Risiko malware | Dokumen dari sumber eksternal dapat berisi payload berbahaya | Dangerzone, sandbox, VM, isolation |
| Risiko salah autentikasi | Dataset palsu atau diubah dapat menghasilkan laporan salah | OSINT, cross-check, metadata review, request for comment |
| Risiko bias analisis | Keyword search dapat melewatkan konteks | Query berulang, sampling, review manual, validasi silang |
| Risiko resource | Dataset besar memerlukan storage, RAM, CPU, dan bandwidth | VPS, indexing tool, pemisahan sub-dataset |
| Risiko reidentification | Data yang sudah direduksi tetap dapat mengarah ke individu | Redaction bertingkat, aggregation, privacy review |
| Risiko chain of custody | Proses analisis tanpa catatan dapat menurunkan kredibilitas | Catat hash, path, script, query, dan transformasi |

---

## 11. Highlight Utama per Topik

| Topik | Highlight |
|---|---|
| Source protection | Perlindungan sumber perlu menjadi tahap awal sebelum analisis substansi |
| Sensitivity classification | Tingkat sensitivitas menentukan media penyimpanan dan prosedur kerja |
| Authentication | Keaslian dataset perlu dibuktikan melalui OSINT, metadata, cross-check, atau validasi pihak terkait |
| Redaction | Publikasi data perlu mempertimbangkan risiko terhadap sumber dan subjek data |
| CLI | Terminal membantu triage dataset besar secara cepat |
| grep and regex | Pencarian pola membantu menemukan dokumen relevan |
| Docker | Container menyederhanakan penggunaan tool analisis kompleks |
| Aleph | Indexing mempercepat pencarian dan analisis dokumen besar |
| Email dump | Format email perlu dipahami sebelum analisis komunikasi |
| Python | Script membantu otomatisasi analisis file dan struktur data |
| CSV | Format tabular perlu dianalisis dengan kombinasi spreadsheet dan script |
| JSON | Struktur nested perlu diparse dengan jq atau Python |
| SQL | Relasi antar tabel perlu dianalisis dengan query dan JOIN |
| GPS metadata | Koordinat dapat digunakan untuk analisis lokasi dan waktu |
| Custom tool | Dataset kompleks dapat memerlukan aplikasi pencarian khusus |
| Case study | Metode teknis perlu dikaitkan dengan autentikasi, redaction, dan pelaporan |

---

## 12. Reading Path yang Disarankan

### Untuk Pembaca Non-Teknis

1. Chapter 1
2. Chapter 2
3. Chapter 3
4. Chapter 6
5. Chapter 9
6. Chapter 13
7. Chapter 14

### Untuk Data Analyst

1. Chapter 3
2. Chapter 4
3. Chapter 7
4. Chapter 8
5. Chapter 9
6. Chapter 11
7. Chapter 12

### Untuk Security Engineer

1. Chapter 1
2. Chapter 2
3. Chapter 4
4. Chapter 5
5. Chapter 6
6. Appendix A
7. Appendix B

### Untuk Cyber Intelligence Team

1. Chapter 1
2. Chapter 2
3. Chapter 4
4. Chapter 5
5. Chapter 6
6. Chapter 9
7. Chapter 10
8. Chapter 11
9. Chapter 12
10. Chapter 13
11. Chapter 14

---

## 13. Output yang Dapat Diadaptasi dari Buku

| Output | Dasar Materi |
|---|---|
| SOP penerimaan leaked dataset | Chapter 1-2 |
| Dataset sensitivity classification matrix | Chapter 1 |
| Secure dataset storage policy | Chapter 1 |
| Source communication protocol | Chapter 1-2 |
| Data authentication checklist | Chapter 1, Chapter 13, Chapter 14 |
| Redaction guideline | Chapter 1 |
| CLI triage playbook | Chapter 3-4 |
| Dataset indexing workflow | Chapter 5 |
| Email dump analysis workflow | Chapter 6 |
| Python analysis template | Chapter 7-8 |
| CSV analysis workflow | Chapter 9 |
| Custom investigation platform blueprint | Chapter 10 |
| JSON metadata analysis workflow | Chapter 11 |
| SQL leak analysis workflow | Chapter 12 |
| Case study report template | Chapter 13-14 |
| Web scraping governance note | Appendix B |

---

## 14. Ringkasan Teknis Satu Halaman

*Hacks, Leaks, and Revelations* adalah panduan teknis untuk menganalisis dataset hasil hack dan leak. Materi buku mencakup keamanan sumber, penyimpanan dataset, autentikasi data, redaction, command line, Docker, Aleph, email dump, Python, CSV, JSON, SQL, geospatial metadata, web scraping, dan case study investigasi.

Workflow utama yang dapat diambil dari buku:

1. Klasifikasikan sensitivitas dataset.
2. Lindungi sumber dan kurangi digital trail.
3. Simpan dataset pada media yang sesuai dengan risiko.
4. Autentikasi dataset sebelum publikasi.
5. Lakukan triage awal dengan command line.
6. Buat inventory file dan pencarian keyword.
7. Index dataset dengan Aleph atau tool setara.
8. Gunakan Python untuk otomasi analisis.
9. Proses format CSV, JSON, dan SQL sesuai struktur data.
10. Validasi temuan dengan sumber data lain.
11. Lakukan redaction dan risk review.
12. Susun laporan dengan bukti yang dapat diverifikasi.

---

## 15. Final Key Takeaways

- Analisis dataset hasil hack/leak memerlukan keamanan operasional sejak tahap awal.
- Perlindungan sumber dan keamanan penyimpanan perlu ditentukan sebelum eksplorasi data.
- Autentikasi dataset merupakan syarat utama sebelum publikasi temuan.
- Redaction perlu dilakukan berdasarkan risiko terhadap sumber, subjek data, dan pihak terkait.
- Command line efektif untuk triage dataset besar.
- Docker dan Aleph membantu indexing dan pencarian dataset besar.
- Email dump memerlukan pemahaman format EML, MBOX, dan PST.
- Python diperlukan untuk otomasi analisis file dan data terstruktur.
- CSV, JSON, dan SQL merupakan format penting dalam dataset hasil leak.
- Metadata lokasi dapat digunakan untuk analisis kejadian berbasis waktu dan tempat.
- Tool investigasi khusus dapat diperlukan untuk dataset kompleks.
- Case study AFLDS dan neo-Nazi chat logs menunjukkan penerapan workflow teknis pada investigasi nyata.
- Buku ini dapat dijadikan rujukan untuk SOP investigasi data, cyber intelligence workflow, dan secure data handling.
