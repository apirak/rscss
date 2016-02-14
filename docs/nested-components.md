# components ที่ซ้อนกัน

![](images/component-nesting.png)

```html
<div class='article-link'>
  <div class='vote-box'>
    ...
  </div>
  <h3 class='title'>...</h3>
  <p class='meta'>...</p>
</div>
```

บางทีมันจำเป็นที่ต้องให้ components กัน มาลองดูแนวทางการเขียน

## Variants

แต่ละ component อาจจะต้องแสดงผลต่างออกไปเมือนมันไปอยู่ใน component อื่น ให้ระวังการแก้ไข component นั้นโดยการอ้างอิงผ่าน component ที่อยู่ด้านนอก

```scss
.article-header {
  > .vote-box > .up { /* ✗ ระวังแบบนี้ */ }
}
```

แทนที่จะทำแบบนั้น ให้ใช้วิธีเพิ่ม variant เข้าไป แล้วใช้มันที่ component ด้านใน

```html
<div class='article-header'>
  <div class='vote-box -highlight'>
    ...
  </div>
  ...
</div>
```

```scss
.vote-box {
  &.-highlight > .up { /* ... */ }
}
```

## การทำให้ components หลายชั้น ดูง่ายขึ้น
บางครั้ง การซ้อน components จะทำให้ HTML ดูรก

```html
<div class='search-form'>
  <input class='input' type='text'>
  <button class='search-button -red -large'></button>
</div>
```
เราสามารถทำให้มันอ่านง่ายขึ้นได้ด้วยการใช้เทคนิค `@extend` ใน CSS preprocessor ของเรา

```html
<div class='search-form'>
  <input class='input' type='text'>
  <button class='submit'></button>
</div>
```

```scss
.search-form {
  > .submit {
    @extend .search-button;
    @extend .search-button.-red;
    @extend .search-button.-large;
  }
}
```

What about repeating elements like lists? Learn about Layouts.
แล้ว element ที่ซ้ำกันเยอะ ๆ เช่นการสร้างรายการละ? ลองศึกษาการเขียน Layouts

[ดูต่อ →](layouts.md)
<!-- {p:.pull-box} -->
