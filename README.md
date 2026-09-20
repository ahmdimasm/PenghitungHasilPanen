## 👥 Anggota Kelompok

- **Dimas:** Fitur Input Data Panen ( `feature-input` )
- **Malah:** Fitur Cetak Laporan Struk ( `feature-laporan` )
- **Tivani:** Fitur Perhitungan Diskon & Total ( `feature-diskon` )

---

## 🛠️ Deskripsi Program

Aplikasi Python ini digunakan untuk mencatat transaksi penjualan komoditas panen, menghitung potongan diskon berdasarkan besaran subtotal, serta mencetak laporan/struk transaksi akhir secara otomatis.

graph TD
    A([Mulai Program]) --> B(Inisialisasi Data Kosong)
    
    subgraph Fitur Input Data - Tivani
        B --> C[/Input Nama Tanaman/]
        C --> D{Apakah input == 'selesai'?}
        D -- Tidak --> E[/Input Berat & Harga/]
        E --> F[Hitung Subtotal per Tanaman]
        F --> G[Simpan ke Dictionary Data Panen]
        G --> C
    end
    
    subgraph Fitur Diskon & Total - Dimas
        D -- Ya --> H[Hitung Total Berat & Total Subtotal Semua Tanaman]
        H --> I{Evaluasi Besaran Subtotal}
        I --> J[Tentukan Persentase Diskon]
        J --> K[Hitung Nilai Potongan Diskon]
        K --> L[Hitung Total Bersih Akhir]
    end
    
    subgraph Fitur Laporan Struk - Malah
        L --> M[Format Data menjadi Teks Struk]
        M --> N[Ambil Waktu & Tanggal Saat Ini]
        N --> O[/Cetak Struk ke Layar Terminal/]
        O --> P[Simpan Struk ke File .txt]
    end
    
    P --> Q([Selesai])
