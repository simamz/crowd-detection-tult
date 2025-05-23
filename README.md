# 👥 Crowd Detection TULT

## 1. Penjelasan

Crowd Detection TULT adalah sistem yang dirancang untuk **mendeteksi dan menghitung jumlah orang** dalam zona tertentu pada sebuah video menggunakan model pretrained **YOLOv5**. Sistem ini bertujuan untuk memberikan **analisis keramaian berdasarkan waktu** sehingga dapat digunakan untuk pemantauan kepadatan, keamanan, atau efisiensi ruang.

## 2. Proses Pengerjaan

### a. 📌 Mencari Dataset
- Durasi video ±10 detik dengan resolusi standar (720p) sebagai bahan uji coba awal.

### b. ⚙️ Instalasi YOLOv5 dan Library

### c. 📌 Pengambilan Koordinat Zona
- Zona yang dianalisis (misalnya area kursi hijau) ditentukan menggunakan cv2.imshow() dan dicatat secara manual sebagai array titik koordinat.

### d. 🔍 Deteksi dan Tracking Keramaian
- Sistem membaca frame dari video
- Mendeteksi objek 'person' menggunakan YOLOv5
- Menghitung jumlah objek dalam zona
- Menyimpan data jumlah orang per frame ke dalam file crowd_log.csv

### e. 📊 Analisis Line Chart
- File CSV hasil logging kemudian diolah:
- Mengelompokkan berdasarkan detik
- Menghitung rata-rata jumlah orang per detik
Menampilkan line chart tren keramaian dari detik ke detik

![hasil](https://github.com/user-attachments/assets/f709cceb-1e21-4553-a1fa-b2bff87cfcb9)

### Crowd Detection
Berdasarkan hasil analisis terhadap rata-rata jumlah orang yang terdeteksi di zona istirahat per detik menggunakan model YOLOv5 pretrained, dapat disimpulkan beberapa hal:

1. Fluktuasi Jumlah Orang
Grafik menunjukkan adanya fluktuasi jumlah orang dari waktu ke waktu, dengan nilai rata-rata yang bervariasi antara detik ke-0 hingga detik ke-10. Ini menunjukkan adanya pergerakan atau dinamika kerumunan yang aktif di area pengamatan.

2. Rata-Rata Jumlah Orang Stabil
Rata-rata jumlah orang per detik selama durasi pengamatan adalah 4.8 orang. Ini menunjukkan bahwa dalam kondisi normal, area kursi istirahat memiliki tingkat okupansi menengah.

3. Deteksi Konsisten
Deteksi objek oleh YOLOv5 menunjukkan konsistensi yang cukup baik dengan fluktuasi yang wajar, tanpa anomali ekstrem. Hal ini menandakan bahwa model bekerja efektif dalam mendeteksi objek manusia dalam zona yang telah ditentukan.

4. Potensi Implementasi Nyata
Dengan sistem ini, pengelola ruang dapat secara real-time. Sistem ini dapat diterapkan di cctv yang mana dapat melakukan analisis keramaian setiap detik maupun menit. Sistem akan memantau tingkat kepadatan area tertentu dan mengambil keputusan cepat, misalnya untuk mengatur sirkulasi udara, memberi peringatan kepadatan, atau membatasi akses masuk. 
