---
sidebar_position: 1
---

# HTML

## Formatting

Seluruh HTML code harus menggunakan **2 space** untuk indentation dan tidak boleh ada potongan whitespace.
Syntax HTML5 harus digunakan dan seluruh attribute harus menggunakan **double quotes (")** untuk mengurung attributes.

```html
<div>
--<span>Hello World</span> //2 baris indentation
</div>
```
Elemen HTML5 harus menggunakan ```<div>``` dan ```<span>``` sebagai pembungkus elemen.

## Doctype and Layout

Kalian harus perhatikan pada saat penggunaan HTML5 doctype, tag ```<html>``` harus memiliki sebuah ```="lang"``` attribute.
Dan ```<head>``` juga harus mencantumkan ```"viewport"``` dan ```"charset"``` meta tag.

## Forms

Field form harus selalu menggunakan sebuah ```label``` dengan attribute ```"for"``` dan ```"id"``` pada input field. Ini akan
membantu aksebilitas dengan memfokuskan input ketika label di klick, dan juga membantu _screen readers_ mencocokkan label kepada input yang ditujukan.

```html
<label for="field-email">email</label>
<input type="email" id="field-email" name="email" value="" />
```
Setiap ```<input>``` harus memiliki sebuah ```"id"``` unique di page. Tidak perlu sama dengan attribute ```"name"```.

Seluruh form harus menggunakan keunggulan baru input type HTML5 seperti ```"placeholder"``` attribute. Menggunakan ini akan meningkatkan kemudahan pengguna.

```html
<div>
  <label for="field-email">Email</label>
  <input type="email" id="field-email" name="email" value="name@example.com">
</div>
<div>
  <label for="field-phone">Phone</label>
  <input type="phone" id="field-phone" name="phone" value="" placeholder="+44 077 12345 678">
</div>
<div>
  <label for="field-url">Homepage</label>
  <input type="url" id="field-url" name="url" value="" placeholder="http://example.com">
</div>
```

## Including ```data-``` Attribute

Biasanya ```class``` satu-satunya yang akan dipakai sebagai hooks saat styling. Jika kamu membutuhkan data tambahan pada HTML dokumen, contohnya pada saat passing data JavaScript, maka kamu **harus** menggunakan ```data-``` attribute.
```html
<a class="btn" data-format="csv">Download CSV</a>
```
Dengan begini akan dapat mudah diakses via jQuery menggunakan ```.data()``` method dengan cara seperti ini.
```js
jQuery('.btn').data('format'); //=> "csv"

// Get the contents of all data attributes.
jQuery('.btn').data(); => {format: "csv"}
```
Nah sebagai catatan, dalam JavaScript API untuk datasets seperti itu akan convert seluruh attribute name ke dalam bentuk **camelCase**.
Jadi ```"data-file-format"``` akan menjadi ```fileFormat```
Sebagai contoh:
```html
<a class="btn" data-file-format="csv">Download CSV</a>
```
Akan menjadi:
```js
jQuery('.btn').data('fileFormat'); //=> "csv"
jQuery('.btn').data(); => {fileFormat: "csv"}
```