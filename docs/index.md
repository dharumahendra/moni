_Modul Praktikum Senior Project TI_  
**Departemen Teknologi Elektro dan Teknologi Informasi, Fakultas Teknik, Universitas Gadjah Mada**

---

## Identitas Kelompok

**Nama Kelompok:** MONITOR

**Anggota Kelompok:**

1. Muhammad Zakiyyuddin Abdul Adhiim - 24/545668/TK/60719
2. Dharu Bintang Mahendratama - 24/535960/TK/59484
3. Razaqi Alkautsar - 24/544958/TK/60570

---

## Jawaban Modul 1

### 1. Nama Produk

MONI

### 2. Jenis Produk

Aplikasi Web

### 3. Latar Belakang & Permasalahan

Mobilitas global masyarakat untuk studi dan bekerja di luar negeri terus meningkat, namun persiapan finansial sering kali menjadi titik kritis yang menggagalkan rencana tersebut. Menurut laporan World Bank (2025), lebih dari 40% calon pekerja dan mahasiswa internasional dari negara berkembang mengalami financial shortfall (kekurangan dana) yang dipicu oleh volatilitas nilai tukar mata uang dan inflasi di negara tujuan. Sebagai contoh, fluktuasi nilai tukar Rupiah (IDR) terhadap Dolar Australia (AUD) atau Euro (EUR) seringkali mengalami deviasi 5-8% hanya dalam kurun waktu 6 bulan (Bank Indonesia, 2026).

Hal ini membuat metode "tabungan statis" bulanan pada aplikasi pencatatan keuangan konvensional menjadi tidak relevan dan sangat berisiko. Aplikasi saat ini hanya mencatat histori pengeluaran masa lalu tanpa memperhitungkan variabel makroekonomi real-time. Jika dibiarkan, selisih kurs ini dapat memicu defisit dana hingga belasan juta rupiah tepat menjelang keberangkatan. Oleh karena itu, terdapat urgensi yang tinggi untuk menghadirkan sistem pencatatan keuangan (sinking fund) yang proaktif, di mana AI dapat secara dinamis mengalkulasi ulang target tabungan harian mengikuti pergerakan pasar global, sehingga mencegah kegagalan finansial di menit-menit terakhir.

### 4. Ide Solusi

Solusi yang diusulkan adalah membangun “MONI", sebuah aplikasi web pencatatan keuangan (sinking fund) proaktif yang mengintegrasikan data makroekonomi real-time. Untuk mengatasi masalah fluktuasi kurs, sistem diarsiteki dengan background worker (cron job) yang secara otomatis menarik data nilai tukar mata uang dari API finansial publik. Data ini diproses oleh model Machine Learning (seperti regresi deret waktu) guna memprediksi tren kurs jangka pendek dan mengalkulasi ulang target tabungan harian secara dinamis. Jika model mendeteksi potensi defisit dana akibat pelemahan nilai tukar, sistem akan menganalisis histori transaksi pengguna untuk merekomendasikan pemangkasan anggaran pada kategori pengeluaran non-esensial. Guna memastikan kelayakan teknis (feasibility) dan keamanan sistem, arsitektur data difokuskan pada mekanisme pencatatan manual dan agregasi melalui unggahan dokumen mutasi rekening (CSV), sehingga sistem dapat beroperasi stabil tanpa bergantung pada kerumitan birokrasi integrasi API perbankan (open banking).

### 5. Analisis Kompetitor

