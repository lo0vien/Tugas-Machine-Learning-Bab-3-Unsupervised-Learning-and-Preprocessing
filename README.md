# Analisis Unsupervised Learning

## Overview

Repository ini berisi hasil pembelajaran dan eksperimen **Machine Learning menggunakan Python dan Google Colab** berdasarkan materi *Introduction to Machine Learning with Python*, khususnya Chapter 3 tentang **Unsupervised Learning and Preprocessing**.

Tujuan dari praktikum ini bukan hanya untuk mengetahui cara menjalankan algoritma menggunakan `scikit-learn`, tetapi juga untuk memahami **perbedaan cara kerja model, pengaruh parameter, karakteristik data yang sesuai, serta bagaimana menginterpretasikan hasil eksperimen**.

Buku menempatkan PCA, NMF, t-SNE, k-Means, Agglomerative Clustering, dan DBSCAN dibahas dalam bagian unsupervised learning.

# 1. Analisis Unsupervised Learning

## 1.1 Konsep Dasar

Unsupervised learning memiliki kondisi yang berbeda karena tidak menggunakan target sebagai jawaban yang harus diprediksi.

Dari eksperimen yang dilakukan, saya melihat bahwa unsupervised learning dapat dibagi menjadi dua tujuan besar:

### Dimensionality Reduction / Representation

* PCA
* NMF
* t-SNE

### Clustering

* k-Means
* Agglomerative Clustering
* DBSCAN

Karena tidak terdapat label sebagai jawaban benar, analisis hasilnya juga berbeda dengan supervised learning.

---

# 2. Analisis Setiap Model Unsupervised

## 2.1 PCA

PCA digunakan untuk mengurangi dimensi data dengan mencari representasi baru yang lebih ringkas.

Dari praktik PCA, saya memahami bahwa jumlah fitur yang banyak tidak selalu berarti informasi yang diperoleh lebih mudah dipahami.

PCA membantu menyederhanakan representasi data sehingga hubungan atau pola tertentu dapat lebih mudah diamati.

Namun, hasil PCA berupa komponen baru sehingga interpretasi setiap komponen tidak selalu langsung sama dengan fitur asli.

**Pemahaman dari eksperimen:** reduksi dimensi dapat membantu mengatasi kompleksitas data tanpa harus langsung membuang seluruh informasi dari dataset.

---

## 2.2 NMF

NMF memiliki tujuan yang mirip dengan PCA dalam hal menemukan representasi data yang lebih sederhana, tetapi menggunakan pendekatan yang berbeda.

Hal penting yang saya pahami adalah NMF menghasilkan komponen non-negatif. Karakteristik tersebut membuat NMF menarik ketika representasi berupa bagian-bagian atau kontribusi positif lebih mudah diinterpretasikan.

Dengan demikian, PCA dan NMF sama-sama dapat digunakan untuk mendapatkan representasi baru, tetapi konsep matematis dan karakteristik hasilnya berbeda.

**Pemahaman dari eksperimen:** dua algoritma yang sama-sama melakukan reduksi atau ekstraksi representasi belum tentu memberikan representasi yang sama.

---

## 2.3 t-SNE

t-SNE merupakan algoritma yang lebih diarahkan untuk **visualisasi data berdimensi tinggi**.

Pada eksperimen menggunakan digits dataset, data yang memiliki banyak fitur direpresentasikan menjadi dua dimensi.

Hasil tersebut membantu melihat apakah data tertentu membentuk kelompok yang secara visual terlihat berdekatan.

Namun, saya memahami bahwa t-SNE tidak sama dengan clustering. Jika terlihat beberapa kelompok pada visualisasi t-SNE, hal tersebut tidak otomatis berarti algoritma telah memberikan label cluster.

Buku juga menjelaskan bahwa t-SNE terutama digunakan untuk visualisasi dan tidak menyediakan metode `transform` untuk menerapkan representasi yang sama pada data baru.

**Pemahaman dari eksperimen:** visualisasi dapat membantu memahami struktur data, tetapi visualisasi tidak boleh langsung dianggap sebagai hasil klasifikasi.

---

# 3. Analisis Clustering

## 3.1 k-Means

k-Means mengelompokkan data berdasarkan kedekatan terhadap centroid.

Dari praktiknya, saya memahami bahwa pengguna harus menentukan jumlah cluster terlebih dahulu. Hal ini menjadi salah satu perbedaan penting dibandingkan algoritma seperti DBSCAN.

Kelebihan pendekatan ini adalah konsepnya sederhana dan hasilnya relatif mudah divisualisasikan.

