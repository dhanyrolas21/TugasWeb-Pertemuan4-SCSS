# Konversi CSS ke SCSS — Portofolio Dhany Rolas

Konversi `style.css` dari **Tugas Pertemuan 2 (Dashboard/Portofolio)** ke SCSS dengan struktur modular **7-1 pattern**, sebagai bagian dari **Tugas Rutin 4**, mata kuliah Pemrograman Web, Universitas Negeri Medan (UNIMED).

## Struktur Folder (7-1 Pattern)

```text
├── index.html                # Menghubungkan scss/main.scss via Vite
├── scss/
│   ├── abstracts/            # Variabel & mixin (tidak menghasilkan CSS langsung)
│   │   ├── _variables.scss   # Warna (light/dark), spacing scale, font, breakpoint
│   │   └── _mixins.scss      # Reusable mixins (flex, responsive, ring, dll.)
│   ├── base/                 # Aturan dasar/global
│   │   ├── _root.scss        # Custom property warna (via @each)
│   │   ├── _reset.scss       # Box-sizing, reset margin/padding
│   │   └── _typography.scss  # Heading, link, focus-visible
│   ├── layout/               # Struktur besar halaman
│   │   ├── _header.scss
│   │   ├── _grid.scss        # .layout-container, .main-content
│   │   ├── _sidebar.scss     # Aside
│   │   └── _footer.scss
│   ├── components/           # Potongan UI yang bisa dipakai ulang
│   │   ├── _navigation.scss
│   │   ├── _cards.scss       # Card-box, card-title, profil
│   │   ├── _project-list.scss
│   │   ├── _forms.scss
│   │   └── _buttons.scss
│   ├── pages/                # Penyesuaian spesifik satu halaman
│   │   └── _portfolio.scss
│   ├── themes/               # Override tema
│   │   └── _dark.scss        # Dark mode (via @each)
│   ├── vendors/              # Resource pihak ketiga
│   │   └── _fonts.scss
│   └── main.scss             # Entry point, menyatukan semua partial
├── dist/
│   └── style.css             # Hasil kompilasi CSS (expanded)
├── package.json              # Script dev (Vite) & build (Dart Sass)
└── README.md

No	Requirement	Implementasi
1	Konversi CSS existing ke SCSS	Seluruh isi style.css dari Tugas Pertemuan 2 dipecah ke 16 partials SCSS secara modular.
2	Variables untuk colors & spacing	Menyiapkan SASS Maps ($colors-light, $colors-dark) serta variabel font/spacing di abstracts/_variables.scss.
3	Nesting (maks 3 level)	Terstruktur rapi dan nesting dijaga ≤ 3 level di seluruh partials SCSS.
4	Minimal 3 mixin reusable	Memiliki berbagai mixin reusable di abstracts/_mixins.scss (seperti flex, respond-min, respond-max, focus-ring, dll.).
5	Struktur 7-1 pattern (partials)	Terbagi lengkap dalam 7 folder (abstracts, base, layout, components, pages, themes, vendors) dan disatukan di main.scss.
6	Gunakan @use (bukan @import)	Seluruh modul dan partials diimpor menggunakan sintaks @use.
7	Minimal 1 @each atau @for	Menggunakan fungsi @each untuk melakukan iterasi peta warna ($colors-light & $colors-dark) pada _root.scss dan _dark.scss.
8	Compile dengan Vite / Dart SASS	Dikompilasi menggunakan Vite untuk live server pengembangan dan Dart SASS (npm run build:css) untuk menghasilkan file fisik dist/style.css.


Dhany Rolas
Mahasiswa Ilmu Komputer, Universitas Negeri Medan