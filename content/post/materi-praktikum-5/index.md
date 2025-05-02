---
title: "Materi Praktikum 5"
description: Membahas tentang Object Oriented Programming
date: 2025-05-01T14:26:29Z
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

## Object Oriented Programming

### Pengertian

Object Oriented Programming (OOP) secara literal berarti Pemrograman Berorientasi Object (PBO), adalah sudut pandang bahasa pemrorgaman yang berkonsep "object".

### Karakteristik Umum

Secara umum, bahasa pemrograman disebut OOP jika memenuhi kriteria berikut:

1. Berbasis objek dan class
2. Ada konsep properti dan method
3. Ada relasi antar objek
4. Fokus pada representasi dunia nyata

## Class

### Pengertian

Ciri-ciri utama dalam bahasa yang mendukung OOP adalah adanya `class`. Class adalah template atau cetakan. Apa yang dimaksud dari cetakan disini? Nanti kamu akan lihat pada point berikutnya.

### Contoh Class

```java
class Mahasiswa {

}
```

Perhatikan bahwa dalam menamakan class, ada baiknya menggunakan format `CamelCase` yaitu huruf awal setiap kata dibuat kapital.

Contoh penamaan yang benar

```java
class UserProfile {

}
```

Contoh penamaan yang salah

```java
class userprofile {
    // atau userProfile juga salah
}
```

### Field

Class dapat menyimpan nilai atau yang dikenal sebagai field/attribute/properties (ketiga itu sama saja).

```java
class Mahasiswa {
    String nama;
    int nrp;
    float ipk;
    final String KAMPUS = "ITS";
}
```

Perhatikan bahwa saat suatu Field itu final / konstan, maka nama Field ditulis kapital.

### Method

Class juga dapat menyimpan "kemampuan" atau "behavior" dengan cara membuat `method`.

```java
class Mahasiswa {
    String nama;
    int nrp;
    float ipk;
    final String KAMPUS = "ITS";

    void info() {
        System.out.println("Nama: " + name);
        System.out.println("NRP: " + nrp);
        System.out.println("IPK: " + ipk);
        System.out.println("Kampus: " + KAMPUS);
    }

    String getName() {
        return name;
    }

    int getNRP() {
        return nrp;
    }

    // Silahkan lengkapi sisanya
}
```

### This

Adakalanya nama Field kamu sama dengan nama parameter atau nama variable yang lain.

Contohnya:

```java
class Mahasiswa {
    String nama;
    int nrp;
    float ipk;
    final String KAMPUS = "ITS";

    void info() {
        System.out.println("Nama: " + name);
        System.out.println("NRP: " + nrp);
        System.out.println("IPK: " + ipk);
        System.out.println("Kampus: " + KAMPUS);
    }

    String getName() {
        return name;
    }

    int getNRP() {
        return nrp;
    }

    String setName(String name) {
        name = name; // ini tidak berhasil
    }

    // Silahkan lengkapi sisanya
}
```

Untuk menghindari kebingungan tersebut, Java menyediakan keyword `this`

```java
class Mahasiswa {
    String nama;
    int nrp;
    float ipk;
    final String KAMPUS = "ITS";

    void info() {
        System.out.println("Nama: " + name);
        System.out.println("NRP: " + nrp);
        System.out.println("IPK: " + ipk);
        System.out.println("Kampus: " + KAMPUS);
    }

    String getName() {
        return name;
    }

    int getNRP() {
        return nrp;
    }

    void setName(String name) {
        // this.name merujuk pada Field name
        this.name = name;
    }

    void setNRP(int nrp) {
        this.nrp = nrp;
    }

    // Silahkan lengkapi sisanya
}
```

## Object

### Pengertian

Saat membahas Object Oriented Programming, sudah pasti membahas tentang Object. Apa itu object? Object adalah **hasil dari class**. Jika diibaratkan sebuah kue, maka `class` adalah cetakan kue, dan `object` adalah kue nya.

