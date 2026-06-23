# Monitoring Aset LPHD — PRCF Indonesia

Situs web statis untuk menampilkan data inventaris dan kondisi aset enam lokasi **Lembaga Pengelola Hutan Desa (LPHD)** dampingan PRCF Indonesia, agar informasinya dapat diakses terbuka oleh masyarakat, pengurus, dan mitra.

**Lokasi:** Nanga Betung · Nanga Jemah · Penepian Raya · Sri Wangi · Tanjung · PRCF (Kantor)

## Fitur

- Dashboard statistik total aset & ringkasan kondisi (Baik / Rusak / Hilang / Perbaikan / Belum Tercatat)
- Tab per lokasi dengan bar ringkasan kondisi
- Pencarian (nama barang, kode aset, serial, pemasok)
- Filter kategori & kondisi, serta pengurutan kolom
- Baris detail yang dapat diperluas: serial, pemasok, garansi, penanggung jawab, dan **riwayat kondisi per tahun (Y1–Y5)**
- Responsif untuk ponsel

## Isi folder

```
index.html    → halaman web (seluruh tampilan & logika)
data.json     → data aset (1.224 item dari 6 lokasi)
.nojekyll     → menonaktifkan pemrosesan Jekyll di GitHub Pages
```

## Cara publikasi di GitHub Pages (gratis)

1. Buat repository baru di GitHub, misalnya `monitoring-aset-lphd`.
2. Unggah ketiga berkas di atas (`index.html`, `data.json`, `.nojekyll`) ke root repository.
3. Buka **Settings → Pages**.
4. Pada **Source**, pilih branch `main` dan folder `/ (root)`, lalu **Save**.
5. Tunggu ±1 menit. Situs akan tersedia di:
   `https://NAMA-AKUN.github.io/monitoring-aset-lphd/`

> Opsional: ubah tautan tombol "Lihat di GitHub" pada `index.html`
> (cari `id="ghlink"`) agar mengarah ke repository Anda.

## Cara memperbarui data

Seluruh data ada di `data.json`. Untuk memperbarui kondisi aset, cukup ganti
berkas tersebut (struktur sama) lalu commit — situs otomatis menampilkan data baru.
Tidak perlu menyentuh `index.html`.

Struktur tiap item:

```json
{
  "nama": "Loud Speaker",
  "spesifikasi": "Audio Meeting, Merk DAT DT 1516, 15 inci",
  "serial": "AI-0522ZT1516",
  "kode": "INA/OE.NB/380-DAT.1/RC#1/2022",
  "kelompok": "Perlengkapan Kantor (OE)",
  "jumlah": "1", "satuan": "unit",
  "kondisi": { "Y1 (Jun22-Mei23)": "Baik", "Y3 (Jun24-Mei25)": "Rusak", ... },
  "kondisi_terkini": "Rusak",
  "lokasi": "Nanga Betung",
  "penanggung_jawab": "LPHD",
  "pemasok": "Kelly Denzel Shop",
  "garansi": "-"
}
```

---
Data bersumber dari berkas pemantauan aset LPHD tahun Y1–Y3.
