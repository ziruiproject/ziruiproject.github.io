---
title: "Tugas Praktikum 4"
description: 
date: 2025-04-15T14:31:24Z
image: cover.png
math: 
license: false
hidden: true
comments: true
draft: true
categories:
    - Teaching
tags: 
    - Java
    - Algorithm
---

## 💡 Petunjuk Umum

- Kerjakan menggunakan bahasa pemrograman Java
- Tambahkan komentar untuk menjelaskan program
- Tulislah kode dengan rapi
- Program harus memenuhi Kriteria Penyelesaian
- Jika pakai AI (ChatGPT, Deepseek, dll), nilai 0

## 📘 Istilah Umum

## Soal 1

### Perintah

Buat program yang menerima input nama, umur, dan IPK dari pengguna. Validasi bahwa umur dan IPK harus berupa angka, serta IPK harus berada pada rentang 0.0 - 4.0. Gunakan exception handling untuk menangani input yang tidak valid. Jika data valid, simpan ke dalam array.

### Kriteria Penyelesaian

1. Gunakan try-catch
2. Tangani kesalahan input non-numerik
3. Tangani IPK di luar rentang dengan custom exception
4. Gunakan finally untuk menampilkan pesan bahwa program sudah selesai
5. Data yang valid disimpan dalam array
6. Tampilkan semua data yang berhasil disimpan setelah proses input selesai
7. Array bisa menyimpan sampai 10 data
8. Program terus menerima input sampai 10 data terpenuhi

### Output yang Diharapkan

```txt
Masukkan nama: Andi
Masukkan umur: 20
Masukkan IPK: 3.5
Data berhasil disimpan.

Masukkan nama: Budi
Masukkan umur: 19
Masukkan IPK: 4.5
Error: Nilai IPK harus berada di antara 0.0 hingga 4.0!

Masukkan nama: Cecep
Masukkan umur: Sembilan Belas
Masukkan IPK: 4.0
Error: Umur harus berupa bilangan bulat!
```

## Soal 2

### Perintah

Buat program yang menerima input sebuah indeks kemudian program akan menampilkan elemen pada array. Jika indeks yang dimasukkan tidak ada dalam array, program harus menangani ArrayIndexOutOfBoundsException.

### Kriteria Penyelesaian

1. Gunakan array untuk menyimpan data (misalnya kumpulan nama orang)
2. Gunakan try-catch untuk menangani kasus indeks yang tidak valid tanpa memeriksa terlebih dahulu apakah indeks valid.
