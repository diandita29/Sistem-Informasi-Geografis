# Diandita Wira Puspita
# 1144028
# D4 Teknik Informatika 3C
# Politeknik Pos Indonesia



# Pembahasan

OpenLayers adalah suatu Library JavaScript untuk menempatkan peta dinamis di halaman web. OpenLayers dapat menampilkan map tiles, data vektor dan marker dari sumber manapun. OpenLayers dikembangkan untuk lebih memanfaatkan semua jenis informasi geografis dan dirilis dibawah lisensi FreeBSD.

# Contoh Source Code

<!DOCTYPE html>

<html>

<head>

<title>Overlay</title>

var map, layerGML;

// data kepadatan penduduk disimpan dalam format associative array

var data = new Array();

data['3401'] = 663;

data['3402'] = 1794;

data['3403'] = 472;

data['3404'] = 1902;

data['3471'] = 11986;

var wilayah = new Array();

wilayah['3401'] = "Kulon Progo";

wilayah['3402'] = "Bantul";

wilayah['3403'] = "Gunung Kidul";

wilayah['3404'] = "Sleman";

wilayah['3471'] = "Kota Yogyakarta";

// array batas bawah kelas (4 kelas)

var batas = [0, 500, 1000, 2000];

// array warna untuk kelas

var warna = ["#EEFFFF", "#6DD5FF", "#19A3FF", "#0048FF"];

function init(){

    map = new OpenLayers.Map('map', {

        controls: [

            new OpenLayers.Control.Navigation(),

            new OpenLayers.Control.PanZoom(),

            new OpenLayers.Control.ScaleLine(),

            new OpenLayers.Control.MousePosition(),

        ]

    });

    var context = {

        getColor: function(feature) {

            // atribut kode di file peta

            var id = feature.attributes.KODE2010;

            // data untuk wilayah dengan kode : id

            var val = data[id];

            // warna default

            var color = "white";

 

            var i = 0;

            while (i < batas.length - 1){

                if (val < batas[i+1]) {

                    color = warna[i];

                    break;

                }

                i++;

            }

            if (val != null && color == "white")

            {

                color = warna[batas.length - 1];

            }

 

            return color;

        },

        getLabel: function(feature) {

            return wilayah[feature.attributes.KODE2010];

        }

    };

 

    var template = {

        strokeColor: "#808080",

        strokeWidth: 1,

        graphicZIndex: 1,

        fillColor: "${getColor}",

        label: "${getLabel}",

        labelAlign: "cm",

    };

 

    var style = new OpenLayers.Style(template, {context: context});

    var myStyles = new OpenLayers.StyleMap(style);

 

    layerGML = new OpenLayers.Layer.GML("GML", "gml/3400000000.gml", {

            isBaseLayer: true,

            styleMap: myStyles

        });

    layerGML.events.on({

        'loadend': onLoadEnd,

    });

 

    map.addLayer(layerGML);

    map.zoomToMaxExtent();

}

function onLoadEnd(){

    var ext = layerGML.getDataExtent();

    map.zoomToExtent(ext, false);

}

</style>

</head>

<body>

Hasilnya :

File tersebut bisa dijalankan dengan Web Server, misal XAMPP, letakkan di folder xampp/htdocs/openlayers, atau dengan cukup meletakkan di direktori openlayers/ dan membuka langsung dengan klik dua kali sehingga tampil di WebBrowser.



# Kesimpulan

Overlay merupakan proses penempatan grafis suatu peta diatas grafis peta lainnya agar menghasilkan gabungan kedua peta yang memiliki informasi atribut dari kedua peta tersebut. Teknik overlay dalam sistem informasi geografis ada 2 yaitu gabungan (union) dan irisan (intersect). 

# Saran

OpenLayers tidak membutuhkan dependecies atau ketergantungan dengan Server, artinya jika suatu saat ada Sumber Peta misalnya Bing Map atau Google Map yang berbayar ditutup, maka kita tidak perlu khawatir, OpenLayers mampu diubah agar mengambil sumber peta dari Map Server (Provider Peta) yang lain.


# Referensi

Aronoff, S. Geographic Information System: A Management Perspective. WDL Publication, Ottawa, Canada.








