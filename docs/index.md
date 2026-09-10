# Project Senior Project TI

_Modul Praktikum Senior Project TI_  
**Departemen Teknologi Elektro dan Teknologi Informasi, Fakultas Teknik, Universitas Gadjah Mada**

---

## Identitas Kelompok

**Nama Kelompok:** MONITOR

**Anggota Kelompok:**

1. Muhammad Zakiyyuddin Abdul Adhiim - 24/545668/TK/60719
2. Dharu Bintang Mahendratama - 24/535960/TK/59484
3. Razaqi Alkautsar -24/544958/TK/60570

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
      <td colspan="2">Milestonia merespons volatilitas makroekonomi dengan mengubah besaran target secara otonom.
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
          <li>Tidak menyediakan fitur visualisasi lintasan proyeksi (<em>forecasting chart</em>) untuk memantau kelayakan dana terhadap tenggat waktu keberangaktan.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <th colspan="2" style="text-align: left;">Key Competitive Advantage & Unique Value</th>
    </tr>
    <tr>
      <td colspan="2">Milestonia menggabungkan kemampuan pemantauan kurs valas dengan sistem manajemen pengeluaran harian yang proaktif.</td>
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
      <td colspan="2">Otak prediktif Milestonia difokuskan pada pengamanan milestone jangka panjang dengan variabel multi-mata uang, bukan sekadar penertiban anggaran bulanan lokal.
    </tr>
  </tbody>
</table>