<table>
  <thead>
    <tr>
      <th colspan="2" style="text-align: center; background-color: #333; color: white;">KOMPETITOR 1</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: right; width: 25%;"><strong>Nama</strong></td>
      <td>YNAB (You Need A Budget)</td>
    </tr>
    <tr>
      <td style="text-align: right;"><strong>Jenis Kompetitor</strong></td>
      <td>Indirect Competitors</td>
    </tr>
    <tr>
      <td style="text-align: right;"><strong>Jenis Produk</strong></td>
      <td>Web Budgeting</td>
    </tr>
    <tr>
      <td style="text-align: right;"><strong>Target Customer</strong></td>
      <td>Individu pengelola arus kas bulanan berbasis target.</td>
    </tr>
    <tr>
      <th style="text-align: center; width: 50%;">Kelebihan</th>
      <th style="text-align: center; width: 50%;">Kekurangan</th>
    </tr>
    <tr>
      <td style="vertical-align: top;">
        <ul>
          <li>Metodologi zero-based budgeting yang ketat dan pencatatan target (goal tracking) yang solid.</li>
          <li>Menyediakan fitur goal tracking yang sangat terstruktur, memungkinkan pengguna memisahkan target pendanaan untuk berbagai proyek sekaligus.</li>
          <li>Ekosistem pelaporan visual yang sangat mendetail, memudahkan pelacakan rasio utang, aset, dan riwayat pengeluaran dari bulan ke bulan.</li>
        </ul>
      </td>
      <td style="vertical-align: top;">
        <ul>
          <li>Target nominal bersifat kaku/statis, tidak merespons perubahan kurs asing atau inflasi.</li>
          <li>Kurva pembelajaran (learning curve) sangat curam, membuat pengguna baru sering kesulitan mengadopsi antarmuka dan konsep metodologinya di minggu-minggu pertama.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <th colspan="2" style="text-align: left;">Key Competitive Advantage & Unique Value</th>
    </tr>
    <tr>
      <td colspan="2">MONI merespons volatilitas makroekonomi dengan mengubah besaran target secara otonom.</td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th colspan="2" style="text-align: center; background-color: #333; color: white;">KOMPETITOR 2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: right; width: 25%;"><strong>Nama</strong></td>
      <td>Wise</td>
    </tr>
    <tr>
      <td style="text-align: right;"><strong>Jenis Kompetitor</strong></td>
      <td>Indirect Competitors</td>
    </tr>
    <tr>
      <td style="text-align: right;"><strong>Jenis Produk</strong></td>
      <td>Dompet Digital / E-Wallet Multi-Currency</td>
    </tr>
    <tr>
      <td style="text-align: right;"><strong>Target Customer</strong></td>
      <td>Ekspatriat, pelancong, atau mahasiswa internasional.</td>
    </tr>
    <tr>
      <th style="text-align: center; width: 50%;">Kelebihan</th>
      <th style="text-align: center; width: 50%;">Kekurangan</th>
    </tr>
    <tr>
      <td style="vertical-align: top;">
        <ul>
          <li>Konversi kurs valas riil, murah, dan transparan.</li>
          <li>Kemampuan menampung puluhan mata uang asing berbeda di dalam satu dompet digital, memudahkan persiapan dana sebelum relokasi.</li>
          <li>Terintegrasi langsung dengan kartu debit internasional, sehingga dana yang disiapkan dapat langsung digesek saat pengguna tiba di negara destinasi.</li>
        </ul>
      </td>
      <td style="vertical-align: top;">
        <ul>
          <li>Murni fasilitas penyimpan dana; tidak menganalisis transaksi pengeluaran harian pengguna.</li>
          <li>Tidak memiliki kecerdasan buatan atau algoritma prediktif yang secara proaktif memperingatkan pengguna jika target tabungan berjalan melambat.</li>
          <li>Tidak menyediakan fitur visualisasi lintasan proyeksi (<em>forecasting chart</em>) untuk memantau kelayakan dana terhadap tenggat waktu keberangkatan.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <th colspan="2" style="text-align: left;">Key Competitive Advantage & Unique Value</th>
    </tr>
    <tr>
      <td colspan="2">MONI menggabungkan kemampuan pemantauan kurs valas dengan sistem manajemen pengeluaran harian yang proaktif.</td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th colspan="2" style="text-align: center; background-color: #333; color: white;">KOMPETITOR 3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: right; width: 25%;"><strong>Nama</strong></td>
      <td>Cleo</td>
    </tr>
    <tr>
      <td style="text-align: right;"><strong>Jenis Kompetitor</strong></td>
      <td>Tertiary Competitors</td>
    </tr>
    <tr>
      <td style="text-align: right;"><strong>Jenis Produk</strong></td>
      <td>AI Financial Assistant App</td>
    </tr>
    <tr>
      <td style="text-align: right;"><strong>Target Customer</strong></td>
      <td>Gen Z dan mahasiswa yang butuh asistensi cash flow.</td>
    </tr>
    <tr>
      <th style="text-align: center; width: 50%;">Kelebihan</th>
      <th style="text-align: center; width: 50%;">Kekurangan</th>
    </tr>
    <tr>
      <td style="vertical-align: top;">
        <ul>
          <li>Prediksi kas jangka pendek yang sangat akurat dengan UI interaktif.</li>
          <li>Memiliki antarmuka chat-based interaktif yang sangat intuitif, membuat pencatatan keuangan terasa seperti mengobrol dengan asisten personal. </li>
          <li>Algoritma pendeteksi pola transaksi yang sangat akurat dalam mengidentifikasi tagihan berulang dan memprediksi krisis arus kas jangka pendek.</li>
          <li>Memanfaatkan gamifikasi yang kuat, seperti mengirimkan notifikasi agresif (fitur "Roast") saat pengguna terdeteksi melakukan pemborosan tidak perlu.</li>
        </ul>
      </td>
      <td style="vertical-align: top;">
        <ul>
          <li>Hanya berfokus pada survival akhir bulan, tidak memiliki arsitektur proyeksi lintasan untuk target lintas negara.</li>
          <li>Hanya berfokus pada keselamatan arus kas jangka pendek (siklus bulanan), dan tidak dirancang untuk manajemen proyeksi target (milestone) jangka panjang lintas tahun. </li>
          <li>Tidak mendukung arsitektur multi-mata uang atau tarikan data makroekonomi valas global, membuatnya tidak relevan untuk persiapan lintas negara.</li>
          <li>Pendekatan interaksi yang mengandalkan humor/sarkasme kurang cocok bagi segmen pengguna profesional yang membutuhkan dasbor analitik berbasis data teknis. </li>
        </ul>
      </td>
    </tr>
    <tr>
      <th colspan="2" style="text-align: left;">Key Competitive Advantage & Unique Value</th>
    </tr>
    <tr>
      <td colspan="2">Otak prediktif MONI difokuskan pada pengamanan milestone jangka panjang dengan variabel multi-mata uang, bukan sekadar penertiban anggaran bulanan lokal.</td>
    </tr>
  </tbody>
