---
title: "Materi Praktikum 4"
description: Membahas tentang Exception Handling
date: 2025-04-14T06:13:17Z
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

![Image 1](qr.png)

## Error

### Pengertian

Error adalah kesalahan dalam program. Kesalahan ini dapat menyebabkan program tidak berjalan sebagaimana mestinya.

Ada beberapa jenis error yang perlu diketahui, yaitu:

### Syntax Error

#### Pengertian

Sebagaimana bahasa manusia, bahasa pemrograman juga memiliki tata bahasanya (grammar) sendiri. **Grammar** dalam bahasa pemrograman disebut **Syntax**. Jika kamu melanggar **Grammar** ini, maka program akan menampilkan error yang disebut **Syntax Error**.

#### Contoh

```java
// Contoh Syntax Error
string Nama = "Yudha";
int Usia = 17
```

Kode diatas mengandung Syntax Error. Error pertama yaitu pada baris pertama, kata `string` seharusnya ditulis `String`. Perhatikan bahwa perbedaan kapital saja berpengaruh pada Syntax Error.

Kemudian kesahalan selanjutnya ada pada baris kedua. Diujung baris, tidak diberi tanda `titik koma (;)`. Sehingga kode yang benar adalah

```java
String Nama = "Yudha";
int Usia = 17;
```

#### Penanganan

Syntax error mudah ditangani karena langsung terdeteksi oleh editor seperti NetBeans, VSCode, dan IntelliJ sebelum program di-running.

### Logical Error

#### Pengertian

Logical Error adalah kesalahan logika, biasanya akan menghasilkan output yang salah padahal tidak ada Error.

#### Contoh

```java
int luas = panjang + lebar; // Dijumlah
System.out.println(luas);
```

Pada kode di atas, progam tidak akan menampilkan error, namun akan mengeluarkan output yang salah. Hal itu terjadi karena ada kesalahan logika saat menghitung `luas`, seharusnya `luas` dihitung dengan rumus `panjang * lebar` bukan `panjang + lebar`.

Kode yang benar seharusnya

```java
int luas = panjang * lebar; // Dikali
System.out.println(luas);
```

#### Penanganan

Cara menangani Logical Error bisa dengan mengecek program langkah demi langkah, mencoba dengan input lain, dan yang terpenting adalah teliti dengan kode yang sudah ditulis.

### Runtime Error

#### Pengertian

Runtime Error adalah error yang terjadi saat program sedang berjalan. Biasa terjadi karena ada input yang tidak sesuai (misalnya memasukan huruf ke dalam integer), mengakses object yang null, atau mengakses array diluar index-nya.

#### Contoh

```java
import java.util.Scanner;

public class InputIntegerSimple {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.println("PROGRAM INPUT INTEGER SEDERHANA");
        System.out.println("-------------------------------");
        
        System.out.print("Masukkan sebuah bilangan bulat: ");
        int number = scanner.nextInt(); // Akan error jika input bukan integer
        
        System.out.println("\nHasil:");
        System.out.println("Anda memasukkan: " + number);
        System.out.println("Kuadratnya: " + (number * number));
        System.out.println("Bilangan ini adalah " + 
                         (number % 2 == 0 ? "genap" : "ganjil"));
        
        scanner.close();
    }
}
```

Program diatas akan mati (error) jika kamu meng-input string / huruf.

#### Penanganan

Fokus utama dalam menangani Runtime Error adalah **program tidak boleh mati.** Meskipun terjadi error, program harus mampu menangani error tersebut sehingga bisa tetap berjalan. Penanganan ini disebut **Exception Handling**.

## Exception

### Pengertian

Di Java, macam-macam kesalahan saat Runtime Error **yang masih bisa ditangani** direpresentasikan dengan istilah Exception.

### Jenis-Jenis

Ada banyak jenis Exception, contohnya sebagai berikut:

| **Exception**                   | **Kegunaan / Deskripsi**                                                               |
|----------------------------------|---------------------------------------------------------------------------------------|
| `Exception`                     | Merupakan kelas induk dari semua exception di Java. Menangani kesalahan umum yang terjadi di runtime. |
| `NullPointerException`          | Terjadi saat mencoba menggunakan objek yang bernilai `null`                           |
| `ArrayIndexOutOfBoundsException`| Index array diakses melebihi batas                                                   |
| `ArithmeticException`           | Kesalahan dalam operasi matematika, seperti pembagian dengan nol                    |
| `NumberFormatException`         | Gagal mengubah string ke angka karena format tidak valid                             |
| `IllegalArgumentException`      | Parameter tidak valid diberikan ke sebuah method                                    |
| `IOException`                   | Terjadi saat kesalahan input/output, seperti membaca/menulis file                    |
| `FileNotFoundException`         | File yang dicari tidak ditemukan                                                     |
| `ClassCastException`            | Gagal dalam konversi tipe objek secara eksplisit                                    |
| `InterruptedException`          | Terjadi saat thread yang sedang berjalan terganggu (biasanya saat `sleep` atau `wait`)|

### Kegunaan

Exception sangat berguna untuk mencegah program agar tidak mati saat terjadi Runtime Error.

## Exception Handling

### Pengertian

Saat program mengalami Runtime Error, program akan "melempar" Exception terkait, lalu Exception yang dilempar tadi bisa "ditangkap" lalu diproses, sehingga program tidak mati. Mekanisme ini disebut Exception Handling.

### Try Catch

