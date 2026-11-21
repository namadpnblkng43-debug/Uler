# ⛏ Ular Tangga Minecraft — Multiplayer Online

Game ular tangga bertema Minecraft untuk 2-5 pemain (satu layar atau online, tiap pemain pakai HP sendiri).
Main online di: https://botgt0013-del.github.io/B/

## Fitur
- **Multiplayer online** (Supabase Realtime) + chat teks & suara.
- **Nama pemain custom**: sebelum game mulai, Pemain 1, 2, 3, ... mengetik namanya (maks 12 huruf). Di multiplayer, tiap pemain mengetik namanya di HP masing-masing.
- **Bank soal** dari satu file `bank-soal.json` (6 mapel x 4 jenjang x 3 tingkat).
- **Event bertingkat**: Common, Uncommon, Rare, **Heavenly**, Doom, Calamity. Event buruk dibuat lebih jarang dan lebih ringan.
- **Voting kartu event tiap 10 giliran**: semua pemain memilih kartu Doom / Calamity / Heavenly dalam 10 detik, suara terbanyak menentukan event.

### Event Heavenly
Kenaikan Agung (semua naik 50 kotak, mendarat di Creeper tetap jatuh), **Meet The Creator** (bertemu Seraphim, mati seketika, lalu dapat 3 skill OP), Cahaya Penyembuh, Malaikat Pelindung, Berkah Sang Raja.

### Event Calamity
**Devil's Contract** (tanda tangani kontrak: nyawa tersisa 1 dengan anugerah acak, atau tolak: nyawa -5), Ender Dragon Mengamuk, Warden Muncul.

## Bank soal (`bank-soal.json`)
Satu-satunya sumber soal. Taruh di folder yang sama dengan `index.html`. Format:
```json
{ "MTK": { "SD": [ { "lv": "easy", "q": "Pertanyaan?", "a": "Benar", "w": ["Salah 1", "Salah 2", "Salah 3"] } ], "SMP": [], "SMA": [], "PhD": [] },
  "IPA": {}, "IPS": {}, "PPKN": {}, "AJW": {}, "ENG": {} }
```
`lv` = `easy` / `mid` / `hard`. Soal dipilih acak tanpa pengulangan. Jika membuka file langsung (file://), pakai tombol **PILIH FILE .json**. Di multiplayer, bank yang dipakai milik host.

## Waktu kuis
Normal: mudah 20 / sedang 40 / sulit 60 detik. Waktu habis = salah.

## 🔥 Hard Mode
Tombol di menu utama (dan di panel host multiplayer): HP 7, waktu kuis 10 / 20 / 35 detik, tidak mengocok dadu dalam 10 detik = beku 1 giliran, peluang Doom + Calamity +15 poin persen (total 21%, rasio 2:1).

## 🌈 Item Legendary
TDR-3000, Void Axe, Excalibur, Totem Keabadian, Lubang Hitam, Napas Ender, Cawan Suci. Jatuh dari kuis sedang (4%) / sulit (8%). Di Mode Simulasi: panel 🧪 > "Beri Item" untuk memberi item dari semua kategori.

## Skin
14 karakter, masing-masing punya skill bawaan. Baru: Jester (Mimicry: meniru skill bawaan terakhir lawan), Ninja, Vampir, Astronot, Tabib, Bajak Laut.

## Deploy ke GitHub Pages
Push ke branch `main`; workflow `.github/workflows/pages.yml` akan publish otomatis.
(Settings → Pages → Source: **GitHub Actions**.)

## Supabase sendiri (disarankan)
Ganti `url` dan `key` pada `window.MP_CONFIG` di `index.html` dengan project Supabase kamu (tanpa tabel; cukup fitur Broadcast).

## Struktur
```
index.html
bank-soal.json   # bank soal
.github/workflows/pages.yml
```

Lisensi: MIT