### Membuat Object

Class Mahasiswa sebelumnya bisa dibuat menjadi object Mahasiswa dengan cara berikut:

```java
class Main {
    public static void main(String[] args) {
        // Membuat object Mahasiswa
        Mahasiswa mahasiswa1 = new Mahasiswa()
    }
}

class Mahasiswa {
    String nama;
    int nrp;
    float ipk;
    final String KAMPUS = "ITS";

    void info() {
        System.out.println("Nama: " + name);
        System.out.println("NRP: " + nrp);
        System.out.println("IPK: " + ipk);
        System.out.println("Kampus: " + KAMPUS);
    }

    String getName() {
        return name;
    }

    int getNRP() {
        return nrp;
    }

    void setName(String name) {
        this.name = name;
    }

    void setNRP(int nrp) {
        this.nrp = nrp;
    }

    // Silahkan lengkapi sisanya
}
```

### Mengakses Field dan Method

Object automatis memiliki `Field` dan `method` yang ada dalam Class. Sebagaimana kue yang dibuat dengan cetakan kue pasti mengikuti bentuk cetakannya.

Kamu bisa mengakses Field dan method dengan menggunakan `(.) titik`.

```java
class Main {
    public static void main(String[] args) {
        // Membuat object Mahasiswa
        Mahasiswa mahasiswa1 = new Mahasiswa();
        // Mengakses Field
        System.out.println(mahasiswa1.ipk);
        // Mengakses method
        mahasiswa1.info();
    }
}
```

## Constructor

### Pengertian

Constructor adalah `method spesial`. Kenapa spesial? Karena constructor adalah method yang bertanggung jawab untuk membuat object.

### Membuat Constructor

Constructor memiliki nama yang sama dengan nama class nya. Misalnya dalam class Mahasiswa, maka nama constructornya adalah `Mahasiswa()`.

Secara default (bawaan), setiap class dalam Java sudah memiliki consctrutor kosong seperti berikut.

```java
class Mahasiswa {
    String nama;
    int nrp;
    float ipk;
    final String KAMPUS = "ITS";

    // Ini constructor
    Mahasiswa() {
       
    }

    void info() {
        System.out.println("Nama: " + name);
        System.out.println("NRP: " + nrp);
        System.out.println("IPK: " + ipk);
        System.out.println("Kampus: " + KAMPUS);
    }

    String getName() {
        return name;
    }

    int getNRP() {
        return nrp;
    }

    void setName(String name) {
        this.name = name;
    }

    void setNRP(int nrp) {
        this.nrp = nrp;
    }

    // Silahkan lengkapi sisanya
}
```

### Constructor dengan Parameter

Karena constructor adalah method, kamu bisa memberikan parameter di constructor.

Contoh:

```java
class Mahasiswa {
    String nama;
    int nrp;
    float ipk;
    final String KAMPUS = "ITS";

    // Ini constructor dengan parameter
    Mahasiswa(String name) {
        this.name = name;
    }

    void info() {
        System.out.println("Nama: " + name);
        System.out.println("NRP: " + nrp);
        System.out.println("IPK: " + ipk);
        System.out.println("Kampus: " + KAMPUS);
    }

    String getName() {
        return name;
    }

    int getNRP() {
        return nrp;
    }

    void setName(String name) {
        this.name = name;
    }

    void setNRP(int nrp) {
        this.nrp = nrp;
    }

    // Silahkan lengkapi sisanya
}
```

#### Memanggil Constructor dengan Parameter

Cara menggunakan contructor dengan parameter adalah sebagai berikut:

```java
class Main {
    public static void main(String[] args) {
        // Membuat object Mahasiswa dengan constructor ber-parameter
        Mahasiswa mahasiswa1 = new Mahasiswa("Bin Laden");
        // Mengakses Field
        System.out.println(mahasiswa1.ipk);
        // Mengakses method
        mahasiswa1.info();
    }
}
```

