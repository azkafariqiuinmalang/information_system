# Dasar sumber dan pembangkitan dataset

Revisi: 13 Oktober 2026.

## Status dan ruang lingkup

`DATASET FINAL - REVISI LITERATUR.xlsx` berisi data sintetis yang dibangkitkan dengan bantuan AI melalui simulasi terprogram. Angka per individu, catatan pakan, dan episode kandang bukan salinan pengamatan peternakan atau baris mentah jurnal. Literatur dipakai sebagai pembanding bobot, umur, konsumsi bahan kering, pertambahan bobot, dan komposisi bahan pakan. Pilihan populasi, batas fase, distribusi, serta kurva konsumsi merupakan asumsi simulasi yang dinyatakan di bawah ini.

File lama `DATASET FINAL.xlsx` tidak ditimpa karena terkunci aplikasi saat penyimpanan. File revisi di atas merupakan hasil yang dibahas dalam dokumen ini. Script Pertemuan 4 masih mengarah ke nama file lama dan perlu disesuaikan sebelum analisis ulang.

Sumber dipusatkan dalam dokumen ini. Excel memuat data, rumus, definisi singkat dan keterangan sintetis. Tidak ada sitasi bibliografis pada tabel data. File ini menjadi dokumen utama untuk menjawab pertanyaan tentang asal parameter.

Populasi simulasi ditetapkan sebagai kambing Peranakan Etawah (PE) jantan yang sudah disapih. Ada 60 observasi kandang-periode, 180 catatan bahan pakan dan 614 catatan individu, pada Januari–Juni 2026. Individu antarobservasi berbeda, sehingga tiga fase bukan perjalanan kambing yang sama dari Januari hingga Juni. Penanggalan tersebut adalah skenario kalender sintetis; sumber terbit setelah Juni 2026 dipakai sebagai rujukan saat penyusunan, bukan bukti informasi historis pada saat pengamatan.

## Rujukan bobot, umur, konsumsi dan pertumbuhan

| Kode | Sumber dan populasi | Angka yang digunakan sebagai pembanding | Batas penggunaan |
|---|---|---|---|
| R1 | Novita, Sudono, Sutama dan Toharmat (2006), *Produktivitas Kambing Peranakan Etawah yang Diberi Ransum Berbasis Jerami Padi Fermentasi*, Media Peternakan 29(2):96–106 | Anak PE disapih umur 3 bulan: bobot sapih rata-rata 13,63 kg, rentang individu 10,20–17,60 kg. ADG prasapih rata-rata 106 g/hari, rentang 41–151 g/hari. PE jantan umur 12–18 bulan: bobot awal 30,18 ± 8,38 kg | Bobot sapih menjadi pembanding awal masuk dataset. ADG prasapih hanya pembanding, bukan distribusi ADG pascasapih yang diukur langsung. Penelitian jantan adalah uji kecernaan, bukan definisi Finisher |
| R2 | Supriyati dan Haryanto (2011), *Bungkil Inti Sawit Terproteksi Molases sebagai Sumber Protein pada Kambing Peranakan Etawah Jantan Muda*, Balai Penelitian Ternak | Bobot awal 17–18 kg; konsumsi BK menurut perlakuan 599,30; 620,74; 690,19; 740,04 g/ekor/hari. ADG 42,06; 52,78; 61,90; 70,24 g/ekor/hari. Pengamatan 12 minggu setelah adaptasi 2 minggu | Umur tepat tidak tercantum pada abstrak. Keempat angka adalah rata-rata perlakuan, bukan batas minimum/maksimum individu |
| R3 | Muhammad, Kuswati dan Mashudi (2023), *Pengaruh Penambahan Tepung Biji Kurma dengan Level yang Berbeda Terhadap Performa Kambing Peranakan Etawah (PE) Jantan*, JIPHO 5(3):198–204, Tabel 3 | PE jantan poel satu, bobot awal 28,92 ± 2,65 kg. Konsumsi BK kelompok 881,66–978,42 g/ekor/hari dan ADG kelompok 77,00–121,20 g/ekor/hari | Dipakai untuk besaran konsumsi pada kambing lebih berat. Tidak mengubah poel satu menjadi umur hari tertentu; rentang adalah rata-rata perlakuan |
| R4 | FAO (2011), *Rearing young ruminants on milk replacers and starter feeds*, Tabel 3.7, halaman tercetak 24, mengutip Kearl (1982) | Potensi konsumsi BK pada bobot 10 kg: 0,37 kg/hari; 15 kg: 0,50; 20 kg: 0,62; 25 kg: 0,71 | Ini potensi konsumsi pada tabel kebutuhan, bukan hasil pengukuran konsumsi PE. Digunakan untuk mengisi skala konsumsi kambing kecil yang belum tersedia pada R2/R3 |

