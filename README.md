# Data simulasi regresi ADG kambing Peranakan Etawah

Repositori ini memuat data sintetis yang digunakan dalam naskah revisi Jurnal Pustaka Data untuk membandingkan pemisahan data per individu dan per kandang pada model prediksi pertambahan bobot harian (ADG). Angka dalam data ini berasal dari simulasi. Data tersebut tidak berasal dari pengukuran di peternakan.

## Data utama

| Berkas | Isi |
| --- | --- |
| [individu.csv](data/individu.csv) | 614 catatan kambing PE jantan pascasapih: 203 Starter, 203 Grower, dan 208 Finisher. |
| [kandang_periode.csv](data/kandang_periode.csv) | 60 pengamatan kandang per periode, masing-masing 20 per fase. Memuat ringkasan pertumbuhan, konsumsi, dan FCR. |
| [pemberian_pakan.csv](data/pemberian_pakan.csv) | 180 catatan bahan pakan, tiga per pengamatan kandang. |
| [komposisi_pakan.csv](data/komposisi_pakan.csv) | Delapan bahan pakan beserta kadar bahan kering, protein kasar, dan TDN. |

Gunakan `Observation_ID` untuk menghubungkan tabel individu, kandang per periode, dan pemberian pakan. Gunakan `ID_Pakan` untuk menghubungkan pemberian pakan dengan komposisinya. CSV memakai UTF-8, pemisah koma, dan titik desimal.

ADG dinyatakan dalam kg/ekor/hari. DMI adalah estimasi konsumsi bahan kering dalam kg/ekor/hari. Protein kasar dan TDN dinyatakan sebagai persentase bahan kering, sedangkan FCR menyatakan kg bahan kering per kg pertambahan bobot. [Acuan pembangkitan](docs/acuan_pembangkitan.md) menjelaskan parameter, rujukan, dan rumus.

## Keluaran evaluasi

| Berkas | Isi |
| --- | --- |
| [uji_pemisahan_adg.csv](hasil/uji_pemisahan_adg.csv) | 432 baris dari 36 pasangan pembagian per fase, dua protokol, dan dua model (M3 dan M4). |
| [simulasi_tambahan_adg.csv](hasil/simulasi_tambahan_adg.csv) | 2.700 pasangan replikasi keluaran M3 berdasarkan tiga fase, tiga nilai korelasi intrakandang (0; 0,25; 0,50), dan 300 replikasi untuk setiap kombinasi. |

Pada simulasi tambahan, `difference` adalah RMSE pemisahan per kandang dikurangi RMSE pemisahan per individu, dalam kg/hari. Pembangkitan ADG tidak memasukkan efek kausal pakan. Hasil digunakan untuk mengevaluasi protokol validasi dan tidak menjadi rekomendasi formulasi pakan.