### Constructor Overloading

Sama seperti method, constructor juga mendukung overloading, yaitu beberapa method yang sama dengan parameter (bisa jumlah atau tipe data) yang berbeda.

```java
class Mahasiswa {
    String nama;
    int nrp;
    float ipk;
    final String KAMPUS = "ITS";

    // Sudah ada constructor (tanpa parameter)
    Mahasiswa() {

    }

    // Tapi ada lagi constructor lain (dengan parameter)
    Mahasiswa(String name) {
        this.name = name;
    }

    // Ada lagi constructor lain dengan parameter, namun jumlah parameternya berbeda
    Mahasiswa(String name, int nrp, float ipk) {
        this.name = name;
        this.nrp = nrp;
        this.ipk = ipk;
    }

    void info() {
        System.out.println("Nama: " + name);
        System.out.println("NRP: " + nrp);
        System.out.println("IPK: " + ipk);
        System.out.println("Kampus: " + KAMPUS);
    }

    String getName() {
        return name;
    }

    int getNRP() {
        return nrp;
    }

    void setName(String name) {
        this.name = name;
    }

    void setNRP(int nrp) {
        this.nrp = nrp;
    }

    // Silahkan lengkapi sisanya
}
```

#### Memanggil Constructor dengan Overloading

Cara menggunakan contructor dengan overloading adalah sebagai berikut:

```java
class Main {
    public static void main(String[] args) {
        // Constructor tanpa parameter
        Mahasiswa mahasiswa1 = new Mahasiswa();
        // Constructor dengan 1 Parameter
        Mahasiswa mahasiswa2 = new Mahasiswa("Mega Toto Walala Tibebe");
        // Constructor dengan 1 Parameter
        Mahasiswa mahasiswa3 = new Mahasiswa("Enikaen", 5000000911, 2.3f);
        // Mengakses Field
        System.out.println(mahasiswa1.ipk)
        // Mengakses method
        mahasiswa1.info()
    }
}
```

#### Memanggil Constructor Lain

Constructor dapat memanggil constructor lain dengan menggunakan kata kunci `this`.

```java
class Mahasiswa {
    String nama;
    int nrp;
    float ipk;
    final String KAMPUS = "ITS";

    // Memanggil constructor lain dengan kata kunci this
    Mahasiswa() {
        this("Mahasiswa Misterius");
    }

    Mahasiswa(String name) {
        this.name = name;
    }

    Mahasiswa(String name, int nrp, float ipk) {
        this.name = name;
        this.nrp = nrp;
        this.ipk = ipk;
    }

    void info() {
        System.out.println("Nama: " + name);
        System.out.println("NRP: " + nrp);
        System.out.println("IPK: " + ipk);
        System.out.println("Kampus: " + KAMPUS);
    }

    String getName() {
        return name;
    }

    int getNRP() {
        return nrp;
    }

    void setName(String name) {
        this.name = name;
    }

    void setNRP(int nrp) {
        this.nrp = nrp;
    }

    // Silahkan lengkapi sisanya
}
```

## Static

### Pengertian

Pasti kamu sudah sering mendengar kata `static`. Seluruh Field dan method di dalam `class` akan terikat ke `object`. Artinya, kamu perlu membuat object terlebih dahulu untuk mengakses Field atau method nya.

Dengan `static` kamu bisa mengakses Field dan method tersebut secara langsung dari class nya tanpa harus membuat object terlebih dahulu.

Namun konsekuensinya adalah Field atau method yang static hanya terikat kepada `class` bukan ke object, dan Field atau method yang static **hanya bisa** mengakses sesuatu yang static pula.

### Penggunaan Static

Cara penggunaan static seperti berikut:

#### Static Field

