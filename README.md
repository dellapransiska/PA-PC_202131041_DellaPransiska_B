NO 4

    Teori yang mendukung mengenai projek terkait
Deteksi marka jalan adalah proses mengidentifikasi dan memetakan marka jalan yang ada pada permukaan jalan. Terdapat beberapa teori dan metode yang digunakan dalam deteksi marka jalan, di antaranya:

1.Deteksi berbasis citra: Metode ini menggunakan teknik pengolahan citra untuk mendeteksi marka jalan. Algoritma pemrosesan citra seperti deteksi tepi, transformasi Hough, dan segmentasi warna digunakan untuk mengenali pola dan bentuk marka jalan. Deteksi berbasis citra dapat dilakukan dengan menggunakan kamera atau sensor yang dipasang pada kendaraan.

2.Deteksi berbasis penginderaan: Metode ini melibatkan penggunaan sensor seperti lidar (Light Detection and Ranging) atau radar untuk mendeteksi marka jalan. Sensor ini mengirimkan sinyal elektromagnetik dan mengukur waktu yang dibutuhkan untuk sinyal tersebut kembali setelah memantul dari marka jalan. Dengan menghitung perubahan waktu pantul, sensor dapat menentukan posisi dan keberadaan marka jalan.

3.Deteksi berbasis pemrosesan data: Metode ini menggunakan data yang dikumpulkan dari kendaraan yang dilengkapi dengan sensor-sensor seperti kamera, lidar, dan radar. Data ini kemudian diproses menggunakan algoritma dan teknik pengolahan data untuk mengenali dan memetakan marka jalan. Metode ini dapat memanfaatkan pendekatan pembelajaran mesin untuk mengklasifikasikan dan memahami data marka jalan.

4.Deteksi berbasis pemetaan: Metode ini melibatkan penggunaan peta digital yang memuat informasi tentang marka jalan. Data dari sensor kendaraan dapat dibandingkan dengan informasi dalam peta untuk menentukan posisi marka jalan. Metode ini bergantung pada keakuratan peta digital yang digunakan dan memerlukan pembaruan secara teratur untuk mencerminkan perubahan marka jalan.

5.Deteksi berbasis pengolahan real-time: Metode ini fokus pada deteksi marka jalan secara real-time dengan menggunakan kombinasi sensor dan pemrosesan data yang cepat. Algoritma deteksi cepat diterapkan untuk mengenali marka jalan dalam waktu nyata dan memberikan umpan balik kepada pengemudi atau sistem pengendalian kendaraan.

Penting untuk dicatat bahwa deteksi marka jalan merupakan bidang penelitian yang terus berkembang, dan terdapat berbagai pendekatan dan kombinasi metode yang digunakan untuk meningkatkan akurasi dan efisiensi deteksi marka jalan.

    Menjelaskan Tahapan Cara Menyelesaikan projek secara detail
1.Mengimpor library yang diperlukan: Kode dimulai dengan mengimpor library yang diperlukan, yaitu cv2 untuk OpenCV, numpy untuk operasi matriks, dan matplotlib.pyplot untuk menampilkan hasil.

2.Memuat gambar: Kode memuat gambar yang ingin dianalisis menggunakan fungsi cv2.imread. Gambar tersebut disimpan dalam variabel image.

3.Konversi ke grayscale: Gambar diubah ke skala abu-abu menggunakan fungsi cv2.cvtColor. Hasilnya disimpan dalam variabel gray.

4.Penerapan Gaussian blur: Untuk mengurangi noise dan memperlancar gambar, diterapkan Gaussian blur menggunakan fungsi cv2.GaussianBlur. Gambar hasil blur disimpan dalam variabel blurred.

5.Deteksi tepi menggunakan Canny edge detector: Fungsi cv2.Canny digunakan untuk mendeteksi tepi dalam gambar yang sudah di-blur. Hasil deteksi tepi disimpan dalam variabel edges.

6.Definisi region of interest (ROI): Dilakukan pengambilan ROI untuk membatasi area yang akan dianalisis. ROI adalah daerah tertentu dalam gambar yang mencakup marka jalan. Daerah ROI ditentukan oleh roi_vertices, yaitu titik-titik pada gambar yang membentuk poligon. Fungsi cv2.fillPoly digunakan untuk membuat mask dengan poligon ROI yang ditentukan. Mask ini digunakan untuk memfilter hasil deteksi tepi agar hanya garis-garis dalam ROI yang diperoleh. Hasilnya disimpan dalam variabel masked_edges.

7.Deteksi garis menggunakan Hough transform: Dengan menggunakan fungsi cv2.HoughLinesP, dilakukan deteksi garis pada gambar yang sudah difilter. Parameter-parameter yang digunakan dalam fungsi ini, seperti threshold, minLineLength, dan maxLineGap, dapat disesuaikan sesuai kebutuhan. Hasil deteksi garis disimpan dalam variabel lines.

8.Menggambar garis pada gambar asli: Setelah deteksi garis selesai, garis-garis yang ditemukan digambar pada gambar asli menggunakan fungsi cv2.line. Hasilnya disimpan dalam variabel line_image.

9.Overlay gambar garis pada gambar asli: Dengan menggunakan fungsi cv2.addWeighted, gambar garis yang sudah digambar di atas gambar asli akan di-overlay. Hasilnya disimpan dalam variabel result.

10.Menampilkan hasil: Hasil akhir ditampilkan menggunakan plt.imshow dari matplotlib dengan menerjemahkan skema warna dari BGR (yang digunakan oleh OpenCV) ke RGB. Pemanggilan plt.axis('off') digunakan untuk menyembunyikan sumbu koordinat pada tampilan. Akhirnya, hasil ditampilkan menggunakan plt.show().

    Tambahkan Jurnal terkait
Markah jalan (tidak baku: marka jalan) secara definisi dapat diartikan sebagai tanda, simbol,garis ataupun tulisan yang digunakan untuk mengatur, menunjang serta memandu ketertiban lalu lintas. Marka jalan terletak pada permukaan jalan raya beraspal. Marka jalan juga digunakan
untuk meningkatkan tingkat keselematan dan kelancaran dalam arus lalu lintas.
Marka garis membujur garis utuh berfungsi sebagai garis pembatas untuk menunjukkan area atau batas posisi yang tepat bagi kendaraan untuk bergerak melintas pada jalan raya bermarka.
Pada garis marka jalan membujur utuh, pengendara dilarang untuk melintasi garis marka tersebut karena termasuk dalam garis marka jalan terlarang. Sedangkan untuk garis marka jalan membujur putus-putus, pengendara diperbolehkan untuk melintasi garis marka tersebut.
