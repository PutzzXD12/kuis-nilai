Kuis Sekolah - GitHub-connected
=================================

Isi file:
- index.html  -> buka langsung di browser atau upload ke GitHub Pages
- data_nilai.json -> contoh file (jika belum ada di repo, script bisa membuatnya saat pertama push)
- README.txt  -> instruksi

Ringkasan cara kerja (GitHub-connected):
- Untuk menyimpan leaderboard di repo GitHub, pengguna harus mengisi konfigurasi GitHub:
  - owner (username GitHub)
  - repo (nama repo)
  - path (path file JSON, misal 'data_nilai.json' atau 'kuis/data_nilai.json')
  - Personal Access Token (PAT) dengan scope `public_repo` (atau `repo` jika repo privat)
- Setelah konfigurasi dimasukkan, saat pemain mengirim jawaban, aplikasi mencoba:
  1. Ambil (GET) isi file JSON via GitHub API untuk mengetahui `sha` dan isi saat ini.
  2. Tambahkan entry skor (nama, score, date) ke JSON dan `PUT` kembali file tersebut.
- Jika file belum ada, script akan membuat file baru dalam commit pertama.
- Jika token tidak diisi, aplikasi hanya menyimpan di LocalStorage (lokal).

Catatan penting keamanan:
- PAT adalah sensitif — simpan hanya di perangkat yang kamu percayai.
- Aplikasi menyimpan PAT hanya di sessionStorage (hanya sesi browser saat ini), bukan di localStorage permanent.
- Jangan commit token ke repo GitHub.

Cara deploy ke GitHub Pages:
1. Buat repo baru (misal: Kuis-Nilai) di akun GitHub kamu.
2. Upload file `index.html` dan `README.txt` ke repo.
3. (Opsional) buat file `data_nilai.json` dengan konten awal `[]` atau biarkan script membuatnya saat push pertama.
4. Aktifkan GitHub Pages dari branch `main` untuk folder root.
5. Buka URL GitHub Pages dan isi konfigurasi GitHub lalu mainkan kuis.

Contoh `data_nilai.json` awal:
[]

Butuh bantu upload file ke repo atau cara bikin PAT Github? Aku bisa pandu langkah demi langkah.
