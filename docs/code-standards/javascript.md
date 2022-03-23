---
sidebar_position: 3
---

# Javascript

## Formatting

Seluruh JavaScript code juga harus menggunakan **2 space** untuk indentation dan tidak boleh ada potongan whitespace.

## White Space

Dua space harus digunakan untuk indentation kapanpun, namun tidak boleh digunakan di dalam tanda kurung
>_antara tanda kurung dan isinya_

```js
// BAD: Terlalu banyak whitespace.
function getUrl( full ) {
  var url = '/styleguide/javascript/';
  if ( full ) {
    url = 'http://okfn.github.com/ckan' + url;
  }
  return url;
}

// GOOD: :)
function getUrl(full) {
  var url = '/styleguide/javascript/';
  if (full) {
    url = 'http://okfn.github.com/ckan' + url;
  }
  return url;
}
```

## Quotes (Tanda Kutip)

Single quotes harus digunakan dimanapun kecuali ketika kamu menulis JSON atau string yang memang mengandung single quotes. Ini akan mempermudah membuat string yang mengandung HTML.

```js
jQuery('<div id="my-div" />').appendTo('body');
```
Object properti harus diketik tanpa tanda kutip, kecuali memang dibutuhkan oleh libs tersebut.
```js
var object = {
  name: 'bill',
  'class': 'user-name'
};
```
