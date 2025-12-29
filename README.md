# Tugas Analisis Statistik: Deskriptif, Korelasi, dan Regresi

## 1. Informasi Penyusun

- **Nama:** `[MELINDA OKTAVIO DINA PATRICIA]`
- **NIM:** `[2515091143]`
- **Program Studi:** `[SISTEM INFORMASI]`
- **Mata Kuliah:** Statistika dan Probabilitas

---

## 2. Deskripsi Proyek

Pada bagian ini, jelaskan secara singkat dataset yang Anda gunakan. Apa saja variabel di dalamnya? Apa tujuan dari analisis yang Anda lakukan?

> Dataset yang digunakan adalah data_startup_saas.csv yang berisi informasi tentang startup berbasis SaaS dan data ini dapat digunakan untuk menganalisis kinerja startup, mengevaluasi efisiensi bisnis serta untuk menganalisis retensi pelanggan. Variabel kunci dalam dataset ini meliputi Pendapatan_Tahunan_Miliar_IDR, Biaya_Akuisisi_Pelanggan_Juta_IDR, Nilai_Pelanggan_Juta_IDR dan Tingkat_Churn_Persen. Tujuan dari proyek ini adalah untuk memahami karakteristik data melalui statistik deskriptif, menguji hubungan antara Pendapatan_Tahunan_Miliar_IDR dan Biaya_Akuisisi_Pelanggan_Juta_IDR melalui analisis korelasi, serta memprediksi Biaya_Akuisisi_Pelanggan_Juta_IDR menggunakan Pendapatan_Tahunan_Miliar_IDR sebagai prediktor melalui analisis regresi.
---

## 3. Struktur Proyek

Proyek ini diorganisir ke dalam beberapa folder:
- `/data`: Berisi dataset mentah yang digunakan untuk analisis.
- `/scripts`: Berisi semua skrip R yang digunakan dalam analisis, diurutkan berdasarkan alur kerja.
- `/results`: Berisi output dari analisis, seperti plot, gambar, atau tabel ringkasan.

---

## 4. Cara Menjalankan Analisis

Untuk mereproduksi hasil analisis ini, ikuti langkah-langkah berikut:
1. Pastikan Anda memiliki R dan RStudio terinstal.
2. Buka proyek R ini di RStudio.
3. Instal paket yang diperlukan dengan menjalankan perintah berikut di konsol R:
   ```R
   # install.packages(c("tidyverse", "corrplot", "knitr"))
   ```
4. Jalankan skrip di dalam folder `/scripts` secara berurutan, mulai dari `01_data_preparation.R` hingga `05_analisis_regresi.R`.

---

## 5. Hasil dan Interpretasi

Di bagian ini, mahasiswa diharapkan untuk menyajikan dan menginterpretasikan hasil dari setiap tahap analisis.

### 5.1. Statistik Deskriptif
- **Ukuran Pemusatan (Mean, Median, Modus):**
  - *Tabel atau ringkasan...*
  - Pada statistik deskriptif, variabel yang saya gunakan adalah variabel Pendapatan_Tahunan_Miliar_IDR dan hasil yang saya peroleh dari statistik desktriptif yaitu:
  1. Mean: 31,8831846153846
  2. Median: 31,305
  3. Modus: 1,87
  - *Interpretasi:* Jelaskan apa arti dari nilai-nilai tersebut terkait dengan data Anda.
  - Berdasarkan statistik deskriptif menggunakan variabel Pendapatan_Tahunan_Miliar_IDR yang telah saya lakukan, diperoleh nilai mean sebesar 31,88 Miliar Rupiah yang berarti rata-rata pendapatan tahunan startup SaaS berada di angka tersebut. Lalu diperoleh nilai median sebesar 31,30 Miliar Rupiah yang menunjukkan bahwa 50% startup memiliki pendapatan dibawah nilai tersebut dan 50% lainnya memiliki pendapatan diatas nilai tersebut. Namun disini saya mendapat nilai Modus sebesar 1,87 Miliar Rupiah yang berarti bahwa tingkat pendapatan yang paling sering ditemui berada pada kategori yang relatif rendah.Hal ini menunjukan bahwa walaupun rata-rata pendapatan startup tergolong cukup tinggi, mayoritas startup dalam dataset masih memiliki pendapatan rendah.Sementara itu, beberapa startup dengan pendapatan yang jauh lebih tinggi ikut mendorong naik nilai rata-rata pendapatan secara keseluruhan.