Tautan sumber:

- R1: https://journal.ipb.ac.id/index.php/mediapeternakan/article/download/871/246
- R2: https://repository.pertanian.go.id/items/d27bb8b6-f5da-4eff-aecb-d4868b56295b
- R3: https://jipho.uho.ac.id/index.php/journal/article/download/829/401/3543 — DOI https://doi.org/10.56625/jipho.v5i3.37280
- R4: https://www.fao.org/4/i2439e/i2439e00.pdf

## Parameter operasional yang dipakai

Angka pada tabel berikut adalah pilihan pembangkitan yang diinformasikan oleh R1–R4. Tidak ada satu penelitian yang menetapkan ketiga batas fase berikut sekaligus. Rentang bobot merupakan batas nilai individu simulasi, bukan minimum biologis universal.

| Fase dalam Excel | Umur awal simulasi | Batas bobot awal individu | Dasar penetapan |
|---|---|---|---|
| Starter | 90–149 hari, sekitar 3 hingga kurang dari 5 bulan | 10,20–16,00 kg | Awal pascasapih, diinformasikan bobot sapih R1 dan skala BK R4 |
| Grower | 150–299 hari, sekitar 5 hingga kurang dari 10 bulan | 16,00–25,00 kg | Rentang pertumbuhan yang meliputi bobot PE muda R2, diperluas sebagai asumsi simulasi |
| Finisher | 300–540 hari, sekitar 10–18 bulan | 25,00–36,00 kg | Populasi lebih berat dengan pembanding R1 dan R3; batas fase adalah asumsi operasional |

Starter di sini secara khusus berarti **awal pascasapih**, bukan keseluruhan fase lahir–3 bulan. Seluruh ternak memiliki `Status_Sapih = Sudah sapih`. Perhitungan tidak memasukkan susu. Fase ditetapkan berdasarkan umur awal; ternak yang mencapai batas fase berikutnya pada akhir bulan tetap diberi label fase awal pada episode tersebut.

## Pola konsumsi yang meningkat dan melandai

Konsumsi ditulis sebagai kg BK/ekor/hari. Besaran pakan segar bergantung kadar air, sehingga angka segar tidak dapat dibandingkan langsung dengan BK. Kurva berikut merupakan interpolasi skenario, bukan hasil estimasi kurva longitudinal dari satu jurnal.

| Bobot rata-rata selama periode (kg/ekor) | Titik acuan konsumsi BK (kg/ekor/hari) | Status |
|---:|---:|---|
| 10 | 0,37 | Acuan potensi konsumsi R4 |
| 15 | 0,50 | Acuan potensi konsumsi R4 |
| 18 | 0,67 | Pilihan mendekati besaran konsumsi R2 |
| 25 | 0,84 | Interpolasi asumsi menuju R3 |
| 29 | 0,93 | Pilihan mendekati besaran konsumsi R3 |
| 36 | 1,00 | Ekstensi asumsi melandai |
| 45 | 1,04 | Ekstensi kurva untuk menjelaskan plateau; dataset ini tidak menghasilkan bobot awal 45 kg |

Bobot untuk interpolasi adalah `(bobot awal rata-rata + bobot akhir rata-rata) / 2`. Konsumsi di antara dua titik dihitung linier. Pengali variasi antarobservasi `1 + N(0; 0,035)` dibatasi pada 0,92–1,08. Dengan demikian jumlah absolut BK meningkat ketika bobot meningkat, sementara kemiringannya menurun pada bobot besar. Data Finisher masih bervariasi; tidak dipaksa sama pada semua baris.

Literatur yang dipakai mendukung skala konsumsi pada populasi yang berbeda, tetapi tidak membuktikan bahwa konsumsi semua kambing pasti stabil pada usia atau fase tertentu. Plateau adalah asumsi skenario. Dataset ini juga tidak melacak perubahan konsumsi kambing yang sama lintas fase.

## Simulasi bobot dan ADG

Pembangkitan menggunakan seed tetap `20261013` dan generator bilangan acak LCG: `state = (1664525 × state + 1013904223) mod 2^32`; nilai uniform adalah `state / 2^32`. Nilai normal diperoleh dengan transformasi Box–Muller. Seed tetap memungkinkan pembangkitan diulang dengan kode yang sama.

Untuk setiap observasi, umur pusat dipilih uniform dalam rentang fase. Umur individu di sekitar pusat memakai simpangan normal 5 hari dan dibatasi rentang fase. Bobot pusat berubah linier dari batas bawah ke batas atas sesuai posisi umur pusat. Bobot individu ditambahkan koreksi umur `0,025 kg/hari` dan variasi normal `SD 0,65 kg`, lalu dibatasi rentang bobot. Hubungan umur–bobot ini merupakan asumsi sederhana dan bukan kurva pertumbuhan PE hasil estimasi.

ADG pusat setiap observasi dibangkitkan dengan parameter berikut:

| Fase | Rata-rata distribusi ADG (kg/hari) | SD pusat | Batas ADG individu (kg/hari) |
|---|---:|---:|---:|
| Starter | 0,075 | 0,016 | 0,041–0,120 |
| Grower | 0,060 | 0,013 | 0,035–0,095 |
| Finisher | 0,085 | 0,017 | 0,045–0,125 |

ADG individu diberi tambahan variasi normal `SD 0,008 kg/hari`. Bobot akhir dihitung `bobot awal + ADG × durasi`, dibulatkan tiga desimal. Besaran Grower diinformasikan R2, Finisher diinformasikan R3, sedangkan Starter memakai asumsi konservatif dengan pembanding R1. Batas dan simpangan baku adalah pilihan simulasi, bukan statistik yang diklaim berasal langsung dari jurnal.

ADG tidak dibangkitkan dari koefisien Protein_CP_pct. Tidak dipilih seed berdasarkan besar korelasi atau signifikansi. Hubungan protein–ADG yang keluar merupakan karakteristik skenario sintetis; hasilnya tidak dapat membuktikan pengaruh biologis protein. Model ini menyederhanakan kecukupan nutrisi dan bukan model mekanistik kebutuhan pakan.

## Pemberian, sisa dan pakan dikonsumsi

Setiap kandang-periode tetap mempunyai tiga bahan sesuai kombinasi kode pada workbook sebelumnya. Proporsi BK dikonsumsi bahan pertama dipilih 45–60%, bahan kedua 22–34%, dan bahan ketiga adalah sisa proporsi hingga 100%. Proporsi ini merupakan asumsi simulasi dan tidak identik dengan ransum penelitian R2 atau R3.

Untuk tiap bahan, fraksi sisa dipilih uniform 4–10%. Nilai ini merupakan asumsi, bukan persentase sisa yang dilaporkan jurnal. Jumlah diberikan diturunkan dari target konsumsi:

```text
BK_target_bahan = DMI_target × jumlah ekor × durasi × proporsi bahan
AsFed_diberikan = BK_target_bahan / (BK_pct / 100) / (1 − fraksi sisa)
AsFed_sisa = AsFed_diberikan × fraksi sisa
AsFed_dikonsumsi = AsFed_diberikan − AsFed_sisa
BK_dikonsumsi = AsFed_dikonsumsi × BK_pct / 100
Protein_dikonsumsi = BK_dikonsumsi × CP_pct_BK / 100
TDN_dikonsumsi = BK_dikonsumsi × TDN_pct_BK / 100
```

Pemberian dan sisa dibulatkan tiga desimal. Komposisi serta kadar air sisa dianggap sama dengan bahan diberikan. Pemilihan bagian pakan oleh kambing tidak dimodelkan. Semua konsumsi adalah hasil simulasi, bukan pengukuran nyata.

Kolom lama `Total_BK_kg`, `Total_Protein_kg` dan `Total_TDN_kg` pada `Pemberian_Pakan` tetap menunjukkan nutrisi **diberikan**. Kolom baru `BK_Dikonsumsi_kg`, `Protein_Dikonsumsi_kg` dan `TDN_Dikonsumsi_kg` menunjukkan nutrisi **dikonsumsi**. Total pada `Dataset_Analisis` sekarang mengagregasi kolom dikonsumsi. Perubahan definisi ini penting saat membandingkan dengan versi sebelumnya.

## Komposisi bahan pakan dan sumbernya

| ID | Bahan dalam Excel | BK (%) | Protein (% BK) | TDN (% BK) | Asal parameter |
|---|---|---:|---:|---:|---|
| P001 | Rumput Gajah | 17,64 | 8,77 | 57,62 | BK dan CP: R3 Tabel 1. TDN: rujukan lama Kamid dkk. (2024); gabungan lintas studi |
| P002 | Rumput Lapang Kering | 68,87 | 12,22 | 58,49 | Nilai sampel rujukan lama Kamid dkk. (2024) |
| P003 | Silase Jagung (buah muda) | 26,00 | 8,00 | 65,00 | Rujukan lama Umiyasih dan Wina (2008) |
| P004 | Konsentrat Kambing | 70,33 | 9,03 | 63,99 | Nilai sampel rujukan lama Kamid dkk. (2024) |
| P005 | Konsentrat Sapi Perah | 71,54 | 17,74 | 71,67 | Nilai sampel rujukan lama Kamid dkk. (2024); nama produk dipertahankan, bukan rekomendasi untuk kambing |
| P006 | Ampas Tahu Kering | 87,12 | 18,56 | 76,30 | Kusmartono dkk. (2026), tabel nutrisi bahan |
| P007 | Dedak Padi | 90,41 | 7,57 | 74,10 | Kusmartono dkk. (2026), tabel nutrisi bahan |
| P008 | Daun Lamtoro Kering | 70,35 | 27,22 | 57,00 | Nilai sampel rujukan lama Kamid dkk. (2024) |

Rujukan tambahan:

- Kamid, Khotijah dan Kumalasari (2024), *Analisis Keragaman Kualitas Nutrien Berbagai Pakan Ruminansia di Wilayah Indonesia*, JINTP 22(1):14–22: https://journal.ipb.ac.id/index.php/jurnalintp/article/view/46867. Nilai dipertahankan dan diperiksa ulang pada PDF: Tabel 13 untuk konsentrat, Tabel 14 untuk rumput, Tabel 10 dan 15 untuk lamtoro. PDF: https://journal.ipb.ac.id/jurnalintp/article/download/46867/28044/276427. Sumber menyatakan sampel dalam kondisi kering.
- Umiyasih dan Wina (2008), WARTAZOA 18(3), rujukan silase yang sudah tercatat dalam versi sebelumnya: https://download.garuda.kemdikbud.go.id/article.php?article=277932&title=Pr&val=7169. Nilai ini dipertahankan dan belum diverifikasi ulang pada revisi ini.
- Kusmartono dkk. (2026), *Effects of cassava waste- and tofu waste-based concentrate formulations on feed intake, nutrient digestibility, growth performance, and economic returns of Madura and Madrasin bulls under smallholder production systems*: https://www.veterinaryworld.org/Vol.19/July-2026/8.php. Angka ampas tahu kering dan dedak diperiksa pada tabel nutrisi bahan. Penelitian dilakukan pada sapi; hanya komposisi bahan yang dipakai, tidak ada data konsumsi atau pertumbuhan sapi yang dialihkan menjadi data kambing.

BK 75,69% pada rumput gajah versi sebelumnya berasal dari sampel kering dan tidak sesuai jika bahan dianggap hijauan segar. Karena itu BK dan CP P001 diganti dengan nilai R3. Nama bahan dengan BK tinggi dibuat eksplisit berwujud kering. Ini adalah bentuk pakan yang disimulasikan, bukan klaim bahwa nilai sampel laboratorium berlaku pada semua bahan di lapangan. TDN P001 tetap rujukan lintas studi, sehingga bukan satu paket analisis laboratorium yang sama dengan BK/CP. Kecukupan protein setiap ransum tidak dijamin oleh simulasi ini; formulasi tidak dioptimalkan untuk memenuhi semua kebutuhan nutrisi.

## Rumus dataset analisis

```text
Jumlah_Ekor = jumlah individu dengan Observation_ID yang sama
Bobot_Awal_Rata2 = rata-rata bobot awal individu
Bobot_Akhir_Rata2 = rata-rata bobot akhir individu
Total_BK = jumlah BK_Dikonsumsi semua bahan pada observasi
Total_Protein = jumlah Protein_Dikonsumsi semua bahan pada observasi
Total_TDN = jumlah TDN_Dikonsumsi semua bahan pada observasi
Protein_CP_pct = Total_Protein / Total_BK × 100
TDN_pct = Total_TDN / Total_BK × 100
DMI = Total_BK / (Jumlah_Ekor × Durasi_Hari)
ADG = (Bobot_Akhir_Rata2 − Bobot_Awal_Rata2) / Durasi_Hari
FCR_DM = DMI / ADG
```

Kolom umur, bangsa, jenis kelamin, dan status sapih ditambahkan setelah kolom analisis lama, sehingga nama A–Q tetap dapat dibaca script Pertemuan 4.

## Hasil pemeriksaan revisi

| Fase | Rata-rata bobot awal kandang (kg/ekor) | Rata-rata konsumsi BK (kg/ekor/hari) | Rentang konsumsi BK antarobservasi |
|---|---:|---:|---:|
| Starter | 13,802 | 0,505 | 0,419–0,555 |
| Grower | 20,205 | 0,753 | 0,626–0,893 |
| Finisher | 30,006 | 0,938 | 0,844–1,040 |

Pemeriksaan mencakup 60 observasi, 20 tiap fase; 180 catatan pakan dan 614 individu. Formula tidak memiliki error pada pemindaian. Semua sisa lebih kecil daripada pemberian. Total nutrisi, DMI, ADG dan FCR direkonsiliasi terhadap perhitungan mandiri. Perubahan sisa pada satu baris diuji dan mengubah DMI pada observasi terkait; nilai kemudian dikembalikan. Tampilan keenam lembar diperiksa. Hasil ini menggambarkan pemeriksaan workbook, bukan validasi biologis terhadap data peternakan.

Hasil numerik dan dokumen Pertemuan 4 yang menggunakan versi lama perlu diperbarui pada pelaksanaan berikutnya. Revisi ini tidak mengubah file Pertemuan 4 atau mengklaim hasil eksperimen sebelumnya masih berlaku.

