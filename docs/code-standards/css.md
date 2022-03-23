---
sidebar_position: 2
---

# CSS

## Formatting

Seluruh CSS code juga harus menggunakan **2 space** untuk indentation dan tidak boleh ada potongan whitespace.
Syntax HTML5 harus digunakan dan seluruh attribute harus menggunakan **double quotes (")** untuk mengurung attributes.
- Menggunakan sedikit tab dengan **(2 Space Indent)**
- Gunakan double quotes **(")**
- Pakai spasi setelah ```:``` dalam mendeklarasikan property CSS
- Pakai spasi sebelum ```{``` dalam mendeklarasikan rules
- Gunakan hex color ```#000``` daripada menggunakan ```rgba()```
- Selalu perhatikan older browser
- Selalu gunakan hanya 1 line pada deklarasi property
- Selalu gunakan 1 jarak space pada setiap pendeklarasian rules

Sebagai contoh

```css
.media {
  overflow: hidden;
  color: #fff;
  background-color: #000; /* Fallback value */
  background-image: linear-gradient(black, grey);
}

.media .img {
  float: left;
  border: 1px solid #ccc;
}

.media .img img {
  display: block;
}

.media .content {
  background: #fff url("../images/media-background.png") no-repeat;
}
```

## Naming

Seluruh id, class, dan attribute harus _lowercase_ dan menggunakan strip sebagai pemisah

```css
/* GOOD */
.dataset-list {}

/* BAD */
.datasetlist {}
.datasetList {}
.dataset_list {}
```

## Modularity and specificity

Cobalah untuk mengelompokkan semua selector secara longgar ke dalam modul jika memungkinkan dan hindari memiliki terlalu banyak selector dalam satu deklarasi agar mudah diganti.
```css
/* Avoid */
ul#dataset-list {}
ul#dataset-list li {}
ul#dataset-list li p a.download {}
```
Sebagai gantinya, buatlah kumpulan data dan styling elemen itu diluar containernya yang memungkinkan kamu untuk menggunakannya secara individu
```css
.dataset-list {}
.dataset-list-item {}
.dataset-list-item .download {}
```
Dalam case yang sama hati-hati dalam penggunaan class pada elemen html yang bisa berubah-ubah.
Contohnya ketika saat kita styling link sosial media:
```html
<ul class="social">
  <li><a href="">Twitter</a></li>
  <li><a href="">Facebook</a></li>
  <li><a href="">LinkedIn</a></li>
</ul>
```
Biasanya mungkin akan dipakai pseudo selectors untuk mempertahankan **clean code** HTML:
```css
.social li:nth-child(1) a {
  background-image: url(twitter.png);
}

.social li:nth-child(2) a {
  background-image: url(facebook.png);
}

.social li:nth-child(3) a {
  background-image: url(linked-in.png);
}
```
Namun membuatnya seperti ini akan menyebabkan berantakan saat sebuah item ditambah atau dihapus.
Sebagai gantinya kita dapat menggunakan class names untuk memastikan icon akan selalu cocok pada elemen.  
```css
.social .twitter {
  background-image: url(twitter.png);
}

.social .facebook {
  background-image: url(facebook.png);
}

.social .linked-in {
  background-image: url(linked-in.png);
}
```
Hindari menggunakan tag names dalam selector yang mungkin akan kita pakai kembali propertinya pada konteks lain.
```css
/* Tidak bisa menggunakan style ini pada <ol> dan <div> elemen */
ul.dataset-item {}
```
Dan juga id tidak boleh digunakan pada selector karena akan membuatnya sangat sulit untuk ditimpa nanti.
```css
/* Tidak bisa menimpa style button ini tanpa mencantumkan id */
.btn#download {}
```