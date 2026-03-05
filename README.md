Langkah 1: Menjalankan Program

Jalankan file utama:

python rc4_presentasi.py

atau:

python3 rc4_presentasi.py
🔑 Langkah 2: Mengatur Key dan Plaintext

Program ini menggunakan input key dan plaintext yang diset pada bagian main() di file rc4_presentasi.py.

Cari bagian ini:

key_str = "kunci-rahasia"
plaintext_str = "Halo RC4! Ini demo step-by-step."
✅ Aturan Key (Kunci)

RC4 adalah kriptografi simetris → kunci yang sama untuk enkripsi & dekripsi

Pada demo ini, key_str adalah string, lalu dikonversi ke bytes dengan UTF-8:

key = key_str.encode("utf-8")

Key tidak boleh kosong

Panjang key boleh bervariasi (program akan memakai key[i % key_length] pada tahap KSA)

Contoh Key:

kunci-rahasia

KUNCI123

passwordku

Contoh Plaintext:

Halo RC4!

Ini pesan rahasia

Belajar stream cipher

PENTING: Jika kamu mengubah key_str atau plaintext_str, jalankan ulang program untuk melihat hasil baru.

🔐 Langkah 3: Proses Enkripsi (Plaintext → Ciphertext)

Saat program berjalan, kamu akan melihat:

1) Output KSA (Key Scheduling Algorithm)

Menampilkan beberapa langkah awal proses pembentukan state S (0..255)

Ada rumus perubahan j dan proses swap S[i] ↔ S[j]

2) Output PRGA (Keystream Generation)

Menampilkan beberapa byte awal keystream K[t]

Ada informasi i, j, swap, dan output K (decimal & hex)

3) Output XOR (Enkripsi)

Menampilkan tabel per byte:

P[t] (Plaintext)

K[t] (Keystream)

C[t] (Ciphertext) = P[t] XOR K[t]

4) Ringkasan Hasil

Program akan mencetak:

Plaintext (utf-8 & hex)

Keystream (hex)

Ciphertext (hex)

📌 Salin nilai Ciphertext (hex) jika ingin dipakai sebagai bukti hasil enkripsi.

🔓 Langkah 4: Proses Dekripsi (Ciphertext → Plaintext)

Pada RC4, dekripsi dilakukan dengan cara yang sama:

Program mengulang KSA + PRGA menggunakan key yang sama

Lalu melakukan XOR:

Plaintext = Ciphertext XOR Keystream

Di akhir program akan muncul:

Recovered (utf-8) → plaintext hasil dekripsi

Validasi:

✅ Validasi OK: recovered == plaintext

🎥 Untuk Presentasi / Screen Record (Step-by-Step)

Kamu bisa mengatur seberapa banyak langkah yang ditampilkan agar sesuai durasi presentasi.

Di main(), ubah nilai berikut:

KSA_STEPS = 10     # jumlah langkah KSA yang ditampilkan
PRGA_STEPS = 12    # jumlah byte awal PRGA yang ditampilkan
XOR_STEPS = 24     # jumlah baris XOR yang ditampilkan

Rekomendasi cepat:

Presentasi singkat: 5, 8, 12

Presentasi detail: 10, 12, 24