Namun, ketika jumlah cluster yang ditentukan tidak sesuai dengan struktur sebenarnya, hasil pengelompokan juga dapat menjadi kurang representatif.

**Pemahaman dari eksperimen:** k-Means cocok ketika kita mempunyai alasan atau analisis tertentu mengenai jumlah kelompok yang ingin dicari.

---

## 3.2 Agglomerative Clustering

Agglomerative Clustering menggunakan pendekatan hierarchical clustering.

Berbeda dari k-Means yang menggunakan centroid sebagai pusat cluster, Agglomerative Clustering membangun kelompok secara bertahap berdasarkan hubungan antar data.

Dari eksperimen, saya memahami bahwa algoritma ini memberikan sudut pandang yang berbeda terhadap struktur kelompok. Data tidak hanya dipandang sebagai kumpulan titik terhadap pusat cluster, tetapi dapat dipahami sebagai struktur hierarki.

Buku membahas Agglomerative Clustering sebagai hierarchical clustering dan juga membahas pilihan linkage yang memengaruhi proses penggabungan cluster.

**Pemahaman dari eksperimen:** cara mendefinisikan hubungan antar data dapat menghasilkan struktur clustering yang berbeda.

---

## 3.3 DBSCAN

DBSCAN menggunakan konsep **kepadatan data**.

Dari eksperimen, saya memahami bahwa DBSCAN memiliki karakteristik yang berbeda dari k-Means karena dapat mengidentifikasi data yang berada di area dengan kepadatan rendah sebagai noise.

Hal tersebut berguna ketika dataset memiliki bentuk cluster yang tidak sederhana.

Namun, hasil DBSCAN sangat dipengaruhi oleh parameter seperti `eps` dan `min_samples`. Oleh karena itu, parameter tersebut perlu disesuaikan dengan karakteristik dataset.

**Pemahaman dari eksperimen:** clustering tidak selalu harus berdasarkan centroid. Kepadatan data juga dapat digunakan untuk menentukan struktur kelompok.

---

# 4. Perbandingan Unsupervised Learning

| Algoritma     | Pendekatan                | Hal yang Dipelajari                            |
| ------------- | ------------------------- | ---------------------------------------------- |
| PCA           | Reduksi dimensi           | Mencari representasi data yang lebih sederhana |
| NMF           | Representasi fitur        | Membentuk komponen non-negatif                 |
| t-SNE         | Manifold learning         | Memvisualisasikan struktur lokal data          |
| k-Means       | Centroid-based clustering | Mengelompokkan berdasarkan kedekatan centroid  |
| Agglomerative | Hierarchical clustering   | Membangun cluster secara bertahap              |
| DBSCAN        | Density-based clustering  | Mencari kelompok berdasarkan kepadatan         |

Buku sendiri mengelompokkan k-Means, Agglomerative Clustering, dan DBSCAN sebagai metode clustering, sedangkan t-SNE berada pada bagian manifold learning dan PCA/NMF pada dimensionality reduction serta feature extraction.

# 5. Kesimpulan

Eksperimen terhadap 13 algoritma memberikan gambaran bahwa Machine Learning memiliki berbagai pendekatan untuk menyelesaikan permasalahan yang berbeda.

**Supervised Learning** lebih terarah karena model belajar menggunakan target. Dari tujuh model yang dicoba, saya melihat perbedaan pendekatan mulai dari model sederhana seperti Linear Models dan KNN sampai model yang lebih kompleks seperti Random Forest, SVM, dan Neural Networks.

**Unsupervised Learning** memiliki tantangan yang berbeda karena tidak terdapat target sebagai jawaban. PCA, NMF, dan t-SNE membantu memahami representasi atau struktur data, sedangkan k-Means, Agglomerative Clustering, dan DBSCAN mencoba menemukan kelompok dalam data dengan pendekatan yang berbeda.

Secara keseluruhan, hasil praktikum membuat saya memahami bahwa **Machine Learning bukan tentang mencari algoritma yang paling kompleks, tetapi tentang memilih pendekatan yang sesuai dengan data dan tujuan permasalahan**.

Sebagai mahasiswa semester 5 yang sedang mempelajari Machine Learning, pemahaman ini menjadi dasar penting sebelum masuk ke tahap yang lebih lanjut seperti **feature engineering, model evaluation, hyperparameter tuning, pipeline, dan penerapan model pada dataset nyata**.

# Referensi

Müller, A. C., & Guido, S. (2017). *Introduction to Machine Learning with Python: A Guide for Data Scientists*. O'Reilly Media.

Materi eksperimen menggunakan Python, Google Colab, dan `scikit-learn`.