</table>

### 6. Metodologi yang Digunakan

**Agile dengan framework Scrum**

**Alasan pemilihan metodologi:**
Kami memilih Scrum karena pengembangan proyek ini akan selalu terdapat pembaruan (update) berkala setiap minggu selama rentang waktu satu semester. Pendekatan ini memungkinkan timeline pengerjaan menjadi lebih terstruktur. Selain itu, kualitas produk akan terus terjaga melalui proses evaluasi dan testing yang dilakukan secara rutin pada akhir setiap _sprint_.

### 7. Perancangan Tahap 1-3 SDLC

**a. Tujuan dari produk**
Membantu pengguna merealisasikan rencana perjalanan ke luar negeri, mulai dari liburan, studi, hingga bekerja, tanpa perlu mengkhawatirkan nilai tukar yang fluktuatif. Dengan fitur penyesuaian target tabungan harian otomatis berbasis kurs real-time, dana yang dibutuhkan selalu aman dan sesuai target.

**b. Pengguna potensial dari produk dan kebutuhan para pengguna tersebut**

- **Mahasiswa calon studi luar negeri:** Berfokus pada pengumpulan dana untuk biaya pendidikan (tuition fee) dan biaya hidup bulanan selama di luar negeri.
- **Masyarakat yang ingin liburan ke luar negeri:** Menabung dalam jangka pendek hingga menengah untuk keperluan rekreasi, seperti tiket pesawat, akomodasi, dan uang saku (pocket money).
- **Calon pekerja yang mempersiapkan dana untuk keberangkatan dan living cost di awal:** Segmen ini membutuhkan kepastian finansial yang solid untuk modal awal keberangkatan.

**c. Use Case Diagram**

_(Gambar Use Case Diagram dilampirkan pada dokumen)_
![Use Case Diagram Aplikasi MONI](images/use-case.webp)

**d. Functional Requirements**

Berikut adalah tabel kebutuhan fungsional (Functional Requirements) untuk use case yang telah dirancang:

| FR                                     | Deskripsi                                                                                                                                   |
| :------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------ |
| **FR 1 Registrasi & Login**            | Sistem harus memungkinkan pengguna mendaftar dengan email/password dan login dengan validasi kredensial.                                    |
| **FR 2 Kelola target keberangkatan**   | Sistem harus memungkinkan pengguna menetapkan negara tujuan (opsional), mata uang tujuan, target tanggal, dan nominal dana yang dibutuhkan. |
| **FR 3 Catat Transaksi Manual**        | Sistem harus memungkinkan pengguna mencatat transaksi pemasukan/pengeluaran secara manual beserta kategorinya.                              |
| **FR 4 Unggah Mutasi Rekening CSV**    | Sistem harus dapat menerima unggahan file CSV mutasi rekening dan mem-parsing datanya menjadi transaksi.                                    |
| **FR 5 Tarik Data Nilai Tukar**        | Sistem harus menjalankan background worker (cron job) yang menarik data kurs dari API finansial publik secara berkala.                      |
| **FR 6 Prediksi Tren Kurs**            | Sistem harus memproses data historis kurs dengan model regresi deret waktu untuk memprediksi tren jangka pendek.                            |
| **FR 7 Kalkulasi Ulang Target Harian** | Sistem harus mengalkulasi ulang target tabungan harian secara otomatis setiap kali terjadi perubahan signifikan pada kurs.                  |

**e. Entity Relationship Diagram (ERD)**

_(Gambar Entity Relationship Diagram dilampirkan pada dokumen)_
![ERD Database MONI](images/erd-moni.webp)

**f. Low-Fidelity Wireframe**

_(Gambar Low-Fidelity Wireframe dilampirkan pada dokumen)_
![Low-Fidelity Wireframe MONI](images/wireframe-lofi.webp)

**g. Gantt Chart**

<table style="border-collapse: collapse; width: 100%; border: 1px solid black; font-family: sans-serif; background-color: white; color: black;">
  <thead>
    <tr>
      <th rowspan="2" style="border: 1px solid black; padding: 8px; text-align: center; background-color: white;">Kegiatan</th>
      <th colspan="12" style="border: 1px solid black; padding: 8px; text-align: center; background-color: white;">Pertemuan</th>
    </tr>
    <tr>
      <th style="border: 1px solid black; padding: 8px; text-align: center; width: 5%;">1</th>
      <th style="border: 1px solid black; padding: 8px; text-align: center; width: 5%;">2</th>
      <th style="border: 1px solid black; padding: 8px; text-align: center; width: 5%;">3</th>
      <th style="border: 1px solid black; padding: 8px; text-align: center; width: 5%;">4</th>
      <th style="border: 1px solid black; padding: 8px; text-align: center; width: 5%;">5</th>
      <th style="border: 1px solid black; padding: 8px; text-align: center; width: 5%;">6</th>
      <th style="border: 1px solid black; padding: 8px; text-align: center; width: 5%;">7</th>
      <th style="border: 1px solid black; padding: 8px; text-align: center; width: 5%;">8</th>
      <th style="border: 1px solid black; padding: 8px; text-align: center; width: 5%;">9</th>
      <th style="border: 1px solid black; padding: 8px; text-align: center; width: 5%;">10</th>
      <th style="border: 1px solid black; padding: 8px; text-align: center; width: 5%;">11</th>
      <th style="border: 1px solid black; padding: 8px; text-align: center; width: 5%;">12</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">Brainstorming</td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">Setup Repositori</td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">Sprint Planning</td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">Use case, FR, ERD</td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">Setup Cloud dan CI/CD</td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">Desain dan Implementasi Database</td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">Auth dan Manajemen Akun</td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">Develop Target Keberangkatan</td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">Catat Transaksi Manual</td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">Unggah dan Parsing Mutasi Rekening CSV</td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">Integrasi API Kurs</td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">Fetch Kurs Berkala</td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">Forecasting</td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">Kalkulasi Sinking Fund</td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">Burn-Down Forecasting Chart</td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">Smart Alert & Rekomendasi Realokasi</td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">Testing & Bug Fixing Over all</td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">Deployment</td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black;"></td>
      <td style="border: 1px solid black; background-color: black;"></td>
    </tr>
  </tbody>
</table>
