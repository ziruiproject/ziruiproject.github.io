---
title: "Tugas Pertemuan Ke 3"
description: "Membahas tentang algoritma sorting & searching"
date: 2025-04-10T11:04:59Z
image: cover.png
math: 
license: 
hidden: false
comments: true
draft: false
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

- **Elemen**: Nilai yang ada di dalam array. Contoh dalam array `{5, 4, 3}`, maka `5` saja adalah elemen, `4` saja adalah elemen, dan `3` saja adalah elemen
- **Target**: Nilai yang ingin dicari di dalam array

## Sorting Misterius 1

### **Perintah**

Buat program untuk mengurutkan array dengan cara mencari nilai terbesar atau terkecil, kemudian ditukar sampai array terurut secara Ascending.  

### **Kriteria Penyelesaian**

1. Program ditulis dalam method bernama

    ```java
    public static int[] SortingMisterius1(int[] arr)
    ```

2. Program harus menampilkan setiap iterasi yang terjadi
3. Program harus menampilkan jumlah iterasi dan pertukaran (swap) yang terjadi
4. Program harus menampilkan array sebelum diurutkan dan setelah diurutkan
5. Program bisa dipanggil di Main Method

## Sorting Misterius 2

### **Perintah**

Buat program untuk mengurutkan array dengan cara mengecek secara berpasangan setiap elemen di dalam array tersebut, kemudian ditukar sampai array terurut secara Descending.

### **Kriteria Penyelesaian**

1. Program ditulis dalam method bernama

    ```java
    public static int[] SortingMisterius2(int[] arr)
    ```

2. Program harus menampilkan setiap iterasi yang terjadi
3. Program harus menampilkan jumlah iterasi dan pertukaran (swap) yang terjadi
4. Program harus menampilkan array sebelum diurutkan dan setelah diurutkan
5. Program bisa dipanggil di Main Method

## Sorting Misterius 3

### **Perintah**

Buat program untuk mengurutkan array dengan cara membandingkan dengan elemen di sebelah kirinya, kemudian ditukar sampai array terurut secara Ascending.  

**Kriteria Penyelesaian**

1. Program ditulis dalam method bernama

    ```java
    public static int[] SortingMisterius3(int[] arr)
    ```

2. Program harus menampilkan setiap iterasi yang terjadi
3. Program harus menampilkan jumlah iterasi dan pertukaran (swap) yang terjadi
4. Program harus menampilkan array sebelum diurutkan dan setelah diurutkan
5. Program bisa dipanggil di Main Method

## Searching Misterius 1

### **Perintah**

Buat program untuk mencari elemen dalam array dengan cara mengambil elemen di tengah, lalu membagi array menjadi dua bagian secara terus menerus hingga menemukan elemen yang dicari atau sampai tidak ditemukan.

### **Kriteria Penyelesaian**

1. Program ditulis dalam method bernama

    ```java
    public static int[] SearchingMisterius(int[] arr, int target)
    ```

2. Program harus dapat mencari elemen meskipun array tidak terurut
3. Program harus menampilkan array yang sedang diproses di setiap iterasi  
4. Program harus menampilkan jumlah iterasi yang terjadi
5. Program harus menampilkan indeks elemen jika ditemukan, dan `-1` jika tidak ditemukan
6. Program bisa dipanggil di Main Method


## Searching Misterius 2

### **Perintah**

Buat program untuk mencari elemen dalam array dengan cara mencari elemen satu per satu dari index pertama hingga akhir sampai menemukan elemen yang dicari atau sampai tidak ditemukan.

### **Kriteria Penyelesaian**

1. Program ditulis dalam method bernama

    ```java
    public static int[] SearchingMisterius(double[] arr, double target)
    ```

2. Program harus dapat mencari elemen meskipun array tidak terurut
3. Program harus menampilkan pesan:
   - `"Elemen tidak sama dengan target"` saat elemen yang dicek bukan target
   - `"Elemen sama dengan target"` saat elemen yang dicek adalah target  
4. Program harus menampilkan jumlah iterasi yang terjadi
5. Program harus menampilkan indeks elemen jika ditemukan, dan `-1` jika tidak ditemukan
6. Program bisa dipanggil di Main Method

## 🗓️ Deadline

- Tugas ini harus dikumpulkan **paling lambat** pada:

  📅 **Hari/Tanggal**: 17 April 2025  
  ⏰ **Pukul**: 18:00 WIB

- Pengumpulan dilakukan melalui MyITS Classroom

⛔ **Catatan**: Tugas yang terlambat, hanya dapat nilai maksimal 50 saja.
