# Petunjuk Pekerjaan Manual - Sistem Deteksi Ujaran Kebencian Bahasa Jawa

**Versi:** 0.1
**Tanggal:** 28 Mei 2025

## 1. Pendahuluan

Dokumen ini bertujuan untuk memberikan panduan terstruktur bagi pekerjaan manual yang esensial dalam proyek "Integrasi Kecerdasan Buatan dan Kearifan Lokal dalam Sistem Deteksi Ujaran Kebencian Bahasa Jawa Menggunakan BERT". Pekerjaan manual ini terutama berkaitan dengan aspek-aspek yang memerlukan interpretasi manusia, pemahaman konteks budaya mendalam, dan penilaian subjektif yang sulit atau belum bisa sepenuhnya diotomatisasi, khususnya dalam pembuatan dan pelabelan dataset.

Kualitas dari pekerjaan manual ini akan berdampak langsung pada kualitas dataset dan, pada akhirnya, performa model machine learning yang akan dikembangkan.

## 2. Panduan Pelabelan Data Ujaran Kebencian Bahasa Jawa

Proses pelabelan data adalah salah satu tahapan manual paling kritis dalam proyek ini. Tujuannya adalah untuk menghasilkan dataset Bahasa Jawa berlabel berkualitas tinggi yang akan digunakan untuk melatih dan mengevaluasi model deteksi ujaran kebencian.

### 2.1. Tujuan Pelabelan

* Menyediakan "ground truth" bagi model machine learning untuk belajar membedakan berbagai kategori ujaran kebencian dan teks netral/bukan ujaran kebencian.
* Memastikan dataset mencerminkan nuansa linguistik dan budaya Bahasa Jawa yang relevan dengan ujaran kebencian.
* Menghasilkan dataset yang dapat digunakan untuk penelitian selanjutnya.

### 2.2. Tim Pelabel

* Proses pelabelan idealnya melibatkan individu yang memiliki pemahaman baik tentang Bahasa Jawa (termasuk dialek dan tingkatan bahasa) dan konteks budayanya.
* Sangat dianjurkan untuk melibatkan atau setidaknya melakukan konsultasi rutin dengan ahli bahasa Jawa dan budayawan Jawa, sebagaimana direncanakan dalam proposal penelitian.

### 2.3. Definisi Kategori Label

Setiap sampel teks akan diklasifikasikan ke dalam salah satu kategori berikut. Konsistensi dalam pemahaman dan penerapan definisi ini sangat penting.

1.  **Bukan Ujaran Kebencian:**
    * Teks yang tidak mengandung unsur hinaan, provokasi, hasutan, ancaman, atau ekspresi negatif yang merendahkan berdasarkan SARA (Suku, Agama, Ras, Antargolongan), gender, orientasi seksual, kondisi fisik, atau atribut pribadi/kelompok lainnya.
    * Termasuk di dalamnya adalah teks netral, positif, kritik membangun (tanpa merendahkan), diskusi, berita, dll.

2.  **Ujaran Kebencian - Ringan:**
    * Teks yang mengandung sindiran halus, ejekan terselubung, atau metafora budaya yang menyiratkan ketidaksukaan atau kerendahan terhadap target, namun tidak secara eksplisit kasar atau mengancam.
    * Mungkin memerlukan pemahaman konteks budaya Jawa untuk mengidentifikasinya.
    * Contoh: Penggunaan pasemon atau peribahasa Jawa yang bertujuan menyindir secara tidak langsung.

3.  **Ujaran Kebencian - Sedang:**
    * Teks yang mengandung hinaan langsung, cercaan, atau penggunaan bahasa kasar (misalnya, dalam konteks ngoko yang tidak pantas) yang jelas ditujukan untuk merendahkan atau melecehkan target.
    * Intensitasnya lebih tinggi dari kategori "Ringan" dan lebih eksplisit.
    * Tidak sampai pada ancaman kekerasan fisik langsung atau diskriminasi sistematis.

4.  **Ujaran Kebencian - Berat:**
    * Teks yang mengandung ancaman kekerasan fisik, hasutan untuk melakukan kekerasan, dehumanisasi, pernyataan yang mendukung diskriminasi sistematis, atau penghinaan ekstrem terkait SARA.
    * Memiliki potensi dampak paling merusak bagi individu atau kelompok target.

### 2.4. Proses Pelabelan (Langkah-langkah Manual)

1.  **Persiapan Pelabelan:**
    * **Pahami Pedoman:** Setiap pelabel harus memahami dengan saksama definisi masing-masing kategori label dan pedoman umum pelabelan ini.
    * **Alat Pelabelan:** Siapkan alat yang akan digunakan. Ini bisa berupa spreadsheet (misalnya, Google Sheets, Excel) dengan kolom untuk teks, label, dan catatan, atau alat anotasi teks khusus jika tersedia.
    * **Akses Data:** Pastikan akses ke dataset teks Bahasa Jawa yang sudah melalui tahap preprocessing awal (pembersihan dari noise seperti URL berlebih, karakter non-tekstual, dll.).

2.  **Analisis Teks dan Konteks:**
    * Baca setiap sampel teks Bahasa Jawa secara menyeluruh.
    * Pertimbangkan konteks linguistik:
        * **Tingkatan Bahasa:** Apakah teks menggunakan Ngoko, Krama Madya, atau Krama Inggil? Penggunaan tingkatan bahasa yang tidak sesuai dapat menjadi indikator.
        * **Dialek:** Jika memungkinkan, identifikasi variasi dialek (misalnya, Jawa Timuran, Jawa Tengahan, Yogyakarta) karena beberapa istilah mungkin memiliki konotasi berbeda.
        * **Metafora & Ungkapan Lokal (Pasemon):** Perhatikan penggunaan metafora, peribahasa, atau ungkapan khas Jawa yang mungkin mengandung makna tersirat terkait ujaran kebencian.
    * Pertimbangkan konteks sosial dan budaya yang lebih luas jika informasi tersebut tersedia atau dapat diinferensikan secara wajar.

