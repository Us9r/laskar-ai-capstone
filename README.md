# 🚀 Prediksi & Segmentasi Siswa: Membangun Pendidikan Inklusif dengan Machine Learning 🎓

Selamat datang di repositori proyek *capstone* Laskar AI🌟 saya, sebuah perjalanan dalam menerapkan kekuatan **Machine Learning (ML)** untuk mendorong inovasi dan inklusi dalam ekosistem pendidikan. Proyek ini, yang merupakan bagian dari program Laskar AI, bertujuan untuk memberdayakan guru dan sekolah dengan *insight* data yang dapat ditindaklanjuti, membantu mereka memahami dan merespons kebutuhan siswa secara lebih personal dan efektif.

---

## 🌟 Ikhtisar Proyek

Dalam proyek ini, saya fokus pada dua area inti *Machine Learning* yang krusial untuk pemahaman siswa dan personalisasi pembelajaran:

1.  **Klasifikasi Status Belajar Siswa:** Saya membangun model untuk memprediksi apakah seorang siswa cenderung mencapai skor akhir 'BAIK' atau 'CUKUP'. Ini juga termasuk mengidentifikasi faktor-faktor kunci yang memengaruhi kinerja mereka, sehingga intervensi dapat dilakukan lebih awal dan tepat sasaran.
2.  **Segmentasi Profil Siswa (Clustering):** Saya mengelompokkan siswa berdasarkan pola karakteristik akademik dan non-akademik mereka. Tujuan dari segmentasi ini adalah untuk menemukan struktur alami dalam populasi siswa, memungkinkan para pendidik untuk merancang strategi pengajaran yang lebih disesuaikan dengan kebutuhan setiap kelompok.

Melalui kedua pendekatan ini, saya berupaya menyediakan alat analitis dan prediktif yang tidak hanya akurat tetapi juga memberikan wawasan yang dapat diimplementasikan, mendukung terciptanya lingkungan belajar yang lebih inklusif.

---

## 💡 Peran & Kontribusi Saya

Sebagai anggota tim *capstone*, saya secara khusus bertanggung jawab atas **pemodelan klasifikasi dan *clustering*** dalam proyek ini. Proyek keseluruhan kami mencakup spektrum luas penerapan *Machine Learning* dalam pendidikan, termasuk **sistem rekomendasi**, **prediksi nilai siswa (regresi)**, **klasifikasi**, dan ***clustering***.

Kontribusi saya mencakup seluruh siklus hidup *data science* untuk kasus klasifikasi dan *clustering*, mulai dari eksplorasi data, pra-pemrosesan, pengembangan dan evaluasi model, hingga interpretasi hasil dan perumusan rekomendasi. Saya bangga telah berkontribusi signifikan dalam mengidentifikasi model-model terbaik dan menggali *insight* penting dari data siswa. Lebih lanjut, keberhasilan proyek ini tidak hanya berhenti pada pengolahan data; **anggota tim kami juga mengembangkan aplikasi berbasis web sebagai antarmuka yang mudah diakses**. Ini memastikan bahwa *insight* dan model yang kami bangun dapat langsung dimanfaatkan oleh pengguna awam, mengubah data kompleks menjadi alat yang praktis dan dapat dicoba.

---

## 📊 Detail Kasus Data Science yang Saya Tangani

Berikut adalah ringkasan mendalam tentang proyek klasifikasi dan *clustering* yang saya kerjakan:

### 📈 Proyek Klasifikasi Skor Akhir Siswa

Dalam proyek klasifikasi ini, tujuan saya adalah menciptakan model prediktif yang mampu mengklasifikasikan skor akhir siswa ke dalam kategori `BAIK` atau `CUKUP`. Lebih dari sekadar label, saya berupaya mengidentifikasi **faktor-faktor kunci** yang memengaruhi kinerja siswa, memberikan wawasan yang dapat digunakan untuk strategi dukungan.

Setelah eksplorasi berbagai model, **Random Forest** dan **XGBoost** terbukti menjadi yang paling unggul dalam performa prediktif. Berdasarkan evaluasi pada set pengujian, **XGBoost** berhasil mencapai **Akurasi 0.87** dengan nilai **AUC 0.94**, menunjukkan kemampuan prediktif yang kuat. Sementara itu, **Random Forest** juga sangat kompetitif dengan **Akurasi 0.86** dan nilai **AUC 0.95**, yang sedikit lebih baik dalam kemampuan membedakan antara kedua kelas. Perlu dicatat, meskipun saya menerapkan teknik **SMOTE** untuk mengatasi ketidakseimbangan kelas pada data pelatihan, hal itu tidak menghasilkan peningkatan kinerja yang signifikan pada set pengujian, mengindikasikan robustnya model-model ini terhadap *imbalance* data yang ada.

