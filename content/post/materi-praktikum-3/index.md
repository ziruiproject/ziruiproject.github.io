---
title: "Materi Praktikum 3"
description: Membahas tentang Searching & Sorting
date: 2025-04-11T16:06:37Z
image: cover.png
math: 
license: false
hidden: false
comments: true
draft: false
categories: 
    - Teaching
tags:
    - Java
    - Algorithm
---

## Searching

Algoritma searching adalah langkah-langkah atau instruksi untuk mencari sesuatu, biasanya adalah elemen di dalam array. Algoritma ini dibagi menjadi dua jenis, yaitu Linear dan Binary.

Dalam materi ini, ranah yang dibahas adalah dalam mencari elemen di dalam suatu array.

### Linear Search

#### Pengertian

Linear Search adalah metode untuk mencari data dengan cara mengecek elemen satu per satu dari posisi awal hingga akhir, sampai menemukan elemen yang dicari.

#### Visualisasi

##### Secara Umum

{{< video src="LinearSearchScene.mp4" autoplay="false">}}

##### Jika Tidak Ketemu

{{< video src="LinearSearchNotFound.mp4" autoplay="false">}}

##### Jika Nilai Duplikat

{{< video src="LinearSearchDuplicate.mp4" autoplay="false">}}

#### Kode

```java
public static int linearSearch(int[] array, int target) {
    for (int i =  ͏0; i < array.length; i++) {
        if (array[i] == target) {
            return i;
        }
    }
    return -1;
}
```

#### Penjelasan Kode

##### Parameter

```java
public static int linearSearch(int[] array, int target)
```

Method `linearSearch` akan menerima dua nilai, yaitu `array` dan `target`. Parameter `array` adalah data yang akan diproses (kotak-kotak dalam visualisasi sebelumnya). Kemudian `target` adalah nilai yang mau dicari.

##### Perulangan

```java
for (int i =  ͏0; i < array.length; i++) {

}
```

Bagian ini akan mengiterasi `array` yang kita masukan sebelumnya, dari awal hingga akhir. Dalam visualisasi, kamu bisa lihat ada **panah** diatas kotak yang selalu bergerak. Itu dia wujud dari perulangan ini.

##### If Statement

```java
if (array[i] == target) {

}
```

Bagian ini akan `mengecek` apakah nilai array sekarang sama dengan target yang dicari.

Jika tidak sama, maka program akan lanjut ke elemen / nilai selanjutnya. Kamu bisa lihat di visualisasi saat tanda panah berpindah ke kotak lain.

##### Return Pertama

```java
if (array[i] == target) {
    return i;
}
```

Jika ternyata nilainya sama, artinya target yang dicari telah ditemukan di dalam array. Maka, program akan mengembalikan nilai `index` atau posisi target tersebut ada di mana.

##### Return Kedua

```java
return -1;
```

Jika semua nilai array sudah dicek sampai habis dan tidak ada nilai yang sama dengan target, maka program akan mengembalikan `-1`.

`-1` dipilih karena tidak ada array yang ber-index negatif.
