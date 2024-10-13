1. Membuat dokumen HTML 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Dasar</title>
</head>
<body>
    <header>
        <h1>CSS Internal dan <i> Inline CSS</i></h1>
    </header>
    <nav>
        <a href="lab2_css_dasar.html">CSS Dasar</a>
        <a href="lab2_eksternal.html">CSS Eksternal</a>
        <a href="lab1_tag_dasar.html">HTML Dasar</a>
    </nav>
    <!--CSS ID Selector-->
    <div id="intro">
        <h1>Hello World</h1>
        <p>Kami sedang belajar HTML dan CSS dasar, pada mata kuliah <b> Pemograman Web</b> di <i>Universitas Pelita Bangsa</i>. Pelajaran pertama yang kami dapat adalah membuat tampilan web sederhana dalam rangka mengenal tag-tag dasar HTML dan CSS.</p>
        <!--CSS Class Selector-->
        <a class="button btn-primary" href="#intro">Informasi selengkapnya.</a>
    </div>
</body>
</html>
![Screenshot (209)](https://github.com/user-attachments/assets/e8617e22-24ff-4e5a-b232-6f7e5767f9b7)

2. Mendeklarasikan CSS internal
   <head>
    <title>CSS Dasar</title>
    <style>
        body {
            font-family: 'Open Sans', sans-serif;
        }
        header {
            min-height: 80px;
            border-bottom: 1px solid #77ccef;
        }
        h1 {
            font-size: 24px;
            color: #0f188f;
            text-align: 20px 10px;
        }
        h1 i {
            color:6d6a6;
        }
    </style>
</head>
![Screenshot (211)](https://github.com/user-attachments/assets/a8ef7d04-dcc1-425f-b35b-6678f913718e)

3. menambahkan Inline CSS
   <p style="text-align: center; color: #ccd8c4;">
![Screenshot (212)](https://github.com/user-attachments/assets/39dc307c-2b60-46ec-b262-f65f40ccb9a0)

4. membuat CSS eksternal
   nav {
    background: #20A759;
    color: #fff;
    padding: 10px;
}
nav a {
    color: #fff;
    text-decoration: none;
    padding: 10px 20px;
}
nav .active,
nav a:hover {
    background: #0bb63a;
}

kemudian tambahkan tag <link> untuk merujuk file css yang sudah dibuat pada bagian <head>
<head>
    <link rel="stylesheet" href="style_eksternal.css">
    <title>CSS Dasar</title>

5. menambahkan CSS selector
   #intro {
    background: #418fb1;
    border: 1px solid #099249;
    min-height: 100px;
    padding: 10px;
}
#intro h1 {6. 
    text-align: left;
    border: 0;
    color: #fff;
}
.button {
    padding: 15px 20px;
    background: #bebcbd;
    color: #fff;
    display: inline-block;
    margin: 10px;
    text-decoration: none;
}
.btn-primary {
    background: #e42a42;
}
![Screenshot (214)](https://github.com/user-attachments/assets/d8a63ca9-78fe-4da7-bc79-05cf03809b8c)

Pertanyaan Dan Tugas
1. Mengubah dan menambah properti CSS menggunakan CSS Cheat Sheet:  
   Menambahkan warna latar belakang (background-color):
     ```css
     h1 {
         background-color: lightblue;
     }
     ```
     Ini akan memberikan warna latar belakang `lightblue` pada elemen `h1`.

   Mengubah margin dan padding:
     ```css
     p {
         margin: 20px;
         padding: 10px;
     }
     ```
     Menambahkan margin dan padding pada paragraf akan memengaruhi ruang di dalam dan luar paragraf.

   Menggunakan `hover` untuk efek ketika elemen disentuh:
     ```css
     a:hover {
         color: red;
     }
     ```
     Ini akan mengubah warna teks dari tag `a` menjadi merah saat pointer menyentuh link.

2. Perbedaan deklarasi `h1 {...}` dengan `#intro h1 {...}`:
   - `h1 {...}` adalah selektor global yang akan memengaruhi semua elemen `h1` di dalam dokumen HTML.
   - `#intro h1 {...}` adalah selektor spesifik yang hanya akan memengaruhi elemen `h1` yang berada di dalam elemen dengan `id="intro"`. Ini adalah seleksi kontekstual yang lebih spesifik.

     Contoh:
     ```html
     <div id="intro">
         <h1>Ini akan terpengaruh oleh #intro h1</h1>
     </div>
     <h1>Ini akan terpengaruh oleh h1</h1>
     ```

3. Prioritas deklarasi internal, eksternal, dan inline CSS:
   Browser akan menerapkan **urutan prioritas** CSS berdasarkan skenario berikut:
   1. Inline CSS: CSS yang ditulis langsung pada elemen akan mendapat prioritas tertinggi.
   2. Internal CSS: CSS yang berada di dalam tag `<style>` di file HTML.
   3. Eksternal CSS: File CSS yang dihubungkan secara eksternal melalui `<link>`.

   Namun, urutan prioritas dapat berubah** dengan penggunaan aturan seperti `!important`. Misalnya:

   ```html
   <style>
       p {
           color: blue; /* Internal CSS */
       }
   </style>
   <link rel="stylesheet" href="styles.css"> <!-- Eksternal CSS -->
   <p style="color: red;">Ini adalah paragraf</p> <!-- Inline CSS -->
   ```

4. ID vs Class pada deklarasi CSS:
   Ketika elemen memiliki ID dan Class, keduanya bisa memiliki deklarasi CSS yang berbeda. Namun, karena ID memiliki spesifisitas lebih tinggi dibandingkan dengan Class, gaya yang diterapkan pada ID akan ditampilkan pada elemen tersebut.

   Contoh:
   ```html
   <style>
       #paragraf-1 {
           color: green;
       }
       .text-paragraf {
           color: blue;
       }
   </style>
   <p id="paragraf-1" class="text-paragraf">Ini adalah paragraf</p>
   ```
