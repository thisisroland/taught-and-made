# Stay Creative. Stay Connected.

A single-page archive of 15 student projects with exhibition documentation.

Build notes only. Nothing here identifies the author on purpose: this file is
rendered on the repository's own page on github.com, which Google indexes and
which the site's robots.txt has no control over.

The Visual Making Project gallery mixes photographs with short looping clips.
Long workbooks open from a collage: click it to expand every page.

---

## Publish on GitHub Pages

This folder is a complete static website. Nothing needs to be built or compiled.

### The easy way — GitHub Desktop (recommended)

The site has about 1,290 files, which is more than the GitHub website lets you
drag-and-drop in one go. GitHub Desktop handles it in one step.

1. Create a new repository on github.com — for example `portfolio`. Make it **Public**.
2. Install **GitHub Desktop** (desktop.github.com) and sign in.
3. *File → Clone repository* and clone the repository you just made.
4. Copy **everything inside this folder** into the cloned folder:
   `index.html`, `img/`, `vid/`, `.nojekyll`, `robots.txt`, `README.md`.
5. In GitHub Desktop: write a summary such as "add portfolio", press
   **Commit to main**, then **Push origin**.
6. On github.com open the repository → **Settings → Pages**.
   Set **Source = Deploy from a branch**, **Branch = main**, **Folder = / (root)**, Save.
7. Wait a minute. The site is live at
   `https://<your-username>.github.io/<repository-name>/`

### Command line

```bash
cd <this folder>
git init
git add .
git commit -m "add portfolio"
git branch -M main
git remote add origin https://github.com/<your-username>/<repository-name>.git
git push -u origin main
```

Then do step 6 above.

---

## What is in here

| Path | What it is |
|---|---|
| `index.html` | The whole site. All CSS and JavaScript are inside this one file. |
| `img/` | Project images. `name.jpg` is full size, `name_t.jpg` is the small version used in the grids. |
| `vid/` | Videos hosted here rather than on YouTube. |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are. Keep it. |
| `robots.txt` | Crawler rules. Keep it. |

### Keeping the site out of search engines

`index.html` carries `noindex` instructions for Google, Bing, DuckDuckGo,
Yandex and Baidu, so the site should never appear in their results. This works
wherever the site is published.

`robots.txt` additionally shuts out AI training crawlers and archive bots. Note
that crawlers only read `robots.txt` at the root of a domain. If the repository
is named `<your-username>.github.io` the file is read; if the repository has any
other name, the site sits in a subfolder and the file is ignored. The `noindex`
tags in `index.html` still apply either way.

None of this makes the site private. Anyone with the link can open it, and the
repository itself is public, so its files can be browsed on github.com. For a
portfolio sent directly to recruiters that is usually fine. If it is not, host
the folder on Netlify or Cloudflare Pages instead — both deploy from a private
repository, and Netlify can put a password on the site.

### The five YouTube films

These are embedded and **not** stored in the repository. To change one, search
`index.html` for `data-yt` and replace the video ID.

| Project | Video ID |
|---|---|
| 03 Angelpod | `wG1jdVbG0BQ` |
| 04 321 Scope | `MxO4LbuEYeg` |
| 09 Pasola Festival — Website | `eUlpBRPsnl0` |
| 13 Nightosphere | `EMSape23JVo` |
| 14 History of Bakmi | `wONYBFR9cMw` |

### The two flipbooks

- *08 Pasola Festival* reads pages from `img/bk01.jpg` to `img/bk50.jpg` (two-page spreads).
- *10 Cow Play Cow Moo* reads pages from `img/cg01.jpg` to `img/cg88.jpg` (single pages).

Both open directly on the page. The **Fullscreen** button opens a larger viewer.

---

## Making changes later

- Replace a photo: drop a new file into `img/` with exactly the same name.
  Remember to replace both `name.jpg` and `name_t.jpg`.
- Change wording: edit `index.html` in any text editor.

GitHub Pages rebuilds a minute or two after each push.

## Perubahan versi ini (21 Nov 2026)

Tujuannya satu: situs ini dan web personal harus terasa satu sistem.

- **Gutter, kolom, header, footer disamakan angka per angka** dengan web
  personal: `--pad: clamp(1.25rem, 4vw, 3.5rem)` (20-56px), kolom 1320px,
  padding nav `max(.95rem, safe-area) var(--pad) .95rem`, padding footer
  `clamp(64px,12vh,120px) 0 max(36px, safe-area)`, gap footer 34px, kolom
  footer 1.2fr/1fr, judul footer `clamp(28px,4.6vw,56px)`.
- **Menu bar hitam** dengan teks cream, menetap di seluruh halaman.
- **Transisi hitam ke paper.** Sampul menyerahkan warnanya ke `<body>` begitu
  selesai membuka, lalu tiap pergantian ground jadi satu fade 0.9 detik. Itu
  yang bikin perpindahan dari layar pembuka ke "About this archive" terbaca
  larut, bukan terpotong. Mekanismenya sama dengan web personal.
- **Plat warna di tiap judul proyek dihapus.** Lima belas warna di antara lima
  belas palet karya mahasiswa terbaca ramai; kepala bagian kembali ke paper.
- **Baris peran disamakan**: "Designer, Artist & Educator" plus blok Assistant
  Professor and Enrichment Program Coordinator.
- **Tombol Download CV** jadi pil cream solid berteks gelap, didorong ke ujung
  kanan baris kontak (`margin-left:auto`), membalik jadi transparan saat
  hover, panahnya turun 3px. Persis web personal.
- **Tanda scroll** dipasang ke viewport, bukan ke dasar hero. Di web personal
  hero-nya lebih tinggi daripada layar laptop, jadi tanda scroll-nya jatuh di
  bawah lipatan dan tidak pernah terlihat. Di sini ritme vertikal hero
  dirapatkan supaya muat 100svh dari 768px ke atas, tanda scroll-nya menyala
  di bawah ticker, dan pada jendela yang terlalu pendek untuk memuat hero
  tanda itu mundur sendiri (`.noroom`) karena di situ halaman sudah jelas
  melimpah dan tanda itu hanya akan menumpuk ticker.
- **Footer** menutup dengan baris "Personal portfolio" ke
  `thisisroland.github.io/woven-ahead/`, berpasangan dengan baris "Teaching
  portfolio" di footer web personal.
- **Font tidak dari Google.** Archivo dan Newsreader di-host dari `fonts/`.

### Perbaikan 22 Nov 2026

- **Baris copyright footer** sebelumnya 16px, bukan 10.5px. Penyebabnya
  selektor: `.foot p` itu class+element, `.foot-copy` cuma class, jadi
  `.foot p` menang. Diperbaiki jadi `.foot p.foot-copy`.
- **Tombol kembali ke atas** sebelumnya cream di atas halaman cream, jadi
  nyaris tak terlihat di atas karya. Sekarang dia mengambil kebalikan dari
  ground yang sedang dilewatinya: ink di atas karya, cream di atas layar
  pembuka dan footer.
- **Tanda scroll muncul di jendela pendek.** Sebelumnya tanda itu mundur
  (`.noroom`) begitu hero tidak muat, dan di jendela laptop dengan banyak tab
  hero memang tidak muat, jadi tandanya tidak pernah kelihatan. Sekarang
  urutannya dibalik: yang mundur duluan ticker disiplin (dekorasi), lalu
  eyebrow, baru tanda scroll. Hasilnya hero muat 100svh dari 640px ke atas
  dan tandanya selalu ada.
- **Judul tab** jadi `Roland Ananda · Taught & Made`, memakai middle dot (·)
  seperti web personal, jadi titiknya duduk di tengah tinggi huruf.

### Perbaikan 22 Nov 2026 (kedua)

- **Tanda scroll kembali muncul** saat naik lagi ke layar pembuka. Sebelumnya
  kelasnya di-`add` dan tidak pernah di-`remove`, jadi sekali hilang ya hilang.
  Sekarang di-`toggle` terhadap posisi scroll.
- **Scrim di belakang tanda scroll dihapus.** Debunya sekarang lewat bebas,
  sama seperti web personal. Kemarin saya pasang gradien gelap supaya tanda
  itu terbaca di atas ticker; cara itu salah, yang benar memberi dia ruang.
- **Ukuran hero disamakan angka per angka** dengan web personal: nama
  `clamp(48px,10.4vw,140px)` (sebelumnya dibatasi 128px), leading .9,
  tracking -.045em, padding hero `clamp(110px,16vh,170px)`, margin eyebrow,
  role, statement, kontak dan ticker semuanya kembali ke nilai web personal.
  Pada jendela 1360x1000 koordinat nama, eyebrow, kontak dan foto identik.
- **Ruang untuk tanda scroll dicari dengan mengukur, bukan menebak.** Dulu
  patokannya tinggi hero versus tinggi jendela; itu kasar, karena padding
  bawah hero dalam, jadi hero bisa lebih tinggi dari jendela dan tanda
  scroll tetap duduk di ruang kosong. Sekarang yang diukur tumpangan
  sebenarnya antara elemen terbawah hero dan tanda scroll. Kalau bertumpuk:
  ticker mundur dulu, lalu padding atas merapat, dan hanya di layar HP
  terkecil tanda scroll mundur. Pengukuran diulang setelah webfont turun,
  karena mengukur dengan metrik font cadangan sempat menyembunyikan tanda
  itu secara permanen.

### Perbaikan 22 Nov 2026 (ketiga)

- **Menu bar tidak lagi memblokir debu di layar pembuka.** Sebelumnya `.top`
  diberi `background: var(--black)` permanen, jadi di atas hero dia jadi pita
  hitam yang memotong canvas dan debunya tidak bisa lewat. Sekarang bar-nya
  transparan di atas sampul, persis seperti nav web personal, dan baru
  mengambil ground (hitam 88% dengan blur) setelah di-scroll lewat 40px —
  ambang yang sama dengan web personal.

### Perbaikan 22 Nov 2026 (keempat)

- **Tombol panah ke atas sekarang membaca apa yang benar-benar ada di
  bawahnya**, bukan ground halaman. Ground berganti saat sebuah bagian
  melewati tengah layar, sedangkan tombolnya duduk di pojok bawah, jadi
  sepanjang layar pertama footer keduanya berbeda pendapat dan tombol ink
  mendarat di atas hitam. Sekarang titik tengah tombol diuji terhadap kotak
  hero dan footer, lalu warnanya dibalik. Diuji di tiga posisi: di atas
  karya ink, baru masuk footer cream, dasar footer cream.
- **Tombol "or jump to any of the 15"** dulu cuma garis rambut di atas paper
  sehingga tidak terbaca sebagai tombol. Sekarang pil ink pekat berteks
  cream, membalik jadi garis saat hover.

## Audit final, 22 Nov 2026

Empat pemeriksaan, semuanya dijalankan di browser sungguhan lewat HTTP
(`python3 -m http.server`), bukan `file://` — karena `file://` memblokir
webfont lewat CORS dan menyembunyikan error yang sebenarnya.

**Tombol — 23/23, nol error JavaScript.** Setiap kontrol diklik dengan mouse
sungguhan, bukan `element.click()` dari JavaScript, karena cara itu melewati
`pointer-events` dan pernah meloloskan tombol play yang sebenarnya mati di
proyek ini. Tercakup: INDEX dan 15 isinya, chip nomor bagian, Escape, salin
e-mail, 5 tombol play lingkaran merah, buka dan tutup galeri, lightbox
beserta panah kiri-kanannya, 2 flipbook, 15 tombol jump, 14 tautan proyek
berikutnya, kembali ke atas, dan 31 anchor internal.

**Mesin pencari — 42/42.** Meta robots `noindex, nofollow, noarchive,
nosnippet, noimageindex, nocache, notranslate` plus varian Googlebot dan
Bingbot; `referrer: no-referrer`; 32 grup di robots.txt dengan 25 di
antaranya `Disallow: /` penuh, termasuk Meta-ExternalAgent,
Meta-ExternalFetcher, FacebookBot, facebookexternalhit, GPTBot, ClaudeBot,
Google-Extended, PerplexityBot, CCBot, Bytespider, Applebot-Extended,
archive.org_bot. Googlebot dan kawan-kawan sengaja diizinkan merayap supaya
bisa membaca tag noindex-nya, tapi PDF-nya diblokir per path. Tidak ada
direktif Sitemap, tidak ada analytics, tidak ada permintaan pihak ketiga,
nol iframe di HTML yang dikirim (pemutar video baru dimuat saat diklik).

**Konten — 31/31.** 1.270 aset dirujuk, nol hilang, nol kegagalan jaringan.
15 proyek tampil lengkap dan berurutan. Tidak ada galeri terpotong. Nol
gambar menganggur: 32 berkas sisa build lama (2,27 MB) dikeluarkan setelah
dipastikan tidak dirujuk, termasuk lewat atribut `data-pages` milik flipbook
yang sempat luput dari pemeriksaan pertama.

**Responsif — 14/14 perangkat bersih.** iPhone SE sampai Full HD, potret dan
lanskap, iPad mini sampai iPad Pro. Nol overflow horizontal di mana pun, menu
bar tidak pernah terpotong, webfont termuat di semua ukuran. Area sentuh di
perangkat touch dibesarkan lewat overlay transparan (bukan padding, supaya
tampilannya tidak berubah): INDEX dan Copy yang tadinya 23px, chip nomor
bagian 17px, dan tautan di baris kontak dan footer. Lebarnya dijaga lebih
kecil daripada jarak antar tetangga, lalu diuji dengan `elementFromPoint`
untuk memastikan tidak ada overlay yang mencuri sentuhan milik tautan lain.
