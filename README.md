# 🔍 Crackme Solutions

Solusi dan writeup proses analisis untuk crackme dari [crackmes.one](https://crackmes.one), dikerjakan sebagai bagian dari pembelajaran Reverse Engineering mata kuliah Keamanan Siber selama satu semester. Setiap crackme dikerjakan secara mandiri dan writeup ditulis berdasarkan proses analisis saya sendiri — fokus pada bagaimana cara berpikir saat menganalisis, bukan sekadar jawaban akhirnya.

**Penulis:** [Nama Lengkap] — [NIM]

## ⚠️ Disclaimer
Repo ini dibuat untuk tujuan edukasi mata kuliah Keamanan Siber. Crackme yang dikerjakan berasal dari crackmes.one, platform yang memang menyediakan binary untuk latihan RE secara legal. Tidak ada software berhak cipta pihak ketiga atau malware aktif di repo ini.

## 🗂 Struktur

```
crackme-solutions/
├── README.md
├── crackme-01/
│   ├── README.md
│   └── screenshots/
├── crackme-02/
│   ├── README.md
│   └── screenshots/
└── crackme-03/
    ├── README.md
    └── screenshots/
```

## 📋 Daftar Crackme

| Nama | Sumber | Level | Tools | Status |
|------|--------|-------|-------|--------|
| _(isi)_ | [link crackmes.one](#) | Easy | Ghidra | WIP |
| _(isi)_ | [link crackmes.one](#) | Easy/Medium | x64dbg | WIP |
| _(isi)_ | [link crackmes.one](#) | Medium | Ghidra + x64dbg | WIP |

> Update status menjadi **Selesai** setelah writeup lengkap dan sudah di-commit.

## ✍️ Format Writeup
Setiap folder `crackme-0X/` punya `README.md` sendiri (lihat [template](crackme-01/README.md) sebagai contoh struktur), berisi:
- Link sumber crackme
- Tools yang dipakai
- Langkah-langkah analisis (proses berpikir, termasuk yang gagal/buntu)
- Minimal 1 screenshot Ghidra/x64dbg yang dianotasi (panah/highlight menjelaskan bagian relevan)
- Solusi akhir & penjelasan kenapa berhasil

## 🛠 Tools
- Ghidra (static analysis / dekompilasi)
- x64dbg (dynamic analysis / debugging)
- Detect It Easy (DIE) untuk identifikasi packer/compiler

