# HR_Analytics_Classification : Project Overview
- Membangun model untuk membantu tim HR dalam mengatasi atrisi karyawan.  
- Dataset diperoleh dari [link berikut](https://drive.google.com/file/d/13-AECvVpxOygbZqlAcMqsVxu2smyTxLe/view).  
- Meng-handle nilai baris yang kosong dengan menggunakan **mode()** untuk fitur kategorik ordinal dan **median()** untuk fitur numerik.  
- Melakukan feature engineering untuk mengoptimalkan proses pembelajaran model.
- Membagi dataset menjadi 30% data *test* dan 70% data *train*.
- Meng-handle class imbalance dengan menggunakan metode SMOTE pada data *train*.  
- Melatih model pada data *train* dengan 6 algoritma berbeda dan memilih 2 terbaik untuk proses *hyperparameter tuning* selanjutnya.  
- Memvalidasi model menggunakan data *test*.
  
## **Problem**
Tingginya atrisi karyawan berdampak signifikan bagi perusahaan, seperti meningkatnya biaya rekrutmen, terganggunya proyek, serta turunnya produktivitas dan kinerja tim. Oleh karena itu, penting bagi perusahaan untuk memahami dan memprediksi faktor-faktor yang mempengaruhi atrisi, seperti usia, departemen, jarak rumah, status pernikahan, jam kerja, kepuasan kerja, keseimbangan hidup, riwayat pekerjaan, dan tingkat gaji. Hal ini membantu perusahaan mengambil langkah proaktif untuk mempertahankan karyawan berharga.

## **Goals**
Menganalisis berbagai faktor yang berkontribusi terhadap keputusan karyawan untuk meninggalkan perusahaan serta membangun model prediktif yang mampu memperkirakan kemungkinan seorang karyawan akan keluar dari perusahaan.

## **Insight Awal dari Data**
- Berdasarkan korelasi antara Age dan TotalWorkingYears dengan Attrition, terlihat bahwa karyawan yang lebih tua dan memiliki pengalaman kerja yang lebih panjang cenderung lebih loyal dan jarang meninggalkan perusahaan.
- Dari distribusi variabel EnvironmentSatisfaction dan WorkLifeBalance, terlihat bahwa karyawan dengan kepuasan lingkungan kerja dan keseimbangan hidup-kerja yang tinggi cenderung memiliki angka attrition yang lebih rendah.
- Variabel PercentSalaryHike menunjukkan sedikit korelasi positif dengan tingkat attrition, yang mungkin menunjukkan bahwa karyawan yang menerima kenaikan gaji yang rendah lebih mungkin untuk meninggalkan perusahaan.
- Variabel YearsSinceLastPromotion menjelaskan promosi terakhir yang didapat oleh karyawan. Variabel ini berkorelasi positif dengan variabel TotalWorkingYears, YearsAtCompany, dan YearsWithCurrManager. Loyalitas karyawan tidak terlalu diapresiasi oleh perusahaan.

## **Machine Learning Modeling**
Sebelum melatih model, dataset dibagi menjadi data *train* dan data *test* dengan ukuran masing-masing 70% dan 20%. Model dilatih menggunakan 6 algoritma berbeda dan dievaluasi dengan **F1-Score**.  
- Alasan penggunaan F1-Score adalah untuk mengurangi **False Positive** dan **False Negative**, sehingga proses penyaringan lebih akurat. Dengan demikian, tim HR dapat meminimalkan prediksi yang salah, seperti **tingginya tingkat turnover** akibat karyawan yang berisiko keluar tetapi tidak terdeteksi (*false negative*), atau alokasi sumber daya yang tidak efisien karena karyawan yang sebenarnya tidak berisiko justru teridentifikasi sebagai berisiko keluar (*false positive*). 
- Model dilatih menggunakan:  
  - **Logistic Regression**
  - **Support Vector Classifier**
  - **Decision Tree**  
  - **Random Forest**
  - **XGBoost**
  - **AdaBoost**

## **Evaluasi Model**
Model dievaluasi menggunakan **F1-Score**. Dipilih 2 model dengan F1-Score tertinggi untuk proses *hyperparameter tuning* selanjutnya.
| Model  | F1-Score |
|-------|------|
|XGBoost|98%|
|Random Forest|96%|

## **Rekomendasi**
- Melakukan survei rutin untuk mengukur kepuasan kerja.
- Membuat jalur karir yang jelas dan transparan.
- Meningkatkan fasilitas kerja, seperti ruang kerja ergonomis, akses hiburan, dan lingkungan yang nyaman.