3.  **Pemberian Label:**
    * Setelah analisis, tentukan satu kategori label yang paling sesuai untuk sampel teks tersebut.
    * Jika sebuah teks dapat masuk ke lebih dari satu kategori (misalnya, mengandung hinaan langsung dan sindiran), pilih kategori yang paling dominan atau paling berat dampaknya.
    * Masukkan label yang dipilih pada kolom yang sesuai di alat pelabelan.

4.  **Pencatatan (Opsional namun Bermanfaat):**
    * Jika ada keraguan, ambiguitas, atau kasus menarik, buat catatan singkat di kolom catatan. Ini akan berguna untuk diskusi tim dan penyempurnaan pedoman.

5.  **Diskusi dan Konsensus:**
    * Untuk kasus-kasus yang ambigu atau sulit, diskusikan dengan anggota tim pelabel lainnya atau dengan ahli bahasa/budaya Jawa.
    * Tujuannya adalah mencapai konsensus dan memastikan konsistensi pelabelan.

6.  **Verifikasi dan Iterasi (Direkomendasikan):**
    * Setelah sejumlah data dilabeli, sebagian sampel dapat diverifikasi oleh pelabel lain (proses *cross-validation* atau *inter-annotator agreement check*).
    * Hasil verifikasi digunakan untuk mengidentifikasi ketidakkonsistenan dan memperbaiki pemahaman atau pedoman pelabelan jika perlu. Proses pelabelan mungkin bersifat iteratif.

### 2.5. Hal-hal yang Perlu Diperhatikan Saat Pelabelan

* **Objektivitas dan Netralitas:** Upayakan untuk melabeli berdasarkan definisi dan pedoman yang ada, bukan berdasarkan opini atau bias pribadi.
* **Konteks adalah Kunci:** Makna sebuah ujaran sangat bergantung pada konteksnya. Jangan melabeli kata atau frasa secara terisolasi.
* **Konsistensi:** Usahakan untuk menerapkan kriteria pelabelan secara konsisten di seluruh dataset.
* **Fokus pada Maksud (Intent):** Meskipun sulit, cobalah untuk mempertimbangkan maksud di balik ujaran, terutama untuk membedakan kritik dari ujaran kebencian.
* **Dokumentasi Kasus Sulit:** Catat contoh-contoh teks yang sulit dilabeli beserta alasannya. Ini akan membantu dalam diskusi tim dan penyempurnaan pedoman.
* **Keterbatasan Data Awal:** Ingat bahwa dataset awal mungkin belum mencakup semua variasi ujaran kebencian. Tetap terbuka untuk menemukan pola-pola baru.

## 3. Pengumpulan Data Manual Awal (Jika Diperlukan Sebagai Tambahan)

Meskipun sebagian besar proses pengumpulan data direncanakan menggunakan script atau API, mungkin ada kebutuhan untuk pengumpulan data manual awal atau tambahan, terutama untuk:

* Mengidentifikasi sumber-sumber data baru atau spesifik (misalnya, grup komunitas online, forum lokal tertentu berbahasa Jawa).
* Mengumpulkan sampel dari platform yang sulit di-scrape secara otomatis.
* Memahami secara kualitatif jenis-jenis ujaran kebencian yang muncul di berbagai platform.

### 3.1. Langkah-langkah Pengumpulan Data Manual Awal

1.  **Identifikasi Sumber Potensial:**
    * Berdasarkan diskusi tim dan pengetahuan lokal, buat daftar platform online, forum, grup media sosial, atau kolom komentar yang sering menggunakan Bahasa Jawa dan berpotensi mengandung ujaran kebencian.
2.  **Eksplorasi Manual:**
    * Kunjungi sumber-sumber tersebut.
    * Gunakan kata kunci pencarian yang relevan dalam Bahasa Jawa (misalnya, istilah-istilah yang sering muncul dalam konteks perdebatan panas, hinaan, dll.).
3.  **Pengumpulan Sampel:**
    * Jika menemukan teks yang relevan (baik yang jelas ujaran kebencian maupun yang ambigu atau kontekstual), salin (copy-paste) teks tersebut.
    * Simpan dalam sebuah file (misalnya, spreadsheet atau dokumen teks).
    * Sertakan informasi sumber jika memungkinkan (misalnya, URL, nama grup/forum, tanggal akses). Ini penting untuk melacak asal data dan potensi bias.
4.  **Fokus pada Keragaman:**
    * Upayakan untuk mengumpulkan sampel dari berbagai dialek dan tingkatan bahasa Jawa jika memungkinkan.
    * Cari juga contoh teks netral atau positif dari sumber yang sama sebagai data pembanding.
5.  **Etika Pengumpulan Data:**
    * Selalu perhatikan etika dan privasi. Hindari mengumpulkan informasi pribadi yang tidak relevan. Jika data berasal dari sumber tertutup, pastikan memiliki izin yang sesuai atau anonimkan data.

Proses manual ini bersifat komplementer terhadap pengumpulan data otomatis dan bertujuan untuk memperkaya dataset awal dengan sampel-sampel yang mungkin terlewat.