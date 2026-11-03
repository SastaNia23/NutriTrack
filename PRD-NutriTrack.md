# Product Requirements Document (PRD)
## NutriTrack — Web App Kalkulator & Pelacak Gizi Harian

| | |
|---|---|
| **Versi dokumen** | 1.0 (Draft) |
| **Tanggal** | 26 Oktober 2026 |
| **Status** | Draft untuk review |
| **Sumber acuan** | `code.html` (desain layar Kalkulator Gizi) dan `DESIGN.md` (NutriTrack Vitality System) |
| **Platform** | Web app responsif (desktop, tablet, mobile) |
| **Bahasa antarmuka** | Bahasa Indonesia (default), arsitektur siap multi-bahasa |

---

## 1. Ringkasan Eksekutif

NutriTrack adalah web app untuk menghitung dan melacak asupan gizi harian. Pengguna mencatat makanan, lalu aplikasi menghitung kalori, makronutrisi (karbohidrat, protein, lemak), serat, hidrasi, dan mikronutrisi penting, dan membandingkannya dengan target personal. Hasilnya ditampilkan di dasbor real-time bersama skor kualitas diet dan tips dari ahli gizi.

Desain yang sudah dibuat menampilkan satu layar utama: **Kalkulator & Pelacak Kalori Harian**. Dokumen ini menerjemahkan desain itu menjadi kebutuhan produk yang dapat dibangun, dan menjabarkan fitur pendukung yang tersirat dari navigasi (Buku Makanan, Statistik & Tren, Resep Sehat) serta footer (Integrasi Perangkat, Pusat Bantuan, Privasi & Ketentuan).

## 2. Latar Belakang & Masalah

Pencatatan gizi sering ditinggalkan pengguna karena:

1. **Terlalu lama.** Mencari makanan dan menakar porsi memakan waktu.
2. **Hasilnya sulit dibaca.** Angka mentah tanpa konteks (sisa berapa, kurang apa) tidak mendorong tindakan.
3. **Data makanan kurang lokal.** Banyak aplikasi tidak memuat makanan Indonesia (nasi merah, sayur tumis, sup jagung, dan sebagainya) dengan takaran yang umum dipakai.
4. **Target tidak personal.** Target kalori generik tidak memperhitungkan BMR, aktivitas, dan tujuan pengguna.

## 3. Tujuan & Non-Tujuan

### 3.1 Tujuan produk
- **G1.** Pengguna dapat mencatat satu makanan dalam **kurang dari 15 detik** (rata-rata).
- **G2.** Pengguna langsung melihat status hari itu (kalori, makro, air, serat, mikro) dalam **satu layar**.
- **G3.** Target kalori dan makro dihitung otomatis dari profil pengguna (BMR, aktivitas, tujuan) dan dapat disesuaikan.
- **G4.** Basis data makanan mencakup makanan Indonesia dengan takaran rumah tangga.
- **G5.** Mendorong kebiasaan: pengguna aktif mencatat minimal 5 hari per minggu.

### 3.2 Non-tujuan (di luar cakupan v1)
- Diagnosis atau terapi medis. NutriTrack adalah alat bantu, bukan pengganti konsultasi dokter.
- Konsultasi langsung dengan ahli gizi (chat atau video).
- Fitur sosial (feed, komunitas, kompetisi).
- Aplikasi native iOS/Android (v1 adalah PWA/web responsif).
- Pemindaian foto makanan dengan AI (masuk daftar eksplorasi pasca-v1).

## 4. Target Pengguna & Persona

| Persona | Deskripsi | Kebutuhan utama |
|---|---|---|
| **Sarah, Health Enthusiast** (persona pada desain) | Profesional urban, 25–35 tahun, rutin berolahraga, ingin menjaga berat badan dan pola makan seimbang | Pencatatan cepat, tampilan jelas, laporan harian |
| **Rizal, Atlet/Fitness** | Fokus pada protein dan komposisi tubuh | Kontrol rasio makro, target protein, tren mingguan |
| **Bu Ratna, Pengelola Kesehatan** | Mengelola diet karena kondisi tertentu (misalnya gula darah, kolesterol) | Pembatasan gula/lemak, pemantauan serat, ekspor laporan untuk dokter |

## 5. Ruang Lingkup & Rilis

Desain yang tersedia baru mencakup layar **Kalkulator Gizi**. Layar lain muncul di navigasi tetapi belum didesain.

| Fase | Cakupan | Catatan |
|---|---|---|
| **MVP (v1.0)** | Autentikasi & onboarding, Kalkulator Gizi (dasbor harian), Buku Harian Makanan, Kalkulator Cepat, pelacak air, target personal, skor diet, ekspor laporan harian | Sesuai desain yang ada |
| **v1.1** | Buku Makanan (database & makanan/resep kustom), Statistik & Tren | Perlu desain baru |
| **v1.2** | Resep Sehat, notifikasi lanjutan, Pusat Bantuan | Perlu desain baru |
| **v2.0** | Integrasi Perangkat (wearable, aplikasi kesehatan), input foto/barcode | Eksplorasi |

## 6. Struktur Informasi & Navigasi

**Header (fixed):** logo NutriTrack, menu utama, pemilih tanggal, tombol *Tambah Makanan*, notifikasi, profil.

| Menu | Fase |
|---|---|
| Kalkulator Gizi (aktif/default) | MVP |
| Buku Makanan | v1.1 |
| Statistik & Tren | v1.1 |
| Resep Sehat | v1.2 |

**Footer:** Pusat Bantuan, Privasi & Ketentuan, Integrasi Perangkat.

**Perilaku responsif navigasi:** menu utama tampil sebagai navigasi horizontal pada layar ≥ 1280px (breakpoint `xl`). Pada layar lebih kecil, menu berpindah ke **bottom navigation** persisten sesuai `DESIGN.md` (mobile < 768px).

## 7. Kebutuhan Fungsional

Prioritas: **P0** = wajib MVP, **P1** = sebaiknya MVP, **P2** = pasca-MVP.

### 7.1 Autentikasi & Onboarding

| ID | Kebutuhan | Prioritas |
|---|---|---|
| AUTH-1 | Pengguna dapat mendaftar dan masuk dengan email + kata sandi dan dengan akun Google. | P0 |
| AUTH-2 | Reset kata sandi melalui email. | P0 |
| ONB-1 | Onboarding mengumpulkan: jenis kelamin, tanggal lahir, tinggi, berat, tingkat aktivitas, tujuan (turun, jaga, naik berat badan), preferensi/pembatasan diet. | P0 |
| ONB-2 | Setelah onboarding, sistem menghitung dan menampilkan target kalori & makro awal beserta penjelasannya; pengguna dapat mengubahnya. | P0 |
| ONB-3 | Persetujuan privasi dan disclaimer medis ditampilkan dan dicatat sebelum data kesehatan disimpan. | P0 |

### 7.2 Header & Pemilih Tanggal

| ID | Kebutuhan | Prioritas |
|---|---|---|
| HDR-1 | Pemilih tanggal menampilkan "Hari Ini, [tanggal]" secara default; pengguna dapat berpindah ke tanggal lain (lampau) untuk melihat atau mengedit catatan. | P0 |
| HDR-2 | Seluruh data di dasbor (ring kalori, makro, air, buku harian, skor, mikro) mengikuti tanggal terpilih. | P0 |
| HDR-3 | Tombol **Tambah Makanan** membuka panel/modal pencatatan makanan dengan pilihan waktu makan. | P0 |
| HDR-4 | Ikon notifikasi menampilkan titik merah bila ada notifikasi belum dibaca (pengingat makan, air, target tercapai). | P1 |
| HDR-5 | Avatar menampilkan nama dan label profil pengguna; menu berisi Profil, Target, Pengaturan, Keluar. | P0 |

### 7.3 Hero Banner (Greeting & Aksi Cepat)

| ID | Kebutuhan | Prioritas |
|---|---|---|
| HERO-1 | Menampilkan badge "Pelacak Harian Real-time" dengan indikator pulsa dan **waktu pembaruan terakhir** (contoh: "Update: 19:42 WIB") yang diambil dari waktu catatan terakhir/sinkronisasi. | P0 |
| HERO-2 | Tombol **Sesuaikan Target** membuka pengaturan target (lihat 7.9). | P0 |
| HERO-3 | Tombol **Unduh Laporan Hari Ini** menghasilkan laporan harian dalam format PDF (lihat 7.10). | P1 |

### 7.4 Ringkasan Kalori (Kartu Ring Kalori)

| ID | Kebutuhan | Prioritas |
|---|---|---|
| CAL-1 | Menampilkan ring progres: kalori terkonsumsi dari target, angka di tengah, teks "dari X kkal", dan persentase "N% Terpenuhi". | P0 |
| CAL-2 | Menampilkan rincian: **Terkonsumsi**, **Target Harian**, **Sisa Kalori**, serta **Target BMR** dan **Aktivitas Fisik** (kalori tambahan dari aktivitas). | P0 |
| CAL-3 | Target Harian = BMR × faktor aktivitas ± penyesuaian tujuan, atau nilai manual (lihat bagian 9). Pada desain: BMR 1.550 + aktivitas 550 = 2.100 kkal. | P0 |
| CAL-4 | Badge status ("Optimal") dihitung dari rasio terkonsumsi terhadap target dengan ambang yang dapat dikonfigurasi (lihat 9.4). | P1 |
| CAL-5 | Jika melebihi target, ring dan sisa kalori berubah ke status peringatan (warna `error`/`tertiary`) tanpa bahasa yang menghakimi. | P0 |
| CAL-6 | Angka diformat sesuai lokal Indonesia (pemisah ribuan titik: `1.450`) dengan tabular figures. | P0 |
| CAL-7 | Animasi transisi ring (±700 ms, ease-out) ketika data berubah. | P2 |

