# Wine-Quality

# Konteks
Dalam industri minuman, khususnya produksi anggur (wine), menjaga kualitas produk merupakan faktor kunci untuk mempertahankan reputasi dan daya saing. Kualitas wine dipengaruhi oleh berbagai faktor kimia dan fisik yang timbul selama proses fermentasi dan penyimpanan, seperti kadar asam, gula, alkohol, dan sulfur dioksida. Untuk membantu pengambilan keputusan dalam pengendalian mutu, perusahaan perlu memiliki model prediksi yang mampu menentukan tingkat kualitas wine berdasarkan karakteristik kimiawinya.

# Pernyataan Masalah
Produsen wine sering kali menghadapi tantangan dalam memastikan bahwa produk mereka memiliki kualitas yang konsisten. Kualitas yang menurun dapat berdampak negatif terhadap penjualan dan kepuasan pelanggan. Dengan mempertimbangkan berbagai variabel seperti kadar asam tetap (fixed acidity), kadar asam volatil (volatile acidity), kadar alkohol, kandungan gula sisa (residual sugar), serta kadar sulfur dioksida, produsen ingin mengembangkan model yang dapat memprediksi tingkat kualitas wine (quality) secara akurat. Masalah ini penting karena kualitas wine yang buruk akan mempengaruhi persepsi merek dan loyalitas pelanggan. Dengan model prediktif yang andal, perusahaan dapat mengidentifikasi kombinasi karakteristik kimia yang menghasilkan kualitas optimal dan melakukan perbaikan proses produksi secara tepat sasaran.

# Tujuan
Berdasarkan konteks dan permasalahan yang telah dijelaskan, tujuan dari penelitian ini adalah untuk memprediksi tingkat kualitas wine berdasarkan karakteristik kimia yang dimilikinya dengan membandingkan performa tiga metode klasifikasi yaitu, **Support Vector Machine (SVM)**, **XGBoost**, **Random Forest**, sehingga dapat membantu perusahaan menjaga konsistensi mutu produk. Selain itu, penelitian ini juga bertujuan untuk mengetahui variabel-variabel yang paling berpengaruh terhadap penentuan kualitas wine, sehingga perusahaan dapat melakukan pengendalian dan perbaikan proses produksi secara lebih terarah guna menghasilkan produk dengan kualitas yang optimal.

# Dataset
Berikut adalah variabel-variabel yang terdapat dalam dataset.

**- fixed acidity**: Kandungan asam tetap (misal tartaric acid)
**- volatile acidity**: Asam volatil (mempengaruhi aroma dan rasa asam)
**- citric acid**: Menambah kesegaran rasa
**- residual sugar**: Jumlah gula yang tersisa setelah fermentasi
**- chlorides**:	Kandungan garam dalam wine
**- free sulfur dioxide**:	Sulfur bebas untuk mencegah oksidasi
**- total sulfur dioxide**:	Total kandungan sulfur dioksida
**- density**:	Kepadatan cairan (berhubungan dengan kadar gula & alkohol)
**- pH**:	Tingkat keasaman
**- sulphates**:	Berkontribusi pada stabilitas dan rasa
**- alcohol**:	Persentase alkohol dalam wine
**- quality**:	Skor kualitas (target klasifikasi)
**- Id**:	Nomor identifikasi sampel

Data yang digunakan dalam penelitian ini mencakup berbagai variabel yang berkaitan dengan karakteristik fisik dan kimia dari wine. Setiap baris dalam dataset merepresentasikan satu sampel wine, sementara setiap kolom menunjukkan atribut atau fitur tertentu seperti kadar alkohol, keasaman, gula residual, pH, kadar sulfur, dan lain-lain. Variabel-variabel ini memberikan wawasan penting mengenai faktor-faktor yang memengaruhi kualitas wine. Dengan memahami pola hubungan antarvariabel tersebut, dapat dikembangkan model prediksi yang mampu mengklasifikasikan tingkat kualitas wine secara akurat, sehingga membantu perusahaan dalam mengontrol mutu dan meningkatkan standar produksinya.

**hasil** Classification Report SVM:
                precision    recall  f1-score   support

           3       1.00      1.00      1.00        77
           4       0.91      1.00      0.95        71
           5       0.71      0.69      0.70        80
           6       0.62      0.55      0.59        74
           7       0.88      0.89      0.88        79
           8       0.95      1.00      0.97        54

    accuracy                           0.85       435
   macro avg       0.84      0.85      0.85       435
weighted avg       0.84      0.85      0.84       435
Macro avg: Precision = 0.84 | Recall = 0.85 | F1-score = 0.85
Weighted avg: Precision = 0.84 | Recall = 0.85 | F1-score = 0.84

Precision: Dari seluruh sampel yang diprediksi oleh model sebagai kelas kualitas tertentu, sekitar 84% di antaranya benar sesuai dengan label aslinya.
Recall: Model SVM berhasil mengidentifikasi sekitar 85% dari seluruh sampel sesuai dengan kelas kualitas sebenarnya.
F1-score: Nilai 0.85 menunjukkan keseimbangan yang baik antara precision dan recall, menandakan bahwa model tidak hanya akurat dalam prediksi tetapi juga konsisten dalam mengenali berbagai kelas kualitas wine.
Accuracy: Model ini mampu memprediksi dengan benar sekitar 85% dari seluruh data uji. Hal ini menunjukkan bahwa SVM memiliki performa yang stabil dalam mengklasifikasikan tingkat kualitas wine.

**hasil** Classification Report XGBoost:
               precision    recall  f1-score   support

           3       1.00      1.00      1.00        77
           4       0.94      0.92      0.93        71
           5       0.74      0.79      0.76        80
           6       0.74      0.65      0.69        74
           7       0.90      0.94      0.92        79
           8       0.95      1.00      0.97        54

    accuracy                           0.88       435
   macro avg       0.88      0.88      0.88       435
weighted avg       0.87      0.88      0.87       435
Macro avg: Precision = 0.88 | Recall = 0.88 | F1-score = 0.88
Weighted avg: Precision = 0.87 | Recall = 0.88 | F1-score = 0.87

Precision: Dari semua prediksi kualitas wine oleh model, sekitar 88% hasil prediksi sesuai dengan nilai kualitas sebenarnya.
Recall: Model XGBoost mampu mengenali sekitar 88% dari seluruh kelas kualitas wine dengan benar.
F1-score: Dengan nilai 0.88, model menunjukkan keseimbangan yang sangat baik antara precision dan recall, sehingga mampu mengidentifikasi tiap kelas kualitas dengan konsisten.
Accuracy: Model ini memiliki tingkat akurasi sekitar 88%, menjadikannya model dengan performa paling tinggi di antara ketiganya. Ini berarti model XGBoost paling optimal dalam mengenali dan memprediksi tingkat kualitas wine secara keseluruhan.

**hasil** Classification Report Random Forest:
               precision    recall  f1-score   support

           3       1.00      1.00      1.00        77
           4       0.96      0.94      0.95        71
           5       0.71      0.84      0.77        80
           6       0.71      0.59      0.65        74
           7       0.92      0.87      0.90        79
           8       0.96      1.00      0.98        54

    accuracy                           0.87       435
   macro avg       0.88      0.87      0.87       435
weighted avg       0.87      0.87      0.87       435
Macro avg: Precision = 0.88 | Recall = 0.87 | F1-score = 0.87
Weighted avg: Precision = 0.87 | Recall = 0.87 | F1-score = 0.87

Precision: Sekitar 87% dari seluruh prediksi kualitas wine yang dihasilkan model Random Forest sesuai dengan label aslinya.
Recall: Model mampu mengenali 87% dari seluruh kelas kualitas wine yang sebenarnya.
F1-score: Nilai 0.87 menunjukkan keseimbangan yang baik antara precision dan recall, menggambarkan performa yang solid dalam klasifikasi multi-kelas.
Accuracy: Model Random Forest menghasilkan akurasi sebesar 87%, sedikit lebih rendah dari XGBoost namun tetap unggul dalam stabilitas dan generalisasi hasil prediksi pada berbagai kelas kualitas wine.

# Kesimpulan
Model klasifikasi yang digunakan (SVM, XGBoost, dan Random Forest) menunjukkan kinerja yang baik dalam memprediksi kualitas wine berdasarkan karakteristik kimianya.
Model XGBoost memberikan hasil terbaik dengan akurasi sebesar 88%, diikuti oleh Random Forest (87%) dan SVM (85%).
Nilai precision, recall, dan f1-score yang tinggi menunjukkan bahwa model mampu mengenali tingkat kualitas wine dengan cukup akurat.
Dengan demikian, model ini dapat menjadi alat bantu yang efektif bagi produsen wine untuk memprediksi kualitas produk sebelum tahap distribusi, sehingga dapat menjaga konsistensi mutu dan kepuasan pelanggan.

# Recomendation
# Rekomendasi untuk Model:
- Penambahan Data: Performa model dapat ditingkatkan dengan menambahkan lebih banyak data sampel wine agar model mampu belajar lebih baik terhadap variasi karakteristik kualitas.
- Penyetelan Hyperparameter: Dilakukan penyetelan lebih lanjut menggunakan teknik seperti GridSearchCV atau RandomizedSearchCV untuk memperoleh kombinasi parameter paling optimal.
- Feature Engineering: Mengeksplorasi fitur-fitur baru atau kombinasi antarvariabel kimia yang mungkin lebih berpengaruh terhadap kualitas wine.

# Rekomendasi untuk Perusahaan:
- Implementasi Model: Model terbaik, yaitu XGBoost, dapat diterapkan untuk memprediksi kualitas wine secara otomatis sebelum proses distribusi.
- Pemantauan Berkala: Performa model perlu dievaluasi secara rutin agar tetap akurat terhadap perubahan data produksi.
- Peningkatan Kualitas Produksi: Hasil model dapat digunakan untuk mengidentifikasi faktor yang paling memengaruhi kualitas wine, sehingga perusahaan dapat fokus pada pengendalian variabel tersebut untuk menjaga mutu produk.