- **Ukuran Sebaran (Standar Deviasi, Range, Kuartil):**
  - *Tabel atau ringkasan...*
  - Pada ukuran sebaran, variabel yang saya gunakan adalah variabel Pendapatan_Tahunan_Miliar_IDR dan hasil yang saya peroleh dari ukuran sebaran yaitu:
  1. Standar Deviasi : 19,7855620465392
  2. Range : 1 - 66,89 = 65,89
  3. Kuartil : Min.= 1.00, Q1= 14.31, Q2/Median= 31.30, Mean= 31.88, Q3= 49.04, Max.= 66.89
  - *Interpretasi:* Jelaskan seberapa menyebar data Anda berdasarkan nilai-nilai ini.
    Pendapatan tahunan startup SaaS dalam dataset ini menunjukkan variasi yang cukup signifikan antar perusahaan. Besarnya nilai standar deviasi, yaitu 19,79 Miliar Rupiah, yang mengindikasikan bahwa pendapatan masing-masing startup tersebar jauh dari nilai rata-rata. Perbedaan ini semakin terlihat dari rentang pendapatan yang sangat lebar, mulai dari 1,00 miliar rupiah hingga mencapai 66,89 miliar rupiah, yang mencerminkan adanya kesenjangan skala bisnis antar startup. Jika dilihat dari pembagian kuartil, sebagian startup masih berada pada kelompok pendapatan rendah, sementara kelompok lainnya telah mencapai tingkat pendapatan yang jauh lebih tinggi, sehingga distribusi pendapatan dalam dataset ini dapat dikatakan tidak merata dan cenderung menyebar luas.
- **Visualisasi (Histogram/Boxplot):**
  - *Plot*
  - *Interpretasi:* Jelaskan wawasan apa yang Anda dapatkan dari bentuk distribusi data.
  - Berdasarkan gambar histogram Pendapatan_Tahunan_Miliar_IDR, distribusi pendapatan tahunan startup SaaS terlihat menyebar cukup merata di berbagai rentang nilai, tanpa adanya konsentrasi yang sangat dominan pada satu titik tertentu. Garis rata-rata yang berada di sekitar tengah distribusi menunjukkan bahwa nilai mean cukup merepresentasikan pusat data, meskipun tetap terdapat variasi pendapatan yang lebar antar startup. Selain itu, sebaran batang histogram yang relatif seimbang dari pendapatan rendah hingga tinggi mengindikasikan bahwa ekosistem startup dalam dataset ini terdiri dari kombinasi startup skala kecil, menengah, hingga besar. Pola distribusi seperti ini mencerminkan adanya keberagaman tingkat kematangan bisnis, di mana tidak hanya didominasi oleh satu kelompok pendapatan tertentu, tetapi terbagi di berbagai level perkembangan usaha.

### 5.2. Uji Normalitas
- **Hasil Uji Shapiro-Wilk:**
  - *Nilai p-value= 1,497e-14*
  - *Interpretasi:* Apakah data Anda terdistribusi normal berdasarkan hasil uji? Apa implikasinya?
  - Hasil pengujian normalitas menggunakan metode Shapiro–Wilk pada variabel Pendapatan_Tahunan_Miliar_IDR menghasilkan p-value sebesar 1,497 × 10⁻¹⁴, yang nilainya jauh berada di bawah batas signifikansi 0,05. Hal ini mengindikasikan bahwa distribusi data pendapatan tidak terdistribusi normal, sehingga asumsi normalitas tidak terpenuhi dan hipotesis nol dapat ditolak. Oleh karena itu, dalam melakukan analisis lanjutan, penggunaan metode statistik yang bergantung pada asumsi normalitas perlu dipertimbangkan kembali, dengan alternatif seperti penerapan transformasi data atau pemilihan pendekatan non-parametrik agar kesimpulan yang diperoleh tetap akurat dan dapat dipercaya.
- **Plot Q-Q:**
  - *Plot*
  - ![alt text](qqplot_Pendapatan_Tahunan_Miliar_IDR.png)
  - *Interpretasi:* Apakah titik-titik data mengikuti garis lurus? Apa artinya?
  - Berdasarkan Q–Q plot uji normalitas pada variabel Pendapatan_Tahunan_Miliar_IDR , titik-titik data tidak sepenuhnya mengikuti garis lurus acuan, melainkan menunjukkan pola melengkung dan penyimpangan yang cukup jelas, terutama pada bagian ekor distribusi. Penyimpangan ini menandakan bahwa distribusi pendapatan tahunan startup tidak sesuai dengan distribusi normal, karena jika data berdistribusi normal maka titik-titik akan cenderung berada di sekitar garis lurus. Dengan demikian, pola pada Q–Q plot ini memperkuat hasil uji normalitas sebelumnya yang menyatakan bahwa data pendapatan tidak berdistribusi normal dan memiliki karakteristik sebaran yang tidak simetris atau mengandung nilai ekstrem.

### 5.3. Analisis Korelasi
- **Nilai Koefisien Korelasi:**
  - *Nilai r= 0,996*
  - *Interpretasi:* Seberapa kuat dan apa arah hubungan antara dua variabel yang Anda uji? (misalnya, korelasi positif kuat, negatif lemah, atau tidak ada korelasi).
  - Berdasarkan hasil uji korelasi yang telah saya lakukan, menunjukkan adanya hubungan yang sangat kuat dan bersifat positif antara dua variabel yang diuji. Angka ini mendekati nilai maksimum 1, yang berarti bahwa ketika nilai salah satu variabel meningkat, variabel lainnya juga cenderung meningkat secara hampir searah dan konsisten. Dengan tingkat korelasi yang sangat tinggi tersebut, dapat disimpulkan bahwa perubahan pada satu variabel memiliki keterkaitan yang erat dengan perubahan variabel lainnya, sehingga hubungan yang terbentuk bukan bersifat kebetulan, melainkan mencerminkan keterkaitan linear yang sangat kuat.
- **Visualisasi (Scatter Plot):**
  - *Plot*
  - ![alt text](result)
  - *Interpretasi:* Apakah pola pada scatter plot mendukung hasil koefisien korelasi?
  - Berdasarkan scatter plot tersebut, plot menunjukkan hasil koefisien korelasi yang sangat tinggi, karena titik-titik data membentuk tren yang jelas dan bergerak searah mengikuti garis tren linear. Sebagian besar titik tersebar di sekitar garis naik, yang menunjukkan bahwa peningkatan pendapatan tahunan diikuti oleh peningkatan biaya akuisisi pelanggan. Keteraturan pola ini mencerminkan hubungan linear yang kuat dan positif antara kedua variabel, sehingga secara visual memperkuat temuan nilai korelasi r = 0,996 yang menunjukkan adanya keterkaitan yang sangat erat di antara keduanya.

### 5.4. Analisis Regresi
- **Model Regresi:**
  - *Persamaan regresi: Y = b0 + b1*X*
  - *Interpretasi:* Jelaskan arti dari koefisien intercept (b0) dan slope (b1) dalam konteks data Anda.
  - Berdasarkan hasil model regresi yang sudah diperoleh, nilai intercept (b0) sebesar 1,37 menunjukkan perkiraan nilai biaya akuisisi pelanggan ketika pendapatan tahunan startup bernilai nol, yang dapat diartikan sebagai biaya dasar atau biaya minimum yang tetap dikeluarkan startup meskipun belum menghasilkan pendapatan. Sementara itu, nilai slope (b1) sebesar 1,01 menunjukkan bahwa setiap peningkatan pendapatan tahunan sebesar 1 miliar rupiah diperkirakan akan diikuti oleh kenaikan biaya akuisisi pelanggan sebesar 1,01 juta rupiah, sehingga hubungan antara pendapatan dan biaya akuisisi bersifat positif dan hampir sebanding, yang mencerminkan bahwa semakin besar skala pendapatan startup, semakin besar pula investasi yang dikeluarkan untuk memperoleh pelanggan.
- **Evaluasi Model (R-squared):**
  - *Nilai R-squared= 0,991 atau 99,1%*
  - *Interpretasi:* Berapa persen variasi dari variabel dependen yang dapat dijelaskan oleh model regresi Anda?
  - Berdasarkan evaluasi model regresi, Nilai R-squared sebesar 0,991 atau 99,1% menunjukkan bahwa model regresi yang digunakan mampu menjelaskan sekitar 99,1% variasi pada variabel dependen, yaitu Biaya Akuisisi Pelanggan. Hal ini berarti hampir seluruh perubahan biaya akuisisi pelanggan dapat diterangkan oleh variabel independen Pendapatan_Tahunan_Miliar_IDR dalam model tersebut. Dengan tingkat penjelasan yang sangat tinggi ini, model regresi dapat dikatakan memiliki kemampuan prediksi yang sangat baik, sementara sisanya sekitar 0,9% variasi dipengaruhi oleh faktor lain di luar model.
- **Visualisasi (Garis Regresi pada Scatter Plot):**
  - *Plot*
  - *Interpretasi:* Jelaskan bagaimana garis regresi merepresentasikan hubungan antara variabel.
  - Garis regresi pada grafik merepresentasikan hubungan linear yang sangat kuat dan searah antara Pendapatan_Tahunan_Miliar_IDR dan Biaya_Akuisisi_Pelanggan_Juta_IDR, di mana kemiringan garis yang positif menunjukkan bahwa peningkatan pendapatan tahunan diikuti oleh peningkatan biaya akuisisi pelanggan. Posisi garis yang melewati dan mendekati sebagian besar titik data menandakan bahwa model mampu menangkap pola hubungan antar variabel dengan sangat baik, sehingga perubahan pada variabel independen dapat digunakan untuk memprediksi perubahan pada variabel dependen secara akurat. Selain itu, nilai R-squared yang sangat tinggi memperkuat bahwa garis regresi tersebut secara efektif menggambarkan keterkaitan antara kedua variabel dalam dataset ini.

---

## 6. Kesimpulan
Rangkum temuan utama dari analisis Anda dalam beberapa kalimat. Apa wawasan paling penting yang Anda peroleh?

  - Berdasarkan seluruh rangkaian analisis yang telah saya lakukan, dapat saya simpulkan bahwa data pendapatan tahunan startup SaaS dalam dataset ini memiliki tingkat variasi yang tinggi dan tidak terdistribusi normal, yang menunjukkan adanya kesenjangan yang jelas antara startup berskala kecil dan besar. Hasil analisis statistik deskriptif memperlihatkan bahwa meskipun nilai rata-rata pendapatan tergolong cukup tinggi, sebagian besar startup masih berada pada tingkat pendapatan yang relatif rendah, sementara beberapa startup dengan pendapatan sangat tinggi memberikan pengaruh besar terhadap nilai rata-rata. Selain itu, analisis korelasi dan regresi menunjukkan adanya hubungan linear yang sangat kuat dan positif antara pendapatan tahunan dan biaya akuisisi pelanggan, yang menandakan bahwa pertumbuhan pendapatan umumnya diiringi dengan peningkatan biaya untuk memperoleh pelanggan. Wawasan paling penting dari analisis ini adalah bahwa pertumbuhan startup SaaS tidak hanya bergantung pada peningkatan pendapatan semata, tetapi juga menuntut investasi yang semakin besar dalam strategi akuisisi pelanggan, sehingga pengelolaan biaya dan efisiensi pemasaran menjadi faktor kunci dalam keberlanjutan bisnis.