### 7.5 Komposisi Nutrisi (Makro, Serat, Air)

| ID | Kebutuhan | Prioritas |
|---|---|---|
| MAC-1 | Menampilkan tiga makro: **Karbohidrat**, **Protein**, **Lemak Sehat**, masing-masing dengan persentase terpenuhi, nilai terkonsumsi, target (gram), dan sisa gram. | P0 |
| MAC-2 | Menampilkan subjudul rasio makro target (contoh: "Berdasarkan rasio 50:20:30"). Rasio dapat diubah pengguna (lihat 7.9). | P0 |
| MAC-3 | Setiap makro memakai warna semantik dari `DESIGN.md`: Karbohidrat = amber, Protein = rose, Lemak = indigo/ungu. | P0 |
| MAC-4 | **Serat Makanan:** menampilkan konsumsi vs target (contoh 22g / 28g) dan status teks ("Memenuhi rekomendasi harian") yang dihitung dari persentase. | P0 |
| MAC-5 | **Asupan Air Bersih:** menampilkan konsumsi vs target (1,8 L / 2,5 L), persentase, dan jumlah gelas (7 dari 10). | P0 |
| MAC-6 | Tombol **+ 1 Gelas** menambah satu gelas (default 250 ml, ukuran gelas dapat diatur) dengan pembaruan instan; tersedia undo. | P0 |
| MAC-7 | Pengguna dapat mengurangi atau mengoreksi asupan air (misalnya salah tekan). | P1 |

### 7.6 Buku Harian Makanan

Kartu daftar makanan terkelompok per waktu makan.

| ID | Kebutuhan | Prioritas |
|---|---|---|
| LOG-1 | Empat grup: **Sarapan**, **Makan Siang**, **Makan Malam**, **Camilan Sehat & Suplemen**. | P0 |
| LOG-2 | Header grup menampilkan ikon, nama, **rentang waktu** (contoh 07:15–08:00 WIB), total kalori grup, **anggaran kalori grup** (contoh "/ ~450 kkal"), dan badge status ("Tercapai"). | P0 |
| LOG-3 | Baris item menampilkan ikon/thumbnail, nama makanan, takaran (contoh "1 mangkuk sedang (200g)"), chip makro **P / C / F** dalam gram, dan kalori item (kkal). | P0 |
| LOG-4 | Menu overflow (`more_vert`) per item: Ubah porsi, Pindahkan ke waktu makan lain, Duplikasi, Simpan sebagai favorit, Hapus. | P0 |
| LOG-5 | Tombol **+ Tambah Menu [Waktu Makan]** di setiap grup membuka pencarian makanan dengan waktu makan terisi otomatis. | P0 |
| LOG-6 | Anggaran kalori per waktu makan default-nya adalah persentase dari target harian (lihat 9.5) dan dapat diubah. | P1 |
| LOG-7 | Badge status per grup: *Belum dicatat*, *Dalam proses*, *Tercapai*, *Melebihi*. | P1 |
| LOG-8 | Grup dapat dilipat/diperluas; grup yang kosong menampilkan empty state dengan ajakan mencatat. | P1 |
| LOG-9 | Tombol **Riwayat 7 Hari Lalu** menampilkan ringkasan 7 hari terakhir dan memungkinkan menyalin makanan dari hari tertentu ke hari ini. | P1 |
| LOG-10 | Hapus/ubah item memperbarui seluruh kartu di dasbor secara instan; hapus dapat dibatalkan (undo snackbar). | P0 |

### 7.7 Kalkulator Cepat Kalori

Formulir pencatatan instan (pada desain berada di kolom samping).

| ID | Kebutuhan | Prioritas |
|---|---|---|
| QC-1 | Field **Nama Makanan / Bahan** dengan autocomplete dari database makanan (ikon pencarian). | P0 |
| QC-2 | Field **Porsi / Takaran** bernilai numerik dengan pemilih satuan di sisi kanan (g, ml, oz, porsi, sendok, gelas, sesuai `DESIGN.md`). | P0 |
| QC-3 | Pilihan **Kategori Waktu**: Sarapan, Makan Siang, Makan Malam, Camilan/Snack. Default berdasarkan jam saat ini. | P0 |
| QC-4 | **Perkiraan Kalori** diperbarui real-time saat nama makanan, takaran, atau satuan berubah, bersama estimasi P dan C (dan F). | P0 |
| QC-5 | Tombol **Hitung & Catat Sekarang** menyimpan entri. Status tombol: normal → menyimpan ("Menyimpan Data...") → sukses ("Makanan Dicatat!") → kembali normal; field nama dikosongkan setelah sukses. | P0 |
| QC-6 | Validasi: nama wajib dipilih dari database atau dibuat sebagai makanan kustom; porsi > 0. Pesan error ditampilkan inline. | P0 |
| QC-7 | Jika makanan tidak ditemukan, tawarkan **Buat makanan kustom** (nama, kalori, P/C/F per takaran). | P1 |
| QC-8 | Dukungan keyboard: Enter untuk simpan, fokus kembali ke nama makanan untuk input beruntun. | P1 |

