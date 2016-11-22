Diandita Wira Puspita
1144028
D4 Teknik Informatika 3C
Politeknik Pos Indonesia


Create Shapefile




Shapefile adalah suatu format yang banyak digunakan untuk menyimpan data geografis vektor. Ini bisa dikembangkan oleh ESRI, perusahaan yang membuat ArcGIS, dalam seperangkat aplikasi SIG.


Cara membuat data geometri shapefile adalah sebagai berikut:
- Buka python di command prompt
- import shapefile
- sf = shapefile.Writer(shapeType=1)
- sf.shapeType -> untuk mengecek
- sf.field('NAMA','C','40')

Cara menampilkan data geometri shapefile adalah sebagai berikut:
- Buka python di command prompt
- import shapefile
- sf = shapefile.Reader('warteg.shp')
- sf.record() -> semua record

Kesimpulan
Shapefile adalah suatu format yang banyak digunakan untuk menyimpan data geografis dan dapat mengukur pada tikik koordinat.

Saran
Menurut saya sebaiknya pembaca lebih memahami lebih mendalam tentang shapefile yang ada pada sistem informasi geografis.

Referensi
Puntodewo, Atie,dkk.2003.Sistem Informasi Geografis untuk Pengelolaan Sumber Daya Alam. Jakarta: Center for International Foresty Research

Scan
https://drive.google.com/open?id=0B17w878LGlWFRzJlSlR2eExmXzg
https://drive.google.com/open?id=0B17w878LGlWFUU5LVGFwdUxRSGM 
