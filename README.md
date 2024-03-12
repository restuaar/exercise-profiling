# Tutorial for Advance Programming Course 2023/2024

**Nama** : **Restu Ahmad Ar Ridho** <br/>
**NPM** : **2206028951** <br/>
**Kelas** : **Advance Programming - A**

## Module 5 - Java Profiling

#### Result of JMeter Test Plans using GUI

1. **HTTP Request for `/all-student`**
<p align="center">
  <img src="src\main\resources\static\images\jmeter1-gui.jpg" />
</p>

2. **HTTP Request for `/all-student-name`**
<p align="center">
  <img src="src\main\resources\static\images\jmeter2-gui.jpg" />
</p>

3. **HTTP Request for `/highest-gpa`**
<p align="center">
  <img src="src\main\resources\static\images\jmeter3-gui.jpg" />
</p>

#### Result of JMeter Test Plans using CLI

1. **HTTP Request for `/all-student`**
<p align="center">
  <img src="src\main\resources\static\images\jmeter1-cli.jpg" />
</p>

2. **HTTP Request for `/all-student-name`**
<p align="center">
  <img src="src\main\resources\static\images\jmeter2-cli.jpg" />
</p>

3. **HTTP Request for `/highest-gpa`**
<p align="center">
  <img src="src\main\resources\static\images\jmeter3-cli.jpg" />
</p>

#### Profiling & Performance Optimization

Setelah menyelesaikan proses pengoptimalan performa dan melakukan uji performa menggunakan JMeter, peningkatan berikut ini dapat diamati:

- Terdapat penurunan _execution time_ saat mengakses endpoint `/all-student` dari rata-rata 3,465ms menjadi 635ms pada Profiling Intellij dan dari rata-rata 63200ms menjadi 3200ms pada JMeter.
- Terdapat penurunan _execution time_ saat mengakses endpoint `/all-student-name` dari rata-rata 806ms menjadi 120ms pada Profiling Intellij dan dari rata-rata 1300ms menjadi 120ms pada JMeter.
- Terdapat penurunan _execution time_ saat mengakses endpoint `/highest-gpa` dari rata-rata 144ms menjadi 108ms pada Profiling Intellij dan dari rata-rata 78ms menjadi 60ms pada JMeter.

Proses optimasi menghasilkan peningkatan yang signifikan dalam waktu eksekusi endpoint yang diuji. Baik Profiling di IntelliJ maupun dengan JMeter telah menunjukkan pengurangan waktu eksekusi yang signifikan, sehingga menghasilkan waktu respons yang lebih cepat untuk masing-masing endpoint.

1. **HTTP Request for `/all-student`**

- **Before Optimization**
  <p align="center">
    <img src="src\main\resources\static\images\before-profiling-1.jpg" />
  </p>

- **After Optimization**
  - Profiling
    <p align="center">
      <img src="src\main\resources\static\images\after-profiling-1.jpg" />
    </p>
  - JMeter
    <p align="center">
      <img src="src\main\resources\static\images\after-jmeter-1.jpg" />
    </p>

2. **HTTP Request for `/all-student-name`**

- **Before Optimization**
  <p align="center">
    <img src="src\main\resources\static\images\before-profiling-2.jpg" />
  </p>

- **After Optimization**
  - Profiling
    <p align="center">
      <img src="src\main\resources\static\images\after-profiling-2.jpg" />
    </p>
  - JMeter
    <p align="center">
      <img src="src\main\resources\static\images\after-jmeter-2.jpg" />
    </p>

3. **HTTP Request for `/highest-gpa`**

- **Before Optimization**
  <p align="center">
    <img src="src\main\resources\static\images\before-profiling-3.jpg" />
  </p>

- **After Optimization**
  - Profiling
    <p align="center">
      <img src="src\main\resources\static\images\after-profiling-3.jpg" />
    </p>
  - JMeter
    <p align="center">
      <img src="src\main\resources\static\images\after-jmeter-3.jpg" />
    </p>

#### Reflection

1. What is the difference between the approach of performance testing with JMeter and profiling with IntelliJ Profiler in the context of optimizing application performance?  
   Jawab: Pengujian kinerja menggunakan JMeter melibatkan simulasi perilaku pengguna untuk mengukur respons aplikasi seperti fokus pada waktu respons, _throughput_, dan penggunaan sumber daya. Ini membantu mengidentifikasi titik-titik lemah untuk perbaikan. Namun, pendekatan ini hanya memperhatikan respons tanpa memperhatikan detail cara kerja aplikasi. Di sisi lain, profiling dengan IntelliJ Profiler menganalisis perilaku aplikasi secara detail, memungkinkan kita untuk mengetahui bagian program mana yang memakan waktu lebih lama dan memahami kinerja aplikasi secara lebih rinci dengan pola penggunaan memori dan waktu cpu bekerja. Dengan informasi yang diperoleh dari profiling, kita dapat mengoptimalkan bagian-bagian kode yang mempengaruhi kinerja aplikasi secara signifikan.

