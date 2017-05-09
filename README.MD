# CekCokSass
> How to write maintanable CSS by using Sass

Dilaksanakan pada 09 Mei 2017 @ QODR HQ

Oleh Nur Arif Hidayatullah a.k.a [@ariflaw](https://github.com/ariflaw)

## Pengenalan Sass
- Termasuk CSS preprocessors
- 3 CSS Preprocessors yang populer: Sass, LESS dan Stylus
- SASS Terlihat seperti CSS tetapi memiliki fitur yang tidak dimiliki CSS
- SASS seperti prepocessor untuk JS/Html: Coffescript / Haml
- Dibuat oleh Hampton Catlin, pembuat Haml
- Ada dua ekstensi di Sass: .scss dan .sass
  - perbedaannya pada penggunaan tanda kurung `()` & titik kome `;`
- Fitur Sass: variabel, importing, extend, nesting dll
- Instalasi Sass: [cek dokumentasi](http://sass-lang.com/install)

## Pengunaan Sass
- Compile file sass : `sass style.scss style.css`
- Otomatis mencompile file sass : `sass --watch style.scss:style.css`
- Menambah komentas yang hanya terbaca di file `.scss` menggunakan `// komentar`
- `@import` untuk mengimport file `.scss` : `@import "folder/file"`
  - berguna juga untuk menonaktifkan komponen yang tidak ingin dipakai
  - penamaan menggunakan `_` artinya partial file untuk mengcompile pada satu file
- nesting untuk membuat class secara terstruktur dalam satu kurung kurawal `{}`  
  ```scss
    .artikel {            
        h1 {
            color: #fff;
        }

        p {
            color: #999;
        }
    }  
  ```
- Pembuatan `variabel` menggunakan `$` : `$primary: red`
  - `variabel` juga memiliki tipe: number, color, string dll
  - jika ada variabel yg sama maka akan dieksekusi variabel terakhir
  - ada fitur `interpolation` untuk mengganti property dgn variabel: `#{$var}`
- `Mixin` untuk mengeset custom css yang nantinya dapat di `include`
  - juga dapat menerima argument/parameter dan nilai default
  ```scss
    @mixin btn {
        background-color: lighten($primary, 10%);
        color: #fff;
        width: $length;
        height: $length;
    }

    .box {
        @include btn;    
    }
  ```
- `Extends` untuk memanggil css dari class tertentu    
  ```scss
    .custom-btn {
        border: 1px solid #fff;
        padding: 10px;
    }

    .box {
        @extend .custom-btn;
    }

  ```
- `Placeholder` mirip `@mixin` (belum ngeh banget bedane)
- `Functions` untuk mendefiniskan beberapa fungsi dari SassScript seperti RGB, opacity, string function dll  
  ```scss
  background-color: lighten($primary, 10%);
  ```

### Resource
Slide pertemuan ini dapat diakses via [slideshare.net](https://www.slideshare.net/tahmina8765/syntactically-awesome-stylesheets-sass)