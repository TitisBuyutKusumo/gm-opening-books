# GM Opening Books

Polyglot chess opening books built from real super-GM games. Point your engine at one and it opens like them.

- **magnus.bin** (7 MB, 444.067 posisi) — Magnus Carlsen
- **hikaru.bin** (45 MB, 2.916.754 posisi) — Hikaru Nakamura

## Datanya dari mana

Semua game diambil dari chess.com published API (`api.chess.com/pub/player/.../games/...`), bulan per bulan sampai September 2026:

- Magnus: 9.454 game standar (Des 2014 – Sep 2026). Sisanya varian/chess960 dibuang.
- Hikaru: 68.349 game standar (Jan 2014 – Sep 2026). Dia main ~7x lebih banyak dari Magnus, makanya file-nya gede.

Semua kontrol waktu masuk (rapid, blitz, bullet). Rating lawan ga difilter — ini repertoire apa adanya, bukan kurasi "cuma lawan kuat".

## Cara bikinnya

Per posisi dicatat: Magnus/Hikaru main apa, berapa kali. Bobot = frekuensi — makin sering dimainin, makin sering kepilih engine. Standard chess doang, max 60 ply (opening + awal middlegame), rokade encoding KxR standar, file sorted biar binary-search aman.

## Kok magnus.bin kecil?

Bukan error. Tiga sebab: Magnus main jauh lebih dikit (9 ribu vs 68 ribu game), repertoire dia sempit (e4/d4 jalur utama, transposisi numpuk di posisi yang sama), dan max-ply 60 motong ekor middlegame. Kecil = padat, bukan rusak.

## Cara pakai

File `.bin` polyglot standar — engine atau GUI apa aja yang baca polyglot bisa pakai: Komodo, Rodent, Arena, Banksia, CuteChess, DroidFish (copy ke folder `DroidFish/book`), atau Stockfish via PolyGlot adapter. Di luar book, engine mikir sendiri kayak biasa.

## Buat apa

Biar engine bukaannya berasa kayak nonton Magnus/Hikaru main: Ruy Lopez + Berlin + Catalan + Sveshnikov ala Magnus, atau 1.e4 campur 1.b3 + Bongcloud ala Hikaru (iya, Ke2-nya masuk book). Buat seru-seruan lawan manusia. Buat turnamen engine-vs-engine ga nambah Elo — book ga gitu cara kerjanya.

## License

MIT — bebas dipakai. Lihat LICENSE.