> **Catatan implementasi:** prototipe HTML saat ini memakai estimasi placeholder `gram × 1,3`. Implementasi produksi **harus** menghitung dari data nutrisi per 100 g makanan terpilih (lihat bagian 9.1), bukan faktor tetap.

### 7.8 Skor Kualitas Diet, Tips Ahli Gizi, Mikronutrisi

| ID | Kebutuhan | Prioritas |
|---|---|---|
| SCR-1 | Menampilkan **Skor Kualitas Diet Hari Ini** (0–100) dengan label tingkat ("Sangat Baik!") dan teks penjelasan faktor penyumbang skor. | P0 |
| SCR-2 | Skor dihitung dari komponen yang transparan (lihat 9.6) dan dapat dilihat rinciannya. | P1 |
| SCR-3 | Kartu **Catatan & Tips Ahli Gizi** menampilkan kutipan tips kontekstual dengan atribusi (nama, gelar, jabatan) dan lencana terverifikasi. | P1 |
| SCR-4 | Tips dikurasi tim ahli gizi dan dipilih berdasarkan aturan (misalnya kandungan omega-3 malam ini, sisa hidrasi). Tips otomatis tanpa review ahli **tidak boleh** memakai atribusi ahli gizi. | P0 |
| SCR-5 | Tombol "suka/berguna" (`thumb_up`) pada tips untuk umpan balik. | P2 |
| MIC-1 | Panel **Mikronutrisi Penting** menampilkan bar progres: Zat Besi, Kalsium, Vitamin C (nilai / target dan persentase). Nilai ≥ 100% berlabel "Optimal". | P0 |
| MIC-2 | Daftar mikronutrisi yang ditampilkan dapat dikustomisasi pengguna (misalnya natrium, kalium, vitamin D, B12). | P2 |
| MIC-3 | Target mikronutrisi mengikuti jenis kelamin, usia, dan kondisi khusus (misalnya zat besi 18 mg untuk wanita usia subur). | P1 |

### 7.9 Pengaturan Target ("Sesuaikan Target")

| ID | Kebutuhan | Prioritas |
|---|---|---|
| TGT-1 | Pengguna dapat memilih mode **Otomatis** (dihitung sistem) atau **Manual**. | P0 |
| TGT-2 | Dapat mengubah: target kalori, rasio makro (karbo:protein:lemak, total = 100%), target serat, target air, target berat badan/tujuan. | P0 |
| TGT-3 | Pratinjau perubahan: menampilkan target gram yang dihasilkan dari rasio sebelum disimpan. | P1 |
| TGT-4 | Peringatan keamanan bila target kalori di bawah batas minimum yang aman (lihat 10.5). | P0 |
| TGT-5 | Perubahan target berlaku mulai hari ini; data historis tidak berubah (target disimpan per hari/versi). | P0 |
| TGT-6 | Pencatatan aktivitas fisik (manual: jenis, durasi → kalori terbakar) yang menambah target pada kartu kalori ("Aktivitas Fisik: +550 kkal"). Impor otomatis dari perangkat menyusul pada v2.0. | P1 |

### 7.10 Laporan & Ekspor

| ID | Kebutuhan | Prioritas |
|---|---|---|
| RPT-1 | **Unduh Laporan Hari Ini** menghasilkan PDF: ringkasan kalori, makro, serat, air, daftar makanan per waktu makan, mikronutrisi, skor diet. | P1 |
| RPT-2 | Nama file berformat `NutriTrack-Laporan-YYYY-MM-DD.pdf`. | P1 |
| RPT-3 | Ekspor data mentah (CSV) dari pengaturan akun. | P2 |

### 7.11 Halaman Pendukung (setelah MVP)

| ID | Kebutuhan | Prioritas |
|---|---|---|
| FOOD-1 | **Buku Makanan:** jelajah dan cari database, makanan favorit, makanan kustom, kombinasi/resep tersimpan. | P1 (v1.1) |
| TREN-1 | **Statistik & Tren:** grafik kalori, makro, berat badan, air, skor diet dalam rentang 7/30/90 hari; rata-rata dan konsistensi pencatatan. | P1 (v1.1) |
| RES-1 | **Resep Sehat:** daftar resep dengan info gizi per porsi dan tombol "Catat ke buku harian". | P2 (v1.2) |
| DEV-1 | **Integrasi Perangkat:** sinkronisasi aktivitas dan langkah dari aplikasi/wearable (misalnya Google Fit, Apple Health). | P2 (v2.0) |
| HELP-1 | **Pusat Bantuan:** FAQ, panduan penggunaan, formulir kontak. | P1 (v1.2) |
| LEGAL-1 | **Privasi & Ketentuan:** halaman kebijakan privasi dan syarat layanan. | P0 |

## 8. Alur Pengguna Utama

**Alur A — Mencatat makanan via Kalkulator Cepat**
1. Pengguna membuka Kalkulator Gizi (tanggal hari ini).
2. Mengetik nama makanan, memilih hasil autocomplete.
3. Mengisi takaran dan satuan; perkiraan kalori dan makro muncul.
4. Memilih kategori waktu (default sesuai jam).
5. Menekan **Hitung & Catat Sekarang** → status sukses → seluruh kartu dasbor (ring, makro, buku harian, skor, mikro) diperbarui.

**Alur B — Menambah makanan dari grup waktu makan**
1. Pengguna menekan **+ Tambah Menu Makan Siang**.
2. Panel pencarian terbuka dengan waktu makan terisi.
3. Memilih makanan dan porsi → disimpan ke grup tersebut.

**Alur C — Mencatat air**
1. Pengguna menekan **+ 1 Gelas** → bar air, persentase, dan jumlah gelas bertambah seketika.

**Alur D — Mengubah target**
1. Pengguna menekan **Sesuaikan Target** → mengubah kalori/rasio makro → melihat pratinjau → menyimpan → dasbor menghitung ulang.

**Alur E — Meninjau hari sebelumnya**
1. Pengguna membuka pemilih tanggal atau **Riwayat 7 Hari Lalu** → memilih hari → dasbor menampilkan data hari itu (mode lihat/edit).

**Alur F — Mengunduh laporan**
1. Pengguna menekan **Unduh Laporan Hari Ini** → PDF dibuat dan diunduh.

## 9. Logika Perhitungan Gizi

### 9.1 Data makanan
- Nilai nutrisi disimpan **per 100 g (atau per 100 ml)** dan/atau per takaran umum: energi (kkal), protein, karbohidrat, lemak, serat, gula, natrium, dan mikronutrisi prioritas (zat besi, kalsium, vitamin C).
- Nilai item = `nilai_per_100g × (gram_porsi / 100)`.
- Konversi takaran rumah tangga (mangkuk, butir, gelas, sendok) ke gram disimpan per makanan.
- Sumber data yang direkomendasikan: Tabel Komposisi Pangan Indonesia (TKPI) untuk makanan lokal, dilengkapi sumber internasional tervalidasi (contoh USDA FoodData Central) untuk makanan lain. Lisensi dan atribusi setiap sumber harus dikonfirmasi sebelum dipakai.

### 9.2 Energi & makro
- Energi makro: karbohidrat 4 kkal/g, protein 4 kkal/g, lemak 9 kkal/g.
- Target gram makro = `(target_kalori × rasio_makro) / kkal_per_gram`.
- Contoh: target 2.100 kkal, rasio 50:20:30 → karbo ≈ 262 g, protein ≈ 105 g, lemak ≈ 70 g (desain menampilkan 260/110/65 g sebagai nilai bulat).

### 9.3 BMR & kebutuhan energi
- **BMR** memakai persamaan **Mifflin-St Jeor**:
  - Pria: `10×BB(kg) + 6,25×TB(cm) − 5×usia + 5`
  - Wanita: `10×BB(kg) + 6,25×TB(cm) − 5×usia − 161`
- **Target harian** = `BMR + kalori aktivitas`, atau `BMR × faktor aktivitas` bila aktivitas belum dicatat (sedentari 1,2; ringan 1,375; sedang 1,55; berat 1,725).
- Penyesuaian tujuan: turun berat badan −10–20% (tidak melewati batas minimum 10.5); naik berat badan +10–15%.

### 9.4 Status kalori (badge)
Ambang awal (dapat disesuaikan setelah uji pengguna):

| Rasio terkonsumsi/target | Status |
|---|---|
| < 50% (pada akhir hari) | Kurang |
| 50–110% | Optimal |
| > 110% | Berlebih |

Status juga mempertimbangkan waktu dalam sehari agar pengguna pagi hari tidak langsung dilabeli "Kurang".

### 9.5 Anggaran per waktu makan (default)
Sarapan 22%, Makan Siang 33%, Makan Malam 26%, Camilan 10%, sisa 9% cadangan. Nilai ini diturunkan dari desain (≈450/700/550/200 kkal dari 2.100) dan dapat diubah di pengaturan.

### 9.6 Skor kualitas diet (0–100)
Skor transparan berbasis komponen berbobot. Usulan awal:

| Komponen | Bobot |
|---|---|
| Kesesuaian kalori dengan target | 25 |
| Keseimbangan makro vs rasio target | 20 |
| Kecukupan protein | 15 |
| Kecukupan serat | 15 |
| Hidrasi | 10 |
| Kecukupan mikronutrisi prioritas | 10 |
| Pembatasan gula tambahan/natrium | 5 |

Rumus final perlu divalidasi oleh ahli gizi. Label skor: ≥ 85 Sangat Baik, 70–84 Baik, 50–69 Cukup, < 50 Perlu Perbaikan.

### 9.7 Hidrasi
- Target air default dihitung dari berat badan (≈ 30–35 ml/kg) dan dapat diubah manual. Desain memakai 2,5 L.
- 1 gelas = 250 ml (default). Jumlah gelas = `ml / ukuran_gelas`.

## 10. Kebutuhan Non-Fungsional

### 10.1 Performa
- Largest Contentful Paint < 2,5 detik pada jaringan 4G.
- Pembaruan dasbor setelah mencatat makanan < 300 ms (optimistic UI), konfirmasi server di latar belakang.
- Autocomplete pencarian makanan merespons < 300 ms (p95).

### 10.2 Keandalan & Data
- Ketersediaan target 99,5%.
- Pencatatan tidak boleh hilang saat koneksi terputus: antrean offline (PWA) dengan sinkronisasi otomatis dan penyelesaian konflik last-write-wins per entri.
- Backup harian dan retensi data sesuai kebijakan privasi.

### 10.3 Keamanan & Privasi
- Data kesehatan diperlakukan sebagai **data pribadi sensitif**: enkripsi saat transit (TLS) dan saat disimpan, kontrol akses berbasis peran.
- Kepatuhan terhadap **UU Pelindungan Data Pribadi (UU PDP) No. 27/2022**: persetujuan eksplisit, hak akses/koreksi/hapus data, ekspor data, dan penghapusan akun.
- Tidak menjual data pengguna. Analitik memakai data teragregasi/anonim.
- Proteksi terhadap serangan umum (OWASP Top 10), pembatasan laju (rate limiting), dan manajemen sesi aman.

### 10.4 Aksesibilitas
- Target **WCAG 2.1 AA**: kontras warna memadai, navigasi keyboard penuh, fokus terlihat (halo emerald sesuai `DESIGN.md`), label ARIA pada ring dan bar progres (nilai, minimum, maksimum), dan makna tidak bergantung pada warna semata (selalu disertai teks/ikon).
- Mendukung `prefers-reduced-motion` untuk animasi pulsa dan ring.
- Target sentuh minimum 44×44 px pada mobile; tinggi input 48 px (mobile) dan 44 px (desktop).

### 10.5 Keamanan Medis & Disclaimer
- Disclaimer permanen: informasi bersifat edukatif dan bukan nasihat medis.
- Target kalori tidak boleh diset di bawah batas aman (usulan: minimum 1.200 kkal untuk wanita dan 1.500 kkal untuk pria tanpa pengawasan tenaga kesehatan) tanpa peringatan jelas.
- Tidak diperuntukkan bagi pengguna di bawah 18 tahun, ibu hamil/menyusui, atau penderita gangguan makan tanpa arahan tenaga kesehatan; ditampilkan pada onboarding.
- Bahasa produk tidak mendorong perilaku makan tidak sehat (hindari framing "dosa", "hukuman", atau pengurangan ekstrem).

### 10.6 Kompatibilitas
- Browser: dua versi terbaru Chrome, Safari, Firefox, Edge.
- Breakpoint: Desktop ≥ 1024 px, Tablet 768–1023 px, Mobile < 768 px.
- Dapat dipasang sebagai PWA.

### 10.7 Lokalisasi
- Bahasa Indonesia default, zona waktu WIB/WITA/WIT mengikuti pengguna.
- Format angka lokal Indonesia (`1.450`, desimal koma pada teks, misalnya "1,8 L").
- Seluruh teks UI dipisahkan ke berkas terjemahan untuk memudahkan penambahan bahasa.

## 11. Kebutuhan Desain & UI

Mengacu pada **NutriTrack Vitality System** (`DESIGN.md`) dan implementasi prototipe `code.html`.

| Aspek | Ketentuan |
|---|---|
| **Tipografi** | Plus Jakarta Sans. Angka nutrisi memakai tabular figures (`tnum`). Label kategori makro memakai `label-sm`, huruf kapital, dan tracking. |
| **Warna** | Primary hijau emerald (token `primary` `#006c49`, `primary-container` `#10b981`). Karbohidrat = amber, Protein = rose, Lemak = indigo/ungu. Permukaan kartu putih di atas kanvas mint. |
| **Bentuk** | Kartu utama `rounded-2xl`; elemen sekunder `rounded-xl`; chip/badge/tombol cepat `rounded-full`. |
| **Elevasi** | Level 1 kartu (bayangan ambient hijau/slate), Level 2 elemen interaktif mengambang, Level 3 modal dengan blur latar. |
| **Grid & spasi** | Skala 8 px. Desktop 12 kolom (maks. 1440 px, gutter 24 px), tablet 8 kolom (gutter 20 px), mobile 4 kolom (gutter 16 px). |
| **Tata letak desktop** | Baris atas: hero banner. Grid 12 kolom: kartu kalori (5 kolom) + kartu komposisi nutrisi; di bawahnya buku harian (utama) dan kolom samping berisi kalkulator cepat, skor diet, tips ahli gizi, mikronutrisi. |
| **Tablet** | Panel samping menjadi *slide-over sheet* yang dapat dilipat. |
| **Mobile** | Seluruh blok bertumpuk dalam satu alur scroll harian, dengan bottom navigation persisten. |
| **Ikon** | Material Symbols Outlined. |
| **Komponen** | Tombol primer/sekunder, ikon quick-add, ring progres, bar progres tersegmentasi, kartu metrik, chip makro, input dengan pemilih satuan, baris daftar makanan. |

**Status UI yang harus dirancang (belum ada pada desain):** loading (skeleton), empty state (hari tanpa catatan), error jaringan, kondisi melebihi target, mode offline, tampilan tanggal lampau, modal tambah/ubah makanan, modal sesuaikan target, onboarding, dan halaman login/daftar.

## 12. Model Data (Tingkat Tinggi)

| Entitas | Atribut utama |
|---|---|
| **User** | id, email, nama, avatar, jenis kelamin, tanggal lahir, tinggi, zona waktu, bahasa, persetujuan privasi (versi, waktu) |
| **BodyMetric** | user_id, tanggal, berat badan |
| **Goal** | user_id, berlaku_mulai, mode (otomatis/manual), kalori, rasio karbo/protein/lemak, serat, air, tujuan |
| **Food** | id, nama, kategori, sumber, kalori/protein/karbo/lemak/serat per 100 g, mikronutrisi, `is_custom`, owner_id |
| **FoodServing** | food_id, label takaran (mangkuk, butir...), gram setara |
| **FoodLog** | id, user_id, food_id, tanggal, waktu_makan (enum), waktu dicatat, jumlah, satuan, gram_setara, snapshot nilai nutrisi |
| **WaterLog** | id, user_id, tanggal, volume_ml, waktu |
| **ActivityLog** | id, user_id, tanggal, jenis, durasi, kalori_terbakar, sumber (manual/perangkat) |
| **DietScore** | user_id, tanggal, skor, rincian komponen |
| **Tip** | id, teks, penulis (ahli gizi), aturan pemicu, status review |
| **Favorite / Recipe** | user_id, daftar item, nama |

Catatan: `FoodLog` menyimpan **snapshot nilai nutrisi** saat dicatat agar catatan historis tidak berubah ketika data makanan diperbarui.

## 13. Kebutuhan Teknis (Rekomendasi)

Bagian ini bersifat rekomendasi dan dapat disesuaikan tim engineering.

- **Frontend:** SPA berbasis React/Next.js (atau setara) dengan Tailwind CSS (selaras dengan token pada `code.html`), state management ringan, grafik via SVG/library (ring dan bar sudah berbasis SVG/CSS pada desain).
- **Backend:** REST atau GraphQL API; autentikasi berbasis token (JWT/OAuth2).
- **Database:** PostgreSQL untuk data relasional; pencarian makanan dengan full-text search (misalnya Postgres FTS atau Meilisearch/Elasticsearch) yang mendukung toleransi salah ketik dan sinonim Bahasa Indonesia.
- **Aset:** font dan ikon dilayani dari sumber sendiri/CDN tepercaya; tidak bergantung pada gambar eksternal untuk logo dan avatar.
- **Infrastruktur:** CI/CD, lingkungan staging, pemantauan error dan performa.

**Ringkasan endpoint inti:**

| Endpoint | Fungsi |
|---|---|
| `GET /summary?date=` | Ringkasan harian (kalori, makro, serat, air, skor, mikro) |
| `GET /foods?q=` | Pencarian/autocomplete makanan |
| `POST /logs` · `PATCH /logs/:id` · `DELETE /logs/:id` | Kelola catatan makanan |
| `POST /water` | Tambah asupan air |
| `GET/PUT /goals` | Baca dan ubah target |
| `GET /history?days=7` | Riwayat |
| `GET /report?date=` | Laporan PDF harian |

## 14. Metrik Keberhasilan

| Metrik | Target (3 bulan setelah peluncuran) |
|---|---|
| Waktu rata-rata mencatat 1 makanan | ≤ 15 detik |
| Aktivasi: pengguna baru yang mencatat ≥ 3 makanan di hari pertama | ≥ 60% |
| Retensi D7 / D30 | ≥ 35% / ≥ 20% |
| Pengguna aktif mingguan yang mencatat ≥ 5 hari/minggu | ≥ 40% |
| Rata-rata hari tercatat lengkap (≥ 3 waktu makan) | ≥ 70% dari hari aktif |
| Tingkat "makanan tidak ditemukan" pada pencarian | < 10% |
| Skor kepuasan (CSAT) | ≥ 4,3 / 5 |
| LCP p75 | < 2,5 detik |

**Event analitik utama:** `signup_completed`, `onboarding_completed`, `food_logged` (sumber: kalkulator cepat / grup waktu makan / riwayat), `food_search_no_result`, `water_added`, `goal_changed`, `report_downloaded`, `date_changed`, `tip_feedback`.

## 15. Risiko & Mitigasi

| Risiko | Dampak | Mitigasi |
|---|---|---|
| Data makanan Indonesia tidak lengkap/akurat | Kepercayaan pengguna turun | Gunakan TKPI sebagai basis, makanan kustom, mekanisme laporan data salah, kurasi ahli gizi |
| Estimasi kalori yang salah dipahami sebagai akurat | Keputusan diet keliru | Tampilkan "perkiraan", jelaskan sumber, sediakan disclaimer |
| Pengguna dengan riwayat gangguan makan | Dampak kesehatan | Batas aman target, bahasa netral, opsi menyembunyikan angka kalori, rujukan ke tenaga kesehatan |
| Pelanggaran data pribadi | Hukum & reputasi | Enkripsi, kontrol akses, audit, kepatuhan UU PDP |
| Atribusi "dr." pada tips tanpa review ahli | Klaim menyesatkan | Wajibkan alur review ahli gizi (SCR-4) |
| Pencatatan terlalu memberatkan | Retensi rendah | Favorit, salin dari hari lain, autocomplete cepat, porsi umum |
| Lisensi data nutrisi | Risiko hukum | Verifikasi lisensi sebelum impor |

## 16. Rencana Rilis (Usulan)

| Tahap | Isi | Perkiraan |
|---|---|---|
| **0. Discovery & desain lanjutan** | Validasi PRD, desain layar yang belum ada (onboarding, modal, Buku Makanan, Tren), kurasi data makanan | 3–4 minggu |
| **1. MVP internal (alpha)** | Auth, onboarding, dasbor, buku harian, kalkulator cepat, air | 8–10 minggu |
| **2. Beta tertutup** | Skor diet, tips, laporan PDF, uji kegunaan, perbaikan akurasi data | 4–6 minggu |
| **3. Peluncuran v1.0** | Hardening keamanan, aksesibilitas, performa, analitik | 2–3 minggu |
| **4. v1.1 / v1.2** | Buku Makanan, Statistik & Tren, Resep Sehat, Pusat Bantuan | Menyusul |

Perkiraan waktu bersifat indikatif dan bergantung pada ukuran tim.

## 17. Pertanyaan Terbuka

1. Model bisnis: gratis, freemium, atau berlangganan? Fitur mana yang berbayar (misalnya laporan, tren lanjutan, integrasi)?
2. Siapa yang menjadi ahli gizi pada kartu tips ("dr. Dania Sp.GK")? Apakah ada kemitraan nyata, dan bagaimana alur review kontennya?
3. Sumber data makanan dan lisensinya (TKPI, USDA, atau kerja sama dengan pihak lain)?
4. Apakah rasio makro 50:20:30 pada desain menjadi default, atau bergantung pada tujuan pengguna?
5. Apakah aplikasi native akan dikembangkan setelah web app terbukti?
6. Apakah diperlukan mode multi-profil (misalnya keluarga)?
7. Batas usia dan kebijakan untuk kondisi khusus (hamil, penyakit kronis).

## 18. Catatan Konsistensi pada Desain Saat Ini

Beberapa hal yang ditemukan pada `code.html` dan `DESIGN.md` dan perlu diputuskan sebelum implementasi:

1. **Total kalori tidak konsisten.** Ring menampilkan 1.450 kkal terkonsumsi, sedangkan jumlah grup pada buku harian adalah 380 + 620 + 410 + 160 = 1.570 kkal. Selain itu, item Makan Siang berjumlah 165 + 198 + 85 + 112 = 560 kkal, bukan 620. Produksi harus menghitung semua angka dari satu sumber data.
2. **Anggaran waktu makan** (≈450 + 700 + 550 + 200 = 1.900 kkal) tidak sama dengan target harian 2.100 kkal. Perlu aturan alokasi (lihat 9.5).
3. **Kalori per item** pada beberapa baris tidak cocok dengan rumus 4/4/9 dari P/C/F yang ditampilkan (misalnya sebagian nilai bersumber dari tabel makanan yang berbeda). Tentukan apakah kalori mengikuti data sumber atau dihitung dari makro.
4. **Token warna.** Prosa `DESIGN.md` menyebut primary `#10B981` dan `#059669`, sedangkan token dan kode memakai `primary` `#006c49` dengan `primary-container` `#10b981`. Tetapkan satu sumber kebenaran untuk token desain.
5. **Radius.** `DESIGN.md` menetapkan kartu `rounded-2xl` = 24 px, sedangkan konfigurasi Tailwind pada prototipe tidak mendefinisikan ulang `2xl` (default Tailwind 16 px). Samakan nilainya.
6. **Aset eksternal.** Logo dan avatar pada prototipe dimuat dari URL eksternal; ganti dengan aset yang dikelola sendiri.
7. **Teks khusus tanggal/waktu.** "Hari Ini, 24 Mei" dan "Update: 19:42 WIB" masih statis dan harus dinamis.

---

*Dokumen ini adalah draft awal dan perlu direview bersama tim produk, desain, engineering, dan ahli gizi sebelum difinalkan.*
