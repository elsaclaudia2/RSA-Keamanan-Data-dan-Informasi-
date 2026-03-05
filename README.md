# Simple RSA Encryption Program (Python)

## Deskripsi
Program ini merupakan implementasi sederhana dari algoritma kriptografi **RSA (Rivest–Shamir–Adleman)** menggunakan bahasa Python. RSA adalah algoritma kriptografi asimetris yang menggunakan dua kunci berbeda, yaitu **public key** untuk enkripsi dan **private key** untuk dekripsi.

Program ini dibuat untuk memahami konsep dasar algoritma RSA, mulai dari pembuatan kunci hingga proses enkripsi dan dekripsi pesan.

---

# Fitur Program
Program ini memiliki beberapa fitur utama:

- Generate bilangan prima secara acak
- Membuat pasangan **public key** dan **private key**
- Melakukan proses **enkripsi pesan**
- Melakukan proses **dekripsi pesan**
- Menampilkan hasil perhitungan RSA

---

# Cara Menjalankan Program

## 1. Clone Repository

Clone repository ini ke komputer Anda.

```
git clone https://github.com/username/nama-repository.git
```

## 2. Masuk ke Folder Project

```
cd nama-repository
```

## 3. Jalankan Program

```
python rsa.py
```

---

# Langkah-langkah Algoritma RSA

## 1. Generate Bilangan Prima

Program akan menghasilkan dua bilangan prima secara acak yaitu:

- p
- q

Bilangan ini dipilih dari rentang tertentu dan dicek menggunakan fungsi pengecekan bilangan prima.

Contoh:

```
p = 107
q = 193
```

---

## 2. Menghitung Nilai n

Nilai **n** dihitung dengan mengalikan dua bilangan prima.

```
n = p × q
```

Contoh:

```
n = 107 × 193
n = 20651
```

Nilai **n** akan digunakan pada public key dan private key.

---

## 3. Menghitung Nilai φ(n)

Nilai φ(n) dihitung menggunakan rumus:

```
φ(n) = (p - 1)(q - 1)
```

Contoh:

```
φ(n) = (107 - 1)(193 - 1)
φ(n) = 106 × 192
φ(n) = 20352
```

Nilai ini digunakan untuk menentukan nilai private key.

---

## 4. Menentukan Nilai e (Public Exponent)

Program memilih nilai **e** yang relatif prima dengan φ(n).

Artinya:

```
gcd(e, φ(n)) = 1
```

Contoh nilai yang didapat:

```
e = 5
```

Nilai ini digunakan sebagai **public key**.

---

## 5. Menghitung Nilai d (Private Key)

Nilai **d** dihitung menggunakan **modular inverse** dari e terhadap φ(n).

```
d = e⁻¹ mod φ(n)
```

Contoh hasil:

```
d = 8141
```

Nilai ini digunakan sebagai **private key**.

---

# Key yang Dihasilkan

Public Key:

```
(e, n)
```

Contoh:

```
(5, 20651)
```

Private Key:

```
(d, n)
```

Contoh:

```
(8141, 20651)
```

---

# Proses Enkripsi

Pesan asli disebut **plaintext**.

Contoh:

```
M = 25
```

Rumus enkripsi RSA:

```
C = M^e mod n
```

Contoh hasil:

```
C = 18353
```

Nilai ini disebut **ciphertext**, yaitu pesan yang sudah terenkripsi.

---

# Proses Dekripsi

Ciphertext akan dikembalikan menjadi plaintext menggunakan private key.

Rumus:

```
M = C^d mod n
```

Contoh hasil:

```
M = 25
```

Pesan berhasil kembali ke nilai semula.

---

# Contoh Output Program

```
=== KEY GENERATION ===
p = 107
q = 193
n = 20651
phi(n) = 20352
Public Key (e, n) = (5, 20651)
Private Key (d, n) = (8141, 20651)

=== ENKRIPSI & DEKRIPSI ===
Plaintext : 25
Ciphertext: 18353
Decrypted : 25
```

---

# Struktur Program

Program terdiri dari beberapa fungsi utama:

- Fungsi untuk mengecek bilangan prima
- Fungsi untuk menghasilkan bilangan prima
- Fungsi Extended Euclidean Algorithm
- Fungsi Modular Inverse
- Proses pembuatan kunci RSA
- Proses enkripsi
- Proses dekripsi

---

# Kesimpulan

Program ini berhasil mengimplementasikan algoritma RSA sederhana dengan langkah-langkah:

1. Generate bilangan prima p dan q
2. Menghitung nilai n dan φ(n)
3. Menentukan public key
4. Menghitung private key
5. Melakukan proses enkripsi
6. Melakukan proses dekripsi

Hasil dekripsi yang sama dengan plaintext menunjukkan bahwa algoritma RSA berjalan dengan benar.

---

# Catatan

Program ini hanya menggunakan bilangan prima kecil sehingga hanya cocok untuk tujuan pembelajaran. Dalam implementasi nyata, RSA menggunakan bilangan prima yang sangat besar agar lebih aman.