Melalui analisis pentingnya fitur menggunakan model XGBoost, saya berhasil **mengidentifikasi 15 fitur teratas** yang paling berpengaruh dalam menentukan skor akhir siswa. Lebih jauh, **Analisis SHAP** memberikan penjelasan granular tentang dampak spesifik setiap fitur (misalnya, nilai mata pelajaran tertentu, absensi, atau status orang tua) terhadap probabilitas seorang siswa mendapatkan skor `BAIK` secara individual.

**Kesimpulan & Rekomendasi:**
Model **XGBoost** yang dilatih dengan 15 fitur teratas adalah kandidat yang sangat kuat untuk implementasi. Kombinasi kinerja tinggi dan interpretasi yang baik melalui analisis fitur dan SHAP memberikan wawasan berharga bagi pihak sekolah. Model ini dapat membantu mengidentifikasi siswa yang berisiko, merancang intervensi yang ditargetkan berdasarkan fitur-fitur yang paling berpengaruh, dan memahami faktor-faktor positif yang berkontribusi pada pencapaian skor `BAIK`. Penerapan model ini berpotensi mendukung pengambilan keputusan berbasis data untuk meningkatkan hasil belajar siswa secara signifikan.

### 💻 Analisis Karakteristik Siswa Melalui Clustering 💼

Analisis *clustering* ini bertujuan untuk mengidentifikasi segmen-segmen siswa berdasarkan pola fitur akademik dan non-akademik terpilih. *Dataset* yang digunakan terdiri dari 15 fitur utama, termasuk nilai mata pelajaran, sikap, partisipasi ekstrakurikuler, dan latar belakang sosial ekonomi orang tua, dengan `final_score` sebagai variabel target biner (`BAIK`/`CUKUP`).

Pada tahap *Exploratory Data Analysis* (EDA), saya menemukan bahwa sebagian besar nilai mata pelajaran terkonsentrasi di atas 80, namun `n_agama` dan `n_bjawa` menunjukkan distribusi bimodal, mengindikasikan adanya dua kelompok siswa yang berbeda. Mayoritas siswa (sekitar 88.3%) ternyata tidak mengikuti kegiatan ekstrakurikuler. Saya juga mengidentifikasi korelasi positif kuat antara nilai mata pelajaran dan `n_sikap_A` dengan `final_score`, sementara `extracurricular_tidak` memiliki korelasi negatif lemah. Selain itu, terdapat ketidakseimbangan kelas yang signifikan pada variabel target `final_score` (`BAIK` lebih dominan).

Untuk visualisasi dan *clustering*, saya menggunakan PCA, UMAP, dan t-SNE untuk mereduksi dimensi data. Meskipun percobaan K-Means dengan k=2 (mencoba mereplikasi label `final_score`) menunjukkan kecocokan yang sangat rendah dengan *ground truth* (misalnya, ARI: 0.0166), hal ini kemungkinan besar karena tumpang tindih intrinsik pada label `final_score` itu sendiri.

Fokus pada **eksplorasi murni dengan K-Means (k=4)** pada data yang telah direduksi via PCA (`X_pca`) menghasilkan **Silhouette Score sebesar 0.6964**, menandakan hasil *clustering* yang sangat baik dengan klaster yang kohesif dan terpisah dengan baik. Saya berhasil mengidentifikasi empat segmen siswa yang distinct dan bermakna:

* **Klaster 3 (Siswa Berprestasi Akademik Sangat Tinggi & Berkarakter Optimal):** Kelompok terkecil dengan nilai akademik tertinggi dan "sikap A" yang kuat.

* **Klaster 1 (Siswa Berprestasi Akademik Tinggi & Berkarakter A):** Mirip Klaster 3 namun sedikit kurang ekstrem, juga dengan "sikap A" yang konsisten.

* **Klaster 0 (Siswa Mayoritas Berprestasi Akademik Menengah & Non-Sikap A, Pasif):** Kelompok terbesar, dengan nilai akademik sedang, mayoritas tidak memiliki "sikap A", dan kurang aktif di ekstrakurikuler.

* **Klaster 2 (Siswa Berprestasi Akademik Rendah & Non-Sikap A, Pasif, Latar Belakang Pekerja):** Kelompok dengan nilai akademik terendah, tanpa "sikap A", pasif, dan memiliki proporsi orang tua dengan pendidikan/pekerjaan terbatas. Kelompok ini kemungkinan paling membutuhkan dukungan dan intervensi.

**Kesimpulan & Rekomendasi:**
Meskipun K-Means tidak efektif dalam mereplikasi label `final_score` yang ada, alur eksplorasi murni berhasil mengidentifikasi empat segmen siswa yang distinct dan bermakna secara statistik maupun substantif. Klaster-klaster ini memberikan *insight* berharga yang dapat menjadi dasar untuk:

1.  **Pengembangan Program Bertarget:** Menciptakan program dukungan khusus untuk Klaster 2.

2.  **Pengayaan:** Mengembangkan program pengayaan atau jalur percepatan untuk Klaster 1 dan 3.

3.  **Meningkatkan Partisipasi Ekstrakurikuler:** Mendorong partisipasi di Klaster 0 dan 2.

4.  **Validasi Lanjut:** Melakukan validasi kualitatif dengan ahli pendidikan untuk memastikan relevansi interpretasi ini.

### 📉 Evaluasi Model Klasifikasi MLP (Dihentikan)

Sebagai bagian dari proses eksplorasi model klasifikasi, saya juga mengembangkan dan mengevaluasi model **Multi-Layer Perceptron (MLP)**. Data diproses melalui *encoding* fitur kategorikal dan normalisasi numerik, dengan penerapan **SMOTE** untuk mengatasi ketidakseimbangan kelas.

Namun, evaluasi model MLP pada data uji hanya menunjukkan **akurasi sebesar 0.8**. Akurasi ini, meskipun tidak buruk, dianggap **tidak mencukupi** untuk memenuhi standar performa proyek yang saya inginkan. Oleh karena itu, pengembangan lebih lanjut pada model MLP ini dihentikan, dan fokus dialihkan sepenuhnya pada model-model alternatif seperti XGBoost dan Random Forest yang terbukti memberikan hasil yang lebih unggul. Ini adalah keputusan penting dalam proses *data science* untuk memastikan solusi yang paling efektif diterapkan.

---

## 🛠️ Tools & Libraries yang Saya Gunakan

Dalam proyek ini, saya memanfaatkan berbagai *tools* dan *library* untuk memastikan alur kerja *data science* yang efisien dan efektif:

* **Integrated Development Environment (IDE):**

    * **Jupyter Notebook:** Sangat penting untuk *prototyping* model yang cepat, *Exploratory Data Analysis* (EDA), dan visualisasi interaktif.

* **Platform & Sumber Data:**

    * **Google Colaboratory (Colab):** Memberikan akses gratis ke GPU/TPU untuk mempercepat pelatihan model, terutama untuk arsitektur yang lebih kompleks.

    * **Microsoft Excel:** Digunakan untuk pengeditan dan pembersihan awal data mentah yang diperoleh langsung dari instansi pendidikan.

* **Machine Learning Libraries:**

    * **TensorFlow & Keras:** Digunakan dalam eksplorasi model *Multi-Layer Perceptron* (MLP).

    * **Scikit-learn:** *Library* utama saya untuk *preprocessing* data, implementasi algoritma *clustering* (termasuk K-Means), dan berbagai metrik evaluasi model.

    * **XGBoost & Random Forest:** *Library* vital untuk algoritma *tree-based ensemble* yang terbukti memberikan performa superior dalam tugas klasifikasi.

    * **NumPy & Pandas:** Fondasi untuk komputasi numerik dan manipulasi data yang efisien.

    * **Matplotlib & Seaborn:** Digunakan untuk visualisasi data dan hasil analisis yang komprehensif.

    * **Shap:** Untuk analisis interpretasi model yang mendalam (SHAP values), membantu menjelaskan mengapa model membuat prediksi tertentu.

* **Lain-lain:**

    * **Git & GitHub:** Digunakan untuk manajemen versi kode, memastikan kolaborasi yang efisien dan pelacakan perubahan proyek.

---

## 🚀 Pembelajaran & Dukungan

Proyek ini merupakan pengalaman belajar yang luar biasa dalam siklus *data science* secara menyeluruh, mulai dari pemahaman data hingga interpretasi hasil. Saya sangat terbantu dengan:

* **Bimbingan Mentor:** Dukungan dari mentor dalam memilih dan mengoptimalkan arsitektur model, serta validasi interpretasi hasil *clustering*.

* **Wawasan Domain:** Diskusi dengan ahli pendidikan untuk memastikan hasil analisis selaras dengan praktik pedagogis nyata.

* **Umpan Balik Pengguna (to be discussed):** Kesempatan untuk mendapatkan umpan balik awal dari calon pengguna untuk menyempurnakan solusi.

---

Terima kasih telah menjelajahi proyek *capstone* saya. Saya antusias untuk terus belajar dan berkontribusi dalam bidang *data science* dan aplikasinya di dunia nyata.

---
⊹ ﹏𓊝﹏𓂁﹏⊹ ˖⊹ ﹏𓊝﹏𓂁﹏⊹ ˖⊹ ﹏𓊝﹏𓂁﹏⊹ ˖