2. How does the profiling process help you in identifying and understanding the weak points in your application?  
   Jawab: Proses profiling membantu dalam mengidentifikasi dan memahami alur kode dalam aplikasi dengan memonitor perilaku runtime, termasuk penggunaan CPU, alokasi memori, pemanggilan metode, dan aktivitas thread. Melalui analisis data ini, kita dapat menunjukkan ketidakefisienan, _bottlenecks_, atau konsumsi sumber daya yang berlebihan. Alat-alat profiling menawarkan representasi visual dari alur runtime aplikasi, memfasilitasi identifikasi jalur kode yang bermasalah dan memungkinkan pengoptimalan yang ditargetkan.

3. Do you think IntelliJ Profiler is effective in assisting you to analyze and identify bottlenecks in your application code?  
   Jawab: Ya, IntelliJ Profiler bisa sangat efektif dalam membantu pengembang untuk menganalisis dan mengidentifikasi kemacetan dalam kode aplikasi mereka. Contohnya dalam tutorial & _exercise_ pada module 5 ini, dimana kita bisa mengetahui bahwa ada beberapa method yang kinerjanya lebih lambat. Dengan mengetahui baris mana yang menjadi _bottlenecks_ karena profiling dapat menampilkan durasi baris, sehingga dapat dengan mudah mengidentifikasi bagian program yang menjadi penghambat.

4. What are the main challenges you face when conducting performance testing and profiling, and how do you overcome these challenges?  
   Jawab: Ada beberapa tantangan utama dalam melakukan pengujian _performance testing and profiling_, salah satunya adalah membaca hasil _output_ dan pembandingan dengan _output_ sebelumnya. Pada _profiling_ terdapat banyak hal berjalan sehingga kita harus mencari dengan baik dan teliti. Kita juga kita harus melakukan rekamanan _output_ sebelumnya seperti melakukan _screenshot_ atauun balik ke Profiling sebelumnya. Namun yang saya harapkan adalah _side to side_ perbandingan dari sesudah dan sebelum optimizing. Sehingga untuk mengatasi itu semua adalah membiasakan diri untuk menggunakannya dan juga teliti untuk mendapatkan hal yang kita mau.

5. What are the main benefits you gain from using IntelliJ Profiler for profiling your application code?  
   Jawab: Dengan penggunaan IntelliJ Profiler kita tidak perlu untuk menggunakan _third-party application_ dan juga profiling sudah terintegrasi dengan keseluruhan IDE yang membuat kita lebih mudah lagi melihat bagian kode mana yang menjadi _bottlenecks_.

6. How do you handle situations where the results from profiling with IntelliJ Profiler are not entirely consistent with findings from performance testing using JMeter?  
   Jawab: Dalam penggunaan sebelumnya saya belum menemukan inkonsisten dari hal tersebut. Namun, ketika menemui perbedaan hasil antara profiling dengan IntelliJ Profiler dan pengujian kinerja menggunakan JMeter, langkah pertama adalah memeriksa kembali metode pengujian dan skenario yang digunakan dalam kedua alat tersebut. Selain itu, bandingkan metrik yang diukur oleh kedua alat untuk mengidentifikasi perbedaan fokus atau ruang lingkup seperti HW/SW yang kita gunakan.

7. What strategies do you implement in optimizing application code after analyzing results from performance testing and profiling? How do you ensure the changes you make do not affect the application's functionality?  
   Jawab: Setelah menganalisis hasil dari pengujian kinerja dan pembuatan profil, beberapa strategi dapat diterapkan untuk mengoptimalkan kode aplikasi. Langkah yang saya lakukan adalah memeriksa durasi program menggunakan JMeter. Jika saya menemukan bahwa waktu eksekusi terlalu lama, saya akan mengidentifikasi bagian kode yang menyebabkan masalah tersebut dan mengoptimalkannya. Dengan selalu memastikan bahwa perubahan yang saya lakukan tidak memengaruhi fungsionalitas aplikasi yaitu dengan cara membandingkan output sebelum dan sesudah perubahan.
