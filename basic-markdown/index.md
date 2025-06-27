# Basic Markdown Syntax


Artikel ini menawarkan contoh dasar sintaks Markdown yang dapat digunakan dalam file konten Hugo.

<!--more-->

{{< admonition >}}
Artikel ini adalah salinan dari halaman [Grav original](https://learn.getgrav.org/content/markdown).

Jika kamu ingin mengetahui tentang sintaks Markdown lanjutan dari tema **LoveIt**, silakan baca [halaman sintaks Markdown lanjutan](../theme-documentation-content#extended-markdown-syntax).
{{< /admonition >}}

Mari kita akui: Menulis konten untuk web itu melelahkan. Editor WYSIWYG membantu meringankan tugas ini, tetapi biasanya menghasilkan kode yang buruk, atau lebih parah lagi, halaman web yang jelek.

**Markdown** adalah cara yang lebih baik untuk menulis **HTML**, tanpa semua kompleksitas dan kejelekan yang biasanya menyertainya.

Beberapa keuntungan utama:

1. Markdown mudah dipelajari, dengan karakter tambahan yang minimal, jadi lebih cepat juga menulis konten.
2. Lebih sedikit kemungkinan kesalahan saat menulis dalam Markdown.
3. Menghasilkan output XHTML yang valid.
4. Memisahkan antara konten dan tampilan visual, jadi kamu tidak merusak tampilan situsmu.
5. Bisa menulis di editor teks atau aplikasi Markdown apa pun yang kamu suka.
6. Markdown menyenangkan digunakan!

John Gruber, penulis Markdown, mengatakan seperti ini:

> Tujuan utama dari sintaks penulisan Markdown adalah agar semudah mungkin dibaca.
> Idenya adalah dokumen yang ditulis dalam format Markdown seharusnya bisa langsung dipublikasikan sebagai teks biasa,
> tanpa terlihat seperti dokumen yang penuh tag atau instruksi format.
> Meskipun sintaks Markdown dipengaruhi oleh beberapa filter text-to-HTML yang sudah ada,
> sumber inspirasi terbesar adalah format email teks biasa.
>
> {{< style "text-align: right;" >}}-- *John Gruber*{{< /style >}}

Tanpa basa-basi lagi, mari kita bahas elemen utama dari Markdown dan seperti apa hasil HTML-nya!

{{< admonition tip >}}
:(far fa-bookmark fa-fw): Tandai halaman ini agar mudah diakses nanti!
{{< /admonition >}}

## 1 Judul (Headings)

Judul dari `h2` sampai `h6` dibuat dengan `#` sesuai levelnya:

```markdown
## Judul h2
### Judul h3
#### Judul h4
##### Judul h5
###### Judul h6
```

Hasil HTML-nya:

```html
<h2>Judul h2</h2>
<h3>Judul h3</h3>
<h4>Judul h4</h4>
<h5>Judul h5</h5>
<h6>Judul h6</h6>
```

{{< admonition note "ID Judul" >}}
Untuk menambahkan ID kustom pada judul, sisipkan ID dalam kurung kurawal di baris yang sama dengan judul:

```markdown
### Judul Keren {#id-kustom}
```

Hasil HTML-nya:

```html
<h3 id="id-kustom">Judul Keren</h3>
```

{{< /admonition >}}

## 2 Komentar

Komentar harus kompatibel dengan HTML.

```html
<!--
Ini adalah komentar
-->
```

Komentar di bawah ini **TIDAK** seharusnya terlihat:

<!--
Ini adalah komentar
-->

## 3 Garis Pemisah (Horizontal Rules)

Elemen `<hr>` HTML digunakan untuk membuat "pemisah tematik" antar paragraf.
Dalam Markdown, kamu bisa membuat `<hr>` dengan salah satu dari:

* `___`: tiga underscore berturut-turut
* `---`: tiga tanda minus berturut-turut
* `***`: tiga tanda bintang berturut-turut

Tampilan hasilnya seperti ini:

---

---

---

## 4 Isi Teks (Body Copy)

Isi teks biasa akan dibungkus dengan tag `<p></p>` dalam HTML.

Contoh isi teks:

```markdown
Lorem ipsum dolor sit amet, graecis denique ei vel, at duo primis mandamus. Et legere ocurreret pri,
animal tacimates complectitur ad cum. Cu eum inermis inimicus efficiendi. Labore officiis his ex,
soluta officiis concludaturque ei qui, vide sensibus vim ad.
```

Hasil HTML-nya:

```html
<p>Lorem ipsum dolor sit amet, graecis denique ei vel, at duo primis mandamus. Et legere ocurreret pri, animal tacimates complectitur ad cum. Cu eum inermis inimicus efficiendi. Labore officiis his ex, soluta officiis concludaturque ei qui, vide sensibus vim ad.</p>
```

Untuk **ganti baris**, cukup beri satu baris kosong.

## 5 HTML di Dalam Markdown (Inline HTML)

Kalau kamu butuh elemen HTML tertentu (dengan class misalnya), bisa langsung pakai HTML:

```html
Paragraf dalam Markdown.

<div class="class">
    Ini adalah <b>HTML</b>
</div>

Paragraf dalam Markdown.
```

## 6 Penekanan (Emphasis)

### Tebal (Bold)

Untuk menekankan teks dengan font lebih tebal.

Cuplikan teks berikut akan **ditampilkan sebagai teks tebal**.

```markdown
**ditampilkan sebagai teks tebal**
__ditampilkan sebagai teks tebal__
```

Hasil HTML-nya:

```html
<strong>ditampilkan sebagai teks tebal</strong>
```

### Miring (Italic)

Untuk menekankan teks dengan huruf miring.

Cuplikan teks berikut akan *ditampilkan sebagai teks miring*.

```markdown
*ditampilkan sebagai teks miring*
_ditampilkan sebagai teks miring_
```

Hasil HTML-nya:

```html
<em>ditampilkan sebagai teks miring</em>
```

...

### Coret (Strikethrough)

Dalam \[[GFM\]^(GitHub flavored Markdown)](https://github.github.com/gfm/), kamu bisa membuat teks dicoret.

```markdown
~~Coret teks ini.~~
```

Hasil tampilannya seperti ini:

~~Coret teks ini.~~

Hasil HTML-nya:

```html
<del>Coret teks ini.</del>
```

### Kombinasi

Tebal, miring, dan coret bisa digunakan bersamaan.

```markdown
***tebal dan miring***
~~**coret dan tebal**~~
~~*coret dan miring*~~
~~***tebal, miring, dan coret***~~
```

Hasil tampilannya seperti ini:

***tebal dan miring***

~~**coret dan tebal**~~

~~*coret dan miring*~~

~~***tebal, miring, dan coret***~~

Hasil HTML-nya:

```html
<em><strong>tebal dan miring</strong></em>
<del><strong>coret dan tebal</strong></del>
<del><em>coret dan miring</em></del>
<del><em><strong>tebal, miring, dan coret</strong></em></del>
```

## 7 Kutipan (Blockquotes)

Untuk mengutip blok konten dari sumber lain dalam dokumenmu.

Tambahkan `>` sebelum teks yang ingin kamu kutip:

```markdown
> **Fusion Drive** menggabungkan hard drive dengan flash storage (solid-state drive) dan menyajikannya sebagai satu volume logis dengan kapasitas gabungan dari kedua drive.
```

Hasil tampilannya:

> **Fusion Drive** menggabungkan hard drive dengan flash storage (solid-state drive) dan menyajikannya sebagai satu volume logis dengan kapasitas gabungan dari kedua drive.

Hasil HTML-nya:

```html
<blockquote>
  <p>
    <strong>Fusion Drive</strong> menggabungkan hard drive dengan flash storage (solid-state drive) dan menyajikannya sebagai satu volume logis dengan kapasitas gabungan dari kedua drive.
  </p>
</blockquote>
```

Kutipan juga bisa disarang (nested):

```markdown
> Donec massa lacus, ultricies a ullamcorper in, fermentum sed augue.
Nunc augue augue, aliquam non hendrerit ac, commodo vel nisi.
>> Sed adipiscing elit vitae augue consectetur a gravida nunc vehicula. Donec auctor
odio non est accumsan facilisis. Aliquam id turpis in dolor tincidunt mollis ac eu diam.
```

Hasil tampilannya:

> Donec massa lacus, ultricies a ullamcorper in, fermentum sed augue. Nunc augue augue, aliquam non hendrerit ac, commodo vel nisi.
>
> > Sed adipiscing elit vitae augue consectetur a gravida nunc vehicula. Donec auctor odio non est accumsan facilisis. Aliquam id turpis in dolor tincidunt mollis ac eu diam.

## 8 Daftar (Lists)

### Tidak Berurutan (Unordered)

Daftar item di mana urutannya tidak penting.

Kamu bisa menggunakan salah satu dari simbol berikut sebagai bullet untuk setiap item daftar:

```markdown
* bullet valid
- bullet valid
+ bullet valid
```

Contohnya:

```markdown
* Lorem ipsum dolor sit amet
* Consectetur adipiscing elit
* Integer molestie lorem at massa
* Facilisis in pretium nisl aliquet
* Nulla volutpat aliquam velit
  * Phasellus iaculis neque
  * Purus sodales ultricies
  * Vestibulum laoreet porttitor sem
  * Ac tristique libero volutpat at
* Faucibus porta lacus fringilla vel
* Aenean sit amet erat nunc
* Eget porttitor lorem
```

Hasil tampilannya seperti ini:

* Lorem ipsum dolor sit amet
* Consectetur adipiscing elit
* Integer molestie lorem at massa
* Facilisis in pretium nisl aliquet
* Nulla volutpat aliquam velit

  * Phasellus iaculis neque
  * Purus sodales ultricies
  * Vestibulum laoreet porttitor sem
  * Ac tristique libero volutpat at
* Faucibus porta lacus fringilla vel
* Aenean sit amet erat nunc
* Eget porttitor lorem

...

### Coret (Strikethrough)

Dalam \[[GFM\]^(GitHub flavored Markdown)](https://github.github.com/gfm/), kamu bisa membuat teks dicoret.

```markdown
~~Coret teks ini.~~
```

Hasil tampilannya seperti ini:

~~Coret teks ini.~~

Hasil HTML-nya:

```html
<del>Coret teks ini.</del>
```

### Kombinasi

Tebal, miring, dan coret bisa digunakan bersamaan.

```markdown
***tebal dan miring***
~~**coret dan tebal**~~
~~*coret dan miring*~~
~~***tebal, miring, dan coret***~~
```

Hasil tampilannya seperti ini:

***tebal dan miring***

~~**coret dan tebal**~~

~~*coret dan miring*~~

~~***tebal, miring, dan coret***~~

Hasil HTML-nya:

```html
<em><strong>tebal dan miring</strong></em>
<del><strong>coret dan tebal</strong></del>
<del><em>coret dan miring</em></del>
<del><em><strong>tebal, miring, dan coret</strong></em></del>
```

## 7 Kutipan (Blockquotes)

Untuk mengutip blok konten dari sumber lain dalam dokumenmu.

Tambahkan `>` sebelum teks yang ingin kamu kutip:

```markdown
> **Fusion Drive** menggabungkan hard drive dengan flash storage (solid-state drive) dan menyajikannya sebagai satu volume logis dengan kapasitas gabungan dari kedua drive.
```

Hasil tampilannya:

> **Fusion Drive** menggabungkan hard drive dengan flash storage (solid-state drive) dan menyajikannya sebagai satu volume logis dengan kapasitas gabungan dari kedua drive.

Hasil HTML-nya:

```html
<blockquote>
  <p>
    <strong>Fusion Drive</strong> menggabungkan hard drive dengan flash storage (solid-state drive) dan menyajikannya sebagai satu volume logis dengan kapasitas gabungan dari kedua drive.
  </p>
</blockquote>
```

Kutipan juga bisa disarang (nested):

```markdown
> Donec massa lacus, ultricies a ullamcorper in, fermentum sed augue.
Nunc augue augue, aliquam non hendrerit ac, commodo vel nisi.
>> Sed adipiscing elit vitae augue consectetur a gravida nunc vehicula. Donec auctor
odio non est accumsan facilisis. Aliquam id turpis in dolor tincidunt mollis ac eu diam.
```

Hasil tampilannya:

> Donec massa lacus, ultricies a ullamcorper in, fermentum sed augue. Nunc augue augue, aliquam non hendrerit ac, commodo vel nisi.
>
> > Sed adipiscing elit vitae augue consectetur a gravida nunc vehicula. Donec auctor odio non est accumsan facilisis. Aliquam id turpis in dolor tincidunt mollis ac eu diam.

## 8 Daftar (Lists)

### Tidak Berurutan (Unordered)

Daftar item di mana urutannya tidak penting.

Kamu bisa menggunakan salah satu dari simbol berikut sebagai bullet untuk setiap item daftar:

```markdown
* bullet valid
- bullet valid
+ bullet valid
```

Contohnya:

```markdown
* Lorem ipsum dolor sit amet
* Consectetur adipiscing elit
* Integer molestie lorem at massa
* Facilisis in pretium nisl aliquet
* Nulla volutpat aliquam velit
  * Phasellus iaculis neque
  * Purus sodales ultricies
  * Vestibulum laoreet porttitor sem
  * Ac tristique libero volutpat at
* Faucibus porta lacus fringilla vel
* Aenean sit amet erat nunc
* Eget porttitor lorem
```

Hasil tampilannya seperti ini:

* Lorem ipsum dolor sit amet
* Consectetur adipiscing elit
* Integer molestie lorem at massa
* Facilisis in pretium nisl aliquet
* Nulla volutpat aliquam velit

  * Phasellus iaculis neque
  * Purus sodales ultricies
  * Vestibulum laoreet porttitor sem
  * Ac tristique libero volutpat at
* Faucibus porta lacus fringilla vel
* Aenean sit amet erat nunc
* Eget porttitor lorem

HTML-nya:

```html
<ul>
  <li>Lorem ipsum dolor sit amet</li>
  <li>Consectetur adipiscing elit</li>
  <li>Integer molestie lorem at massa</li>
  <li>Facilisis in pretium nisl aliquet</li>
  <li>Nulla volutpat aliquam velit
    <ul>
      <li>Phasellus iaculis neque</li>
      <li>Purus sodales ultricies</li>
      <li>Vestibulum laoreet porttitor sem</li>
      <li>Ac tristique libero volutpat at</li>
    </ul>
  </li>
  <li>Faucibus porta lacus fringilla vel</li>
  <li>Aenean sit amet erat nunc</li>
  <li>Eget porttitor lorem</li>
</ul>
```

### Berurutan (Ordered)

Daftar item yang urutannya penting.

```markdown
1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa
4. Facilisis in pretium nisl aliquet
5. Nulla volutpat aliquam velit
6. Faucibus porta lacus fringilla vel
7. Aenean sit amet erat nunc
8. Eget porttitor lorem
```

Hasil tampilannya:

1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa
4. Facilisis in pretium nisl aliquet
5. Nulla volutpat aliquam velit
6. Faucibus porta lacus fringilla vel
7. Aenean sit amet erat nunc
8. Eget porttitor lorem

HTML-nya:

```html
<ol>
  <li>Lorem ipsum dolor sit amet</li>
  <li>Consectetur adipiscing elit</li>
  <li>Integer molestie lorem at massa</li>
  <li>Facilisis in pretium nisl aliquet</li>
  <li>Nulla volutpat aliquam velit</li>
  <li>Faucibus porta lacus fringilla vel</li>
  <li>Aenean sit amet erat nunc</li>
  <li>Eget porttitor lorem</li>
</ol>
```

> 💡 **Tips:** Kamu bisa menggunakan `1.` untuk semua nomor, Markdown akan secara otomatis menomori ulang daftar saat dirender:

```markdown
1. Lorem ipsum dolor sit amet
1. Consectetur adipiscing elit
1. Integer molestie lorem at massa
1. Facilisis in pretium nisl aliquet
1. Nulla volutpat aliquam velit
1. Faucibus porta lacus fringilla vel
1. Aenean sit amet erat nunc
1. Eget porttitor lorem
```

Hasil tampilannya:

1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa
4. Facilisis in pretium nisl aliquet
5. Nulla volutpat aliquam velit
6. Faucibus porta lacus fringilla vel
7. Aenean sit amet erat nunc
8. Eget porttitor lorem

The HTML looks like this:

```html
<ol>
  <li>Lorem ipsum dolor sit amet</li>
  <li>Consectetur adipiscing elit</li>
  <li>Integer molestie lorem at massa</li>
  <li>Facilisis in pretium nisl aliquet</li>
  <li>Nulla volutpat aliquam velit</li>
  <li>Faucibus porta lacus fringilla vel</li>
  <li>Aenean sit amet erat nunc</li>
  <li>Eget porttitor lorem</li>
</ol>
```

{{< admonition tip >}}
If you just use `1.` for each number, Markdown will automatically number each item. For example:

```markdown
1. Lorem ipsum dolor sit amet
1. Consectetur adipiscing elit
1. Integer molestie lorem at massa
1. Facilisis in pretium nisl aliquet
1. Nulla volutpat aliquam velit
1. Faucibus porta lacus fringilla vel
1. Aenean sit amet erat nunc
1. Eget porttitor lorem
```

The rendered output looks like this:

1. Lorem ipsum dolor sit amet
1. Consectetur adipiscing elit
1. Integer molestie lorem at massa
1. Facilisis in pretium nisl aliquet
1. Nulla volutpat aliquam velit
1. Faucibus porta lacus fringilla vel
1. Aenean sit amet erat nunc
1. Eget porttitor lorem
{{< /admonition >}}

### Task Lists

Task lists allow you to create a list of items with checkboxes. To create a task list, add dashes (`-`) and brackets with a space (`[ ]`) before task list items. To select a checkbox, add an x in between the brackets (`[x]`).

```markdown
- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media
```

The rendered output looks like this:

- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media

## 9 Code

### Inline Code

Wrap inline snippets of code with <code>`</code>.

```markdown
In this example, `<section></section>` should be wrapped as **code**.
```

The rendered output looks like this:

In this example, `<section></section>` should be wrapped as **code**.

The HTML looks like this:

```html
<p>
  In this example, <code>&lt;section&gt;&lt;/section&gt;</code> should be wrapped with <strong>code</strong>.
</p>
```

### Indented Code

Or indent several lines of code by at least four spaces, as in:

```markdown
    // Some comments
    line 1 of code
    line 2 of code
    line 3 of code
```

The rendered output looks like this:

    // Some comments
    line 1 of code
    line 2 of code
    line 3 of code

The HTML looks like this:

```html
<pre>
  <code>
    // Some comments
    line 1 of code
    line 2 of code
    line 3 of code
  </code>
</pre>
```

### Block Fenced Code

Use "fences" <code>```</code> to block in multiple lines of code with a language attribute.

{{< highlight markdown >}}
```markdown
Sample text here...
```
{{< / highlight >}}

The HTML looks like this:

```html
<pre language-html>
  <code>Sample text here...</code>
</pre>
```

### Syntax Highlighting

[GFM]^(GitHub Flavored Markdown) also supports syntax highlighting.

To activate it, simply add the file extension of the language you want to use directly after the first code "fence",
<code>```js</code>, and syntax highlighting will automatically be applied in the rendered HTML.

For example, to apply syntax highlighting to JavaScript code:

{{< highlight markdown >}}
```js
grunt.initConfig({
  assemble: {
    options: {
      assets: 'docs/assets',
      data: 'src/data/*.{json,yml}',
      helpers: 'src/custom-helpers.js',
      partials: ['src/partials/**/*.{hbs,md}']
    },
    pages: {
      options: {
        layout: 'default.hbs'
      },
      files: {
        './': ['src/templates/pages/index.hbs']
      }
    }
  }
};
```
{{< / highlight >}}

The rendered output looks like this:

```js
grunt.initConfig({
  assemble: {
    options: {
      assets: 'docs/assets',
      data: 'src/data/*.{json,yml}',
      helpers: 'src/custom-helpers.js',
      partials: ['src/partials/**/*.{hbs,md}']
    },
    pages: {
      options: {
        layout: 'default.hbs'
      },
      files: {
        './': ['src/templates/pages/index.hbs']
      }
    }
  }
};
```

{{< admonition >}}
[Syntax highlighting page](https://gohugo.io/content-management/syntax-highlighting/) in **Hugo** Docs introduces more about syntax highlighting, including highlight shortcode.
{{< /admonition >}}

## 10 Tables

Tables are created by adding pipes as dividers between each cell, and by adding a line of dashes (also separated by bars) beneath the header. Note that the pipes do not need to be vertically aligned.

```markdown
| Option | Description |
| ------ | ----------- |
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |
```

The rendered output looks like this:

| Option | Description |
| ------ | ----------- |
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |

The HTML looks like this:

```html
<table>
  <thead>
    <tr>
      <th>Option</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>data</td>
      <td>path to data files to supply the data that will be passed into templates.</td>
    </tr>
    <tr>
      <td>engine</td>
      <td>engine to be used for processing templates. Handlebars is the default.</td>
    </tr>
    <tr>
      <td>ext</td>
      <td>extension to be used for dest files.</td>
    </tr>
  </tbody>
</table>
```

{{< admonition note "Right or center aligned text" >}}
Adding a colon on the right side of the dashes below any heading will right align text for that column.

Adding colons on both sides of the dashes below any heading will center align text for that column.

```markdown
| Option | Description |
|:------:| -----------:|
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |
```

The rendered output looks like this:

| Option | Description |
|:------:| -----------:|
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |
{{< /admonition >}}

## 11 Links {#links}

### Basic Link

```markdown
<https://assemble.io>
<contact@revolunet.com>
[Assemble](https://assemble.io)
```

The rendered output looks like this (hover over the link, there is no tooltip):

<https://assemble.io>

<contact@revolunet.com>

[Assemble](https://assemble.io)

The HTML looks like this:

```html
<a href="https://assemble.io">https://assemble.io</a>
<a href="mailto:contact@revolunet.com">contact@revolunet.com</a>
<a href="https://assemble.io">Assemble</a>
```

### Add a Title

```markdown
[Upstage](https://github.com/upstage/ "Visit Upstage!")
```

The rendered output looks like this (hover over the link, there should be a tooltip):

[Upstage](https://github.com/upstage/ "Visit Upstage!")

The HTML looks like this:

```html
<a href="https://github.com/upstage/" title="Visit Upstage!">Upstage</a>
```

### Named Anchors

Named anchors enable you to jump to the specified anchor point on the same page. For example, each of these chapters:

```markdown
## Table of Contents
  * [Chapter 1](#chapter-1)
  * [Chapter 2](#chapter-2)
  * [Chapter 3](#chapter-3)
```

will jump to these sections:

```markdown
## Chapter 1 <a id="chapter-1"></a>
Content for chapter one.

## Chapter 2 <a id="chapter-2"></a>
Content for chapter one.

## Chapter 3 <a id="chapter-3"></a>
Content for chapter one.
```

{{< admonition >}}
The specific placement of the anchor tag seems to be arbitrary. They are placed inline here since it seems to be unobtrusive, and it works.
{{< /admonition >}}

## 12 Footnotes

Footnotes allow you to add notes and references without cluttering the body of the document. When you create a footnote, a superscript number with a link appears where you added the footnote reference. Readers can click the link to jump to the content of the footnote at the bottom of the page.

To create a footnote reference, add a caret and an identifier inside brackets (`[^1]`). Identifiers can be numbers or words, but they can’t contain spaces or tabs. Identifiers only correlate the footnote reference with the footnote itself — in the output, footnotes are numbered sequentially.

Add the footnote using another caret and number inside brackets with a colon and text (`[^1]: My footnote.`). You don’t have to put footnotes at the end of the document. You can put them anywhere except inside other elements like lists, block quotes, and tables.

```markdown
This is a digital footnote[^1].
This is a footnote with "label"[^label]

[^1]: This is a digital footnote
[^label]: This is a footnote with "label"
```

This is a digital footnote[^1].

This is a footnote with "label"[^label]

[^1]: This is a digital footnote
[^label]: This is a footnote with "label"

## 13 Images

Images have a similar syntax to links but ude a preceding exclamation point.

```markdown
![Minion](https://octodex.github.com/images/minion.png)
```

![Minion](https://octodex.github.com/images/minion.png)

or:

```markdown
![Alt text](https://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")
```

![Alt text](https://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")

Like links, images also have a footnote style syntax:

```markdown
![Alt text][id]
```

![Alt text][id]

With a reference later in the document defining the URL location:

```markdown
[id]: https://octodex.github.com/images/dojocat.jpg  "The Dojocat"
```

[id]: https://octodex.github.com/images/dojocat.jpg  "The Dojocat"

{{< admonition tip >}}
**LoveIt** theme has [special shortcode for image](../theme-documentation-extended-shortcodes#image), which provides more features.
{{< /admonition >}}

