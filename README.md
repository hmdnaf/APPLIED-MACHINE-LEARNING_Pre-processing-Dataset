# Simulasi Pra-pemrosesan Data Pinjaman Online - Tugas II

Nama: HAMDAN AL FATTAH

NIM: 105841108323

Kelas: 5AI-A

Mata Kuliah: APPLIED MACHINE LEARNING


Tahap II (Lanjutan) dari pipeline pra-pemrosesan data untuk dataset Pinjaman Online yang sudah dibersihkan pada Tahap I.
Tujuan utama tahap ini adalah mengoptimalkan fitur input (X) melalui dua strategi paralel (Seleksi Fitur dan Reduksi Dimensi) untuk mempersiapkan data ke dalam empat skenario modelling (Klasifikasi dan Regresi).
Dataset Input: Data yang sudah dibersihkan dan di-scale dari Tahap I.


# Alur Kerja (Pipeline) Tugas II: Optimasi Fitur
Menjalankan strategi pipeline ganda untuk memastikan data dioptimalkan untuk berbagai kebutuhan bisnis:

Strategi Pemisahan Utama
Tahap II dijalankan secara paralel untuk dua tugas dengan target yang berbeda:

Tugas Klasifikasi (Target y: Status Pinjaman): Untuk memprediksi risiko (Gagal Bayar vs. Lunas).
Tugas Regresi (Target y: Jumlah Pinjaman/Suku Bunga): Untuk memprediksi nilai numerik tertentu.

Skenario Optimasi (Feature Selection vs. PCA)
Setiap tugas dijalankan dalam dua skenario optimasi fitur untuk membandingkan hasilnya di tahap modelling:

1. Seleksi Fitur menggunakan LASSO (L1 Regularization)
Tujuan: Memilih sub-set fitur yang paling relevan dengan memaksa koefisien fitur yang tidak penting menjadi nol.
Implementasi: Digunakan LassoCV dan SelectFromModel untuk secara otomatis memilih fitur yang koefisiennya signifikan (melampaui ambang batas median).

2. Reduksi Dimensi menggunakan PCA (Principal Component Analysis)
Tujuan: Mengurangi jumlah fitur sekaligus mempertahankan sebagian besar varians (informasi) data.
Implementasi: PCA diterapkan pada semua fitur numerik. Jumlah komponen utama ditentukan berdasarkan analisis Scree Plot, yang mencari komponen yang menangkap 95% dari total varians.