```java
class Mahasiswa {
    String nama;
    int nrp;
    float ipk;
    // Membuat Field menjadi static
    static final String KAMPUS = "ITS";
}

class Main {
    public static void main(String[] args) {
        // Memanggil Field yang statiic
        System.out.println(Mahasiswa.KAMPUS); // Akan menghasilkan "ITS"
    }
}
```

#### Static Method

```java
class Mahasiswa {
    String nama;
    int nrp;
    float ipk;
    static final String KAMPUS = "ITS";

    static void tempatKuliah() {
        System.out.println("Tempat Kuliah di: " + );
    }
}

class Main {
    public static void main(String[] args) {
        System.out.println(Mahasiswa.KAMPUS) ;
        Mahasiswa.tempatKuliah();
    }
}
```

## Primitive vs Non Primitive

Tipe data dalam Java dibagi menjadi dua kategori, yaitu Primitive dan Non Primitive.

Seharusnya kamu sudah tau bahwa di Java ada beberapa tipe data seperti: int, double, String, char, boolean, dan lain-lain. Jika diperhatikan, semua tipe data tersebut dituis dengan huruf kecil, kecuali `String`. Tapi kenapa?

### Primitive

Tipe data Primitive adalah tipe data bukan object. Contohnya int, double, boolean, float, char, dan lain-lain yang berawal huruf kecil.

Tipe data primitive selalu mempunyai default value (nilai awal jika tidak diisi), seperti `int` misalnya yang jika tidak diisi maka akan menghasilkan 0.

Karena bukan object, tipe data Primitive tidak mempunyai field ataupun method.

| Tipe Data   | Ukuran (bit) | Nilai Minimum                 | Nilai Maksimum                  | Default Value |
|-------------|--------------|-------------------------------|----------------------------------|---------------|
| byte        | 8            | -128                          | 127                              | 0             |
| short       | 16           | -32,768                       | 32,767                           | 0             |
| int         | 32           | -2^31 (-2,147,483,648)        | 2^31-1 (2,147,483,647)           | 0             |
| long        | 64           | -2^63                         | 2^63-1                           | 0L            |
| float       | 32           | ~1.4e-45                      | ~3.4e+38                         | 0.0f          |
| double      | 64           | ~4.9e-324                     | ~1.8e+308                        | 0.0d          |
| char        | 16           | '\u0000' (0)                  | '\uffff' (65,535)                | '\u0000'      |
| boolean     | 1 | false                         | true                             | false         |

### Non Primitive

Kebalikan dari Primitive, tipe data Non Primitive merupakan Object. Contohnya adalah `String`. Tapi kenapa ditulis dengan huruf awal yang kapital?

Ingat bahwa saat menulis class, sangat dianjurkan untuk menulisnya dengan huruf awal setiap kata berupa kapital. Sehingga `String` (yang merupakan class) ditulis dengan huruf awal yang kapital.

Karena tipe data Non Primitive merupakah Object, maka tipe data ini memiliki Field dan Method. Namun, jika tidak diisi, nilai awalnya adalah `null`.

| Tipe Data        | Deskripsi                                                                 | Contoh Penggunaan                         | Default Value |
|------------------|---------------------------------------------------------------------------|-------------------------------------------|---------------|
| String           | Kumpulan karakter (objek dari class `String`)                            | `String nama = "Yudha";`                  | null          |
| Array            | Kumpulan elemen bertipe sama (juga merupakan objek)                      | `int[] angka = {1, 2, 3};`                | null          |
| Class            | Blueprint untuk membuat objek custom                                     | `Mahasiswa mhs = new Mahasiswa();`        | null          |
| Interface        | Kontrak/struktur perilaku yang harus diimplementasikan oleh class lain   | `Runnable r = new MyRunnable();`          | null          |
| Enum             | Tipe khusus yang menyimpan nilai konstan                                 | `Hari h = Hari.SENIN;`                    | null          |
| Record (sejak Java 14)| Struktur data immutable dan ringan                                   | `record Point(int x, int y) {}`           | 
null          |

![Link Materi 5](materi5.png)