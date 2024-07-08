<br />
<div id="readme-top" align="center">

  <h3 align="center">Markdown</h3>

  <p align="center">
    Markdown cheatsheet.
    <br />
    <br />
    <a href="https://github.com/mBlomsterberg/github-cheatsheet/blob/main/workflows/MATRIX.md">Matrix</a>
    ·
    <a href="https://github.com/mBlomsterberg/github-cheatsheet/blob/main/workflows/REUSABLE.md">Reusable</a>
  </p>
  <br />
</div>
<br>

# Overview
https://docs.github.com/en/get-started/writing-on-github 




```md
# H1
## H2
### H3
#### H4
##### H5
###### H6
```


```md
Emphasis            *asterisks* or _underscores_

Strong emphasis     **asterisks** or __underscores__.

Combined emphasis   **asterisks and _underscores_**.

Strikethrough       ~~Scratch this.~~
```

<br/>

## Horizontal Ruler

```md
--- 

***

___

```

---

***

___

<br/>

## Footnotes
```md
footnote[^1]
footnote[^mynote]

[^1]: This is a footnote
[^mynote]: This is a custom label footnote
```
footnote[^1]

footnote[^mynote]

[^1]: This is a footnote

[^mynote]: This is a custom label footnote

<br/>

## Blockquotes
```md
> Blockquotes.
```
> Blockquotes.

<br/>

## Lists
```md
Ordered
1. frist
2. second

Unordered
- first 
- second
```
Ordered
1. frist
2. second

Unordered
- first 
- second

<br/>

## Links
```md
[Link](https://www.google.com)
[Link](https://www.google.com "hover text")
[Link file](../markdown/README.md)

[link ref][1]
[1]: https://www.google.com
```

[Link](https://www.google.com)

[Link](https://www.google.com "hover text")

[Link file](../markdown/README.md)

[link ref][1]

[1]: https://www.google.com


<br/>

## Images
Markdown does not support custom sizes use html instead.
```md
![Logo](../logo.svg)
![Logo](https://github.com/mBlomsterberg/github-cheatsheet/blob/main/logo.svg)
![Logo](../logo.svg "hover text")

![Logo ref][1]
[1]: https://github.com/mBlomsterberg/github-cheatsheet/blob/main/logo.svg
```

![Logo](../logo.svg)

![Logo](https://github.com/mBlomsterberg/github-cheatsheet/blob/main/logo.svg)

![Logo](../logo.svg "hover text")

![Logo ref][img]

[img]: https://github.com/mBlomsterberg/github-cheatsheet/blob/main/logo.svg

<br/>

## Code snippet
```md

  ```javascript
    console.log("Hello World")
  '```
```
  ```javascript
    console.log("Hello World")
  ```

<br/>

## Tables
```md

| *Tables*      | `renders`     | **Cool** |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

```


| *Tables*      | `renders`     | **Cool** |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |


<br/>

## HTML

```html
<div id="readme-top" align="center">
  <a href="https://github.com/mBlomsterberg/">
    <picture>
      <source srcset="../logo_inv.svg" media="(prefers-color-scheme: dark)">
      <img src="../logo.svg" alt="Logo" width="200" height="200">
    </picture>
  </a>

  <h3 align="center">HTML used in markdown</h3>

  <p align="center">
    With links.
    <br />
    <br />
    <a href="https://github.com/mBlomsterberg/github-cheatsheet/blob/main/workflows/README.md">Module Examples</a>
    ·
    <a href="https://github.com/mBlomsterberg/github-cheatsheet/blob/main/markdown/README.md">Versioning</a>
  </p>
  <br />
</div>

<div align="center">
<img src="https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white"> <img src="https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white"> 
</div>
```

<br/>
<div id="readme-top" align="center">
  <a href="https://github.com/mBlomsterberg/">
    <picture>
      <source srcset="../logo_inv.svg" media="(prefers-color-scheme: dark)">
      <img src="../logo.svg" alt="Logo" width="200" height="200">
    </picture>
  </a>

  <h3 align="center">HTML used in markdown</h3>

  <p align="center">
    With some links.
    <br/>
    <br/>
    <a href="https://github.com/mBlomsterberg/github-cheatsheet/blob/main/workflows/README.md">Readme</a>
    ·
    <a href="https://github.com/mBlomsterberg/github-cheatsheet/blob/main/markdown/README.md">Readme</a>
  </p>
  <br/>
</div>

<div align="center">
<img src="https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white"> <img src="https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white"> 
</div>


<br/>
