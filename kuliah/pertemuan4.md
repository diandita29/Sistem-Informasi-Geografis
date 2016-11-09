Diandita Wira Puspita
1144028
D4 Teknik Informatika 3C
Politeknik Pos Indonesia

Retrieve Data Geospasial

Retrieve Data Geospasial adalah suatu cara untuk mengambil data geometri dan Database data geospasial yang merupakan data vektor yaitu salah satu jenis dari data geospasial, karena data vektor berbentuk shape yang bisa digunakan untuk retrive di phithon, shapefile atau SHP.

Shapefile yaitu format data non topologi yang mudah dan sangat sederhana untuk menyimpan data lokasi geometric dan atribut informasi dari sebuah data geografis. SHP mempunyai salah satu file yang terletak didalam shapefile yang menyimpan data dari geometri.

Membaca jumlah Data Geometri
-> import shapefile
-> sf = shapefile.Reader("namafile.shp")
-> sf.shapes()
-> a=sf.shapes()
-> print len(a)

Membaca Data DBF
-> import shapefile
-> sf.records()
-> sf.records(n)


Kesimpulan
            Shapefile yaitu format data non topologi yang mudah dan sangat sederhana untuk menyimpan data geometric dan atribut informasi dari sebuah data geografis. DBF adalah suatu file yang dapat menyimpan file tabular dan menyimpan data atribut.

Saran
            Menurut saya sebaiknya kita harus mempelajari Retrieve Data Geospasial ini lebih dalam lagi agar kita mampu memahami lebih jauh.

Referensi
Prahasta, Eddy. 2009. Sistem Informasi Geografis : Konsep-konsep Dasar (Perspektif Geodesi dan Geomatika). Penerbit Informatika, Bandung.

Scan
https://drive.google.com/open?id=0B17w878LGlWFcm5UeTdBM3RISk0 
https://drive.google.com/open?id=0B17w878LGlWFbHNhOUpWc2M5QkE 