Untuk menangkap Exception, kamu perlu menggunakan try-catch expression.

#### Penggunaan Dasar Try Catch

Try berisi kode yang berpotensi "melempar" Exception, sedangkan Catch berisi kode yang "menangkap" Exception.

Contohnya:

```java
public static void main(String[] args) {
    try {
        int result = 10 / 0; // Berpotensi "melempar" Exception
    } catch (Exception e) { // Menangkap Exception
        // Memproses Exception
        System.out.println("Terjadi kesalahan: " + e.getMessage());
    }
}
```

`Exception` pada kode di atas dapat diubah menjadi jenis Exception lain seperti pada tabel sebelumnya.

Contohnya:

```java
public static void main(String[] args) {
    try {
        // Berpotensi "melempar" Exception
        // Exception yang akan terjadi adalah Kesalahan Aritmatik (karena pembagian 0)
        int result = 10 / 0; 
    } catch (ArithmeticException e) { // Menangkap Exception Khusus Aritmatik
        // Memproses Exception
        System.out.println("Terjadi kesalahan aritmatika: " + e.getMessage());
    }
}
```

#### Multiple Catch Block

Di program sebelumnya, program hanya melempar satu Exception saja, padahal suatu program bisa saja melempar banyak Exception.

Contohnya:

```java
public static void main(String[] args) {
    // Menyebabkan beberapa jenis exception
    try {
        String str = null;

         // NullPointerException
        System.out.println(str.length());

        // ArithmeticException
        int result = 10 / 0;

        String[] arr = new String[2];

        // ArrayIndexOutOfBoundsException
        System.out.println(arr[5]);
    } 
    // Menangkap NullPointerException
    catch (NullPointerException e) { 
        System.out.println("Terjadi kesalahan: " + e.getMessage());
    } 
    // Menangkap ArithmeticException
    catch (ArithmeticException e) { 
        System.out.println("Terjadi kesalahan aritmatika: " + e.getMessage());
    }
    // Menangkap ArrayIndexOutOfBoundsException
    catch (ArrayIndexOutOfBoundsException e) {
        System.out.println("Indeks array tidak valid: " + e.getMessage());
    }
    // Menangkap semua jenis Exception lainnya (seperti else)
    catch (Exception e) {
        System.out.println("Terjadi kesalahan lain yang tidak terduga: " + e.getMessage());
    }
}
```

#### Finally

Selain try-catch, kamu bisa menambahkan blok Finally. Blok ini akan selalu dijalankan baik terjadi Exception ataupun tidak.

Contohnya:

```java
public static void main(String[] args) {
    // Menyebabkan beberapa jenis exception
    try {
        String str = null;

         // NullPointerException
        System.out.println(str.length());

        // ArithmeticException
        int result = 10 / 0;

        String[] arr = new String[2];

        // ArrayIndexOutOfBoundsException
        System.out.println(arr[5]);
    } 
    // Menangkap NullPointerException
    catch (NullPointerException e) { 
        System.out.println("Terjadi kesalahan: " + e.getMessage());
    } 
    // Menangkap ArithmeticException
    catch (ArithmeticException e) { 
        System.out.println("Terjadi kesalahan aritmatika: " + e.getMessage());
    }
    // Menangkap ArrayIndexOutOfBoundsException
    catch (ArrayIndexOutOfBoundsException e) {
        System.out.println("Indeks array tidak valid: " + e.getMessage());
    }
    // Menangkap semua jenis Exception lainnya (seperti else)
    catch (Exception e) {
        System.out.println("Terjadi kesalahan lain yang tidak terduga: " + e.getMessage());
    } 
    // Ini akan selalu dieksekusi apapun yang terjadi
    finally {
        System.out.println("Blok finally dieksekusi: proses selesai.");
    }
```

### Throw and Throws

Throw dan Throws digunakan untuk melempar Exception.

#### Throw

Digunakan untuk melempar Exception secara manual. Digunakan jika kita ingin sengaja memunculkan error.

#### Penggunaan Throw

Secara umum, Throw bisa ditulis seperti berikut:

```java
throw new Exception("Pesan error");
```

Contoh pengguaan:

```java
public static void main(String[] args) {
    int usia = 15;
    if (usia < 13) {
        throw new IllegalArgumentException("Usia harus 13 tahun ke atas.");
    }
}
```

#### Throws

Throws dengan `s` digunakan untuk menandai bahwa suatu method bisa melempar Exception.

#### Penggunaan Throws

Secara umum, Throws bisa ditulis seperti berikut:

```java
public void namaMethod() throws Exception {
    // kode yang bisa menyebabkan exception
}
```

Contoh penggunaan:

```java
public class ValidasiPassword {
    // Method untuk memeriksa apakah password valid
    public static void periksaPassword(String password) throws IllegalArgumentException {
        if (password == null || password.length() < 8) {
            throw new IllegalArgumentException("Password harus minimal 8 karakter dan tidak kosong.");
        }

        System.out.println("Password valid: " + password);
    }

    public static void main(String[] args) {
        try {
            periksaPassword("12345");  // Password terlalu pendek
        } catch (IllegalArgumentException e) {
            System.out.println("Terjadi kesalahan validasi: " + e.getMessage());
        }

        try {
            periksaPassword("rahasia123");  // Password valid
        } catch (IllegalArgumentException e) {
            System.out.println("Terjadi kesalahan validasi: " + e.getMessage());
        }
    }
}
```
