Diandita Wira Puspita
1144028
D4 Teknik Informatika 3C
Politeknik Pos Indonesia


Create Shapefile



Pembahasan
Shapefile adalah suatu format yang banyak digunakan untuk menyimpan data geografis vektor. Ini bisa dikembangkan oleh ESRI, perusahaan yang membuat ArcGIS, dalam seperangkat aplikasi SIG.

Shapefile sebenarnya kumpulan dari beberapa file yang berbeda. Contohnya, shapefile yang berisi data bangunan mungkin memiliki file dengan ekstensi berikut ini:
- buildings.shp
- buildings.shx
- buildings.dbf
Shape memiliki file-file tambahan yang berisi informasi lainnya.

Shapefile harus ditunjukan untuk mengadakan satu jenis fitur (titik, garis, atau poligon), dan setiap fitur memiliki atribut di dalam tabel. Tidak seperti sistem OpenStreetMap yang setiap objeknya memiliki jumlah tag yang tidak terbatas, atribut fitur ini pada sebuah shapefile harus sesuai dengan shapefile yang mendefinisikan melalui struktur tabel.

Cara menambahkan record pada shapefile:
-> Pada Point = 'a.point(x,y)' atau 'a.point(x,y,0,0)' dengan domain x dan y adalah koordinat.
-> Pada Polyline = 'a.poly(shapefile=3,parts=[[[x1,y1.z1,w1],[x2,y2,z2,w2],[.....]]])'
-> Pada Polygon = 'a.poly(shapefile=5,parts=[[[.......],[........]]])'

Kesimpulan
Shapefile adalah suatu format yang banyak digunakan untuk menyimpan data geografis dan dapat mengukur pada tikik koordinat.

Saran
Menurut saya sebaiknya pembaca lebih memahami lebih mendalam tentang shapefile yang ada pada sistem informasi geografis.

Referensi
Puntodewo, Atie,dkk.2003.Sistem Informasi Geografis untuk Pengelolaan Sumber Daya Alam. Jakarta: Center for International Foresty Research

Scan
https://drive.google.com/open?id=0B17w878LGlWFQUhDLVNCeW5FVnc 
https://drive.google.com/open?id=0B17w878LGlWFODVEVjhTMVZQajg 
