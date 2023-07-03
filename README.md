NO 4
 
     Teori yang mendukung mengenai project terkait 
1. Konversi Warna: Pada baris kedua, gambar awal dibaca menggunakan cv2.imread dan kemudian dikonversi dari format BGR (Blue-Green-Red) ke RGB (Red-Green-Blue) menggunakan cv2.cvtColor(image, cv2.COLOR_BGR2RGB). Konversi ini diperlukan agar gambar dapat ditampilkan dengan benar menggunakan Matplotlib.

2. Pengaburan Citra (Image Blurring): Baris ketiga menggunakan cv2.GaussianBlur untuk mengaburkan gambar dengan kernel Gaussian berukuran (5, 5) dan nilai sigma 0. Pengaburan ini membantu mengurangi noise atau derau pada gambar.

3. Konversi Ruang Warna: Baris keempat mengubah gambar yang telah diabur menjadi ruang warna HSV (Hue-Saturation-Value) menggunakan cv2.cvtColor(blurred_frame, cv2.COLOR_BGR2HSV). Konversi ini memungkinkan kita untuk dengan mudah menentukan rentang warna yang kita minati dalam gambar.

4. Thresholding: Pada baris keenam dan ketujuh, thresholding dilakukan dengan menggunakan cv2.inRange(hsv, lower_yellow, upper_yellow). Thresholding ini memungkinkan kita untuk menghasilkan mask atau gambar biner di mana hanya piksel yang berada dalam rentang warna kuning yang akan tetap berwarna putih (255), sedangkan yang lainnya menjadi hitam (0).

5. Deteksi Tepi (Edge Detection): Baris kedelapan menggunakan cv2.Canny untuk mendeteksi tepi dalam mask yang dihasilkan sebelumnya. cv2.Canny menerapkan algoritma Canny untuk mengidentifikasi tepi gambar dengan menghitung gradien intensitas piksel.

6. Transformasi Hough (Hough Transform): Pada baris kesembilan, cv2.HoughLinesP digunakan untuk mendeteksi garis-garis dalam citra yang dihasilkan oleh cv2.Canny. Metode HoughLinesP ini adalah variasi dari Transformasi Hough yang digunakan untuk mendeteksi garis-garis lurus dengan menghitung titik-titik dalam ruang parameter Hough.

7. Visualisasi: Terakhir, gambar asli dan gambar dengan deteksi marka jalan ditampilkan menggunakan Matplotlib pada baris terakhir. Gambar asli ditampilkan dengan memanggil imshow pada ax[0], sementara gambar dengan deteksi marka jalan ditampilkan pada ax[1].

Demikianlah teori-teori yang mendukung codingan di atas, yang meliputi konversi warna, pengaburan citra, konversi ruang warna, thresholding, deteksi tepi, dan transformasi Hough.

     Menjelaskan tahapan cara menyelesaikan projek secara rinci
1. Impor library: Pertama, kita perlu mengimpor library yang diperlukan untuk pemrosesan gambar, seperti cv2 (OpenCV), numpy (Numerical Python), dan matplotlib.pyplot (Matplotlib).

2. Membaca gambar: Gunakan cv2.imread untuk membaca gambar "Garis Parkiran.jpg" dan menyimpannya dalam variabel image.

3. Konversi warna: Untuk memastikan tampilan gambar yang benar saat ditampilkan dengan Matplotlib, konversi warna dari BGR ke RGB menggunakan cv2.cvtColor dan simpan dalam variabel image_asli.

4. Pengaburan citra: Untuk mengurangi noise atau derau pada gambar, gunakan cv2.GaussianBlur untuk mengaburkan gambar dengan kernel Gaussian berukuran (5, 5) dan nilai sigma 0. Hasil pengaburan disimpan dalam variabel blurred_frame.

5. Konversi ruang warna: Lakukan konversi dari BGR ke HSV menggunakan cv2.cvtColor pada blurred_frame dan simpan dalam variabel hsv. Konversi ini memungkinkan kita untuk dengan mudah menentukan rentang warna yang kita minati dalam gambar.

6. Thresholding: Gunakan cv2.inRange untuk membuat mask yang hanya mempertahankan piksel dalam rentang warna kuning yang ditentukan oleh lower_yellow dan upper_yellow. Simpan mask dalam variabel mask.

7. Deteksi tepi: Dengan menggunakan cv2.Canny, lakukan deteksi tepi pada mask dengan nilai threshold bawah 74 dan threshold atas 150. Hasil deteksi tepi disimpan dalam variabel edges.

8. Transformasi Hough: Gunakan cv2.HoughLinesP untuk mendeteksi garis-garis dalam citra tepi edges. Atur parameter sesuai kebutuhan, seperti resolusi spasial dengan nilai 1, resolusi sudut dengan nilai np.pi/180, threshold untuk panjang garis dengan nilai 50, dan maxLineGap untuk jarak maksimum antara piksel garis dengan nilai 50. Hasil deteksi garis disimpan dalam variabel lines.

9. Visualisasi garis: Jika terdapat garis yang terdeteksi, loop melalui setiap garis dalam lines. Ambil titik awal dan akhir dari setiap garis, lalu gunakan cv2.line untuk menggambar garis tersebut pada gambar asli (image) dengan warna hijau (0, 255, 0) dan ketebalan garis 75.

10. Konversi warna untuk tampilan: Terakhir, konversi image dari BGR ke RGB menggunakan cv2.cvtColor dan simpan dalam variabel image_rgb. Ini diperlukan agar gambar yang ditampilkan dengan Matplotlib memiliki tampilan yang benar.

11. Tampilkan gambar: Buat plot dengan dua subplot menggunakan plt.subplots. Pada subplot pertama (ax[0]), tampilkan gambar asli (image_asli) dengan menggunakan ax[0].imshow. Berikan judul 'Gambar Asli' dengan `ax

     Tambahkan Jurnal terkait
Markah jalan (tidak baku: marka jalan) secara definisi dapat diartikan sebagai tanda, simbol,garis ataupun tulisan yang digunakan untuk mengatur, menunjang serta memandu ketertiban lalu lintas. Marka jalan terletak pada permukaan jalan raya beraspal. Marka jalan juga digunakan
untuk meningkatkan tingkat keselematan dan kelancaran dalam arus lalu lintas.
Marka garis membujur garis utuh berfungsi sebagai garis pembatas untuk menunjukkan area atau batas posisi yang tepat bagi kendaraan untuk bergerak melintas pada jalan raya bermarka.
Pada garis marka jalan membujur utuh, pengendara dilarang untuk melintasi garis marka tersebut karena termasuk dalam garis marka jalan terlarang. Sedangkan untuk garis marka jalan membujur putus-putus, pengendara diperbolehkan untuk melintasi garis marka tersebut.