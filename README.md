# Analisis Pola Konsumsi Pengguna Aplikasi A-A-B Testing Untuk Perilaku Konsumen Penjualan Produk
**Pendahuluan <a id='intro'></a>**

   Dalam era di mana teknologi telah menjadi tulang punggung dari berbagai industri, aplikasi mobile telah memainkan peran yang krusial dalam meredefinisi cara konsumen memperoleh dan menikmati produk makanan. Sebagai bagian dari startup yang bergerak dalam industri makanan, pemahaman mendalam tentang perilaku pengguna aplikasi adalah kunci untuk mengembangkan strategi yang efektif dalam menjangkau dan memenuhi kebutuhan pasar yang dinamis. 
   Dalam konteks ini, proyek ini bertujuan untuk menganalisis pola konsumsi pengguna aplikasi startup makanan dengan cermat. Data yang dikumpulkan akan mengungkapkan pola preferensi konsumen, kecenderungan pembelian, serta faktor-faktor yang mempengaruhi keputusan pembelian mereka. Pengetahuan yang dihasilkan dari analisis ini akan menjadi fondasi yang kuat untuk menyesuaikan strategi pemasaran, pengembangan produk, dan peningkatan layanan agar lebih relevan dengan kebutuhan pelanggan.  
   Dengan pemahaman yang lebih mendalam tentang perilaku konsumen, kami berharap dapat memperbaiki pengalaman pengguna, meningkatkan loyalitas pelanggan, dan secara keseluruhan, meningkatkan penjualan produk makanan kami di pasar yang kompetitif ini.
   Evaluasi A/A/B testing, kami akan mengevaluasi hasil A/A/B testing yang dilakukan oleh tim desain dan manajemen produk. Adanya kekhawatiran terkait potensi gangguan terhadap pengguna dengan perubahan font memunculkan keputusan untuk melakukan A/A/B testing. Pengguna kami akan dibagi menjadi dua kelompok kontrol, yang akan diberikan versi font lama, dan satu kelompok uji, yang akan melihat versi font terbaru. Kami memahami pentingnya ketelitian dalam pengujian ini, dan oleh karena itu, hasil yang dapat diterima harus mencerminkan kesamaan antara kedua kelompok kontrol.
   Analisis Funnel Penjualan, kami akan memulai dengan menggali jalur yang ditempuh pengguna dalam mencapai tahap pembelian pada aplikasi kami. Melalui analisis funnel penjualan, kami berencana untuk mengidentifikasi jumlah pengguna yang berhasil mencapai tahap pembelian, sekaligus mengidentifikasi titik-titik dimana pengguna mungkin terhenti atau mengalami hambatan. Dengan pemahaman mendalam mengenai tahap-tahap ini, kami akan dapat mengoptimalkan pengalaman pengguna dan meningkatkan konversi penjualan.
   Kedalaman Analisis, dalam eksplorasi data, kita akan menggunakan dataset yang sama untuk kedua analisis. Ini menggambarkan praktek yang umum di dunia nyata, dimana eksperimen dan analisis sering dilakukan secara bersamaan untuk memberikan gambaran menyeluruh tentang kualitas aplikasi. Dengan membandingkan hasil A/A/B testing dengan data umum, kita berharap mendapatkan wawasan yang lebih mendalam tentang efektivitas perubahan desain terkait font.
   
**Tujuan <a id='destination'></a>**

   Tujuan dari proyek ini adalah untuk mendalami pola konsumsi para pengguna aplikasi di startup makanan dengan teliti. Dalam upaya untuk memperoleh wawasan yang mendalam mengenai preferensi dan kebiasaan pembelian mereka, analisis ini bertujuan untuk mengidentifikasi tren-tren yang mendasari perilaku konsumen. Dengan pemahaman yang lebih baik terhadap preferensi makanan, frekuensi pembelian, serta faktor-faktor lain yang memengaruhi keputusan konsumen, perusahaan dapat mengarahkan strategi pemasaran dan pengembangan produk yang lebih terfokus. Melalui penargetan yang lebih tepat terhadap preferensi konsumen, diharapkan peningkatan penjualan produk dapat tercapai dengan memenuhi kebutuhan pasar dan memberikan pengalaman yang lebih memuaskan bagi para pengguna aplikasi. Analisis ini menjadi landasan untuk meningkatkan interaksi dengan pelanggan, meningkatkan kepuasan pelanggan, serta membentuk strategi berkelanjutan yang mendukung pertumbuhan perusahaan dalam industri makanan yang kompetitif ini.

Project ini bertujuan yaitu :

1. Mendalami Funnel Penjualan, dengan mengidentifikasi jalur pengguna dari pendaftaran hingga pembelian, menentukan jumlah pengguna yang berhasil mencapai tahap pembelian, dan mengidentifikasi dan menganalisis titik-titik hambatan atau penurunan jumlah pengguna di setiap tahap funnel.

2. Optimasi Pengalaman Pengguna, dengan meningkatkan pemahaman terhadap pengalaman pengguna pada setiap tahap, menentukan area-area yang perlu dioptimalkan untuk meningkatkan konversi penjualan, dan mengimplementasikan perbaikan atau perubahan berdasarkan temuan analisis funnel.

3. Evaluasi Hasil A/A/B Testing, mengidentifikasi dan memahami perubahan yang diuji dalam desain font, membandingkan hasil antara kelompok kontrol (font lama) dan kelompok uji (font baru), dan menentukan apakah perbedaan hasil antara kelompok kontrol mencerminkan perubahan desain atau faktor lain yang mungkin memengaruhi.

4. Keputusan Berbasis Data, mengambil keputusan terkait implementasi atau penolakan perubahan font berdasarkan hasil A/A/B testing yang akurat dan meningkatkan kepercayaan dalam keputusan dengan membandingkan hasil A/A/B testing dengan data umum aplikasi.

5. Peningkatan Kualitas dan Daya Tarik Aplikasi, membangun dasar untuk meningkatkan kualitas aplikasi, meningkatkan daya tarik aplikasi bagi pengguna melalui peningkatan pengalaman pengguna dan desain yang dioptimalkan, dan dengan mencapai tujuan-tujuan ini, kita berharap dapat membawa dampak positif terhadap konversi penjualan, kepuasan pengguna, dan keseluruhan kualitas aplikasi yang kita tawarkan di pasar.


Berikut rincian yang akan kita lewati:

**Tahapan yang Dilakukan**

**Langkah 1: Insialisasi**

- Memanggil data library yang dibutuhkan

  -# *List library yang digunakan*
  
     * import pandas as pd
     * import matplotlib.pyplot as plt
     * import seaborn as sns
     * import numpy as np
     * from datetime import datetime, timedelta
     * from scipy import stats
     * from scipy.stats import levene, shapiro, ttest_ind, mannwhitneyu
     
**Langkah 2: Memuat Dataset**

**Analisis data dengan memuat dataset:** 
    
- `/datasets/logs_exp_us.csv`

- MengUbah nama kolom sesuai dengan yang diinginkan.
- Memeriksa nilai yang hilang dan tipe datanya. Perbaiki datanya jika diperlukan.
- Menambahkan kolom tanggal dan waktu, serta satu kolom terpisah untuk tanggal.

**Langkah 3: Pelajari dan Periksa Datanya:**

- Berapa banyak peristiwa yang tercatat dalam log?
- Berapa banyak pengguna yang tercatat dalam log?
- Berapa jumlah rata-rata peristiwa per pengguna?
- Periode waktu mana yang dicakup oleh data? Temukan tanggal maksimum dan minimumnya. Buat sebuah histogram berdasarkan tanggal dan waktu. Bisakah kita memastikan bahwa data yang kita miliki sama lengkapnya untuk seluruh periode? Peristiwa terdahulu bisa saja muncul dalam log beberapa pengguna karena alasan teknis dan ini bisa mengacaukan distribusi data secara keseluruhan. Temukan momen ketika data mulai dirasa lengkap dan abaikan data lama tersebut. Periode mana yang benar-benar diwakili oleh data yang kita miliki?
- Apakah banyaknya kehilangan peristiwa dan pengguna saat menyingkirkan data lama?
- Pastikan kita memiliki pengguna dari ketiga kelompok eksperimen.

**Langkah 4: Pelajari Funnel Peristiwanya:**

- Melihat peristiwa apa saja yang ada dalam log dan berapa banyak frekuensi kemunculannya. Mengurutkan peristiwa tersebut berdasarkan frekuensi.
- Menemukan jumlah pengguna yang melakukan setiap tindakan. Mengurutkan peristiwa berdasarkan jumlah pengguna. Menghitung proporsi pengguna yang melakukan tindakan setidaknya satu kali.
- Dalam hal urutan apa tindakan-tindakan tersebut terjadi? Apakah semuanya merupakan bagian dari satu urutan? kita tidak perlu memperhitungkan semuanya saat menghitung funnel.
- Gunakan funnel peristiwa untuk menemukan persentase pengguna yang terus berlanjut dari satu tahap ke tahap berikutnya. (Misalnya, untuk urutan peristiwa A → B → C, hitung rasio pengguna pada tahap B terhadap jumlah pengguna pada tahap A, serta rasio pengguna pada tahap C terhadap jumlah pengguna pada tahap B).
- Pada tahap mana kita kehilangan banyak pengguna?
- Berapa banyak persentase pengguna yang berhasil menyelesaikan seluruh tahapan yang ada, dari peristiwa pertama hingga pembayaran?

**Langkah 5: Mempelajari Hasil Eksperimen:**

- Berapa banyak pengguna yang ada di setiap kelompok?
- Kita memiliki dua kelompok kontrol dalam A/A testing di mana kita memeriksa mekanisme dan perhitungan kita. Memperhatikan apakah ada perbedaan yang signifikan secara statistik antara sampel 246 dan 247.
- Pilih peristiwa yang paling populer. Pada setiap kelompok kontrol, temukan jumlah pengguna yang melakukan tindakan tersebut. Temukan persentasenya. Periksa apakah perbedaan antar kelompok signifikan secara statistik. Ulangi prosedur ini untuk semua peristiwa lainnya (akan menghemat waktu jika kita bisa menciptakan sebuah fungsi khusus untuk melakukan pengujian ini). Bisakah kita memastikan apakah kelompok-kelompok tersebut sudah dipisah dengan benar?
- Lakukan hal yang sama untuk kelompok pengguna yang diperlihatkan versi font terbaru. Membandingkan hasilnya dengan masing-masing kelompok kontrol untuk setiap peristiwa secara terpisah. Membandingkan hasilnya dengan hasil gabungan untuk kelompok kontrol. Nah, kesimpulan apa yang bisa kita tarik dari eksperimen tersebut?
- Berapa tingkat signifikansi yang kita tetapkan untuk menguji hipotesis statistik yang disebutkan di atas? Menghitung berapa banyak pengujian hipotesis statistik yang telah kita lakukan. Dengan tingkat signifikansi statistik 0,1 - satu dari 10 hasil bisa saja salah. Berapa tingkat signifikansi yang seharusnya ditetapkan? Jika kita ingin mengubahnya, jalankan ulang tahap sebelumnya dan periksa kesimpulanmu.

**Langkah 6: Kesimpulan Umum**
