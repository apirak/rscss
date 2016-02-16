# Pitfalls

## Bleeding through nested components
พึงระวังการใช้ components ซ้อนกัน เพราะอาจจะมี element ที่ใช้ชื่อเดียวกันอยู่ก็ได้

```html
<article class='article-link'>
  <div class='vote-box'>
    <button class='up'></button>
    <button class='down'></button>
    <span class='count'>4</span>
  </div>

  <h3 class='title'>Article title</h3>
  <p class='count'>3 votes</p>
</article>
```

```scss
.article-link {
  > .title { /* ... */ }
  > .count { /* ... (!!!) */ }
}

.vote-box {
  > .up { /* ... */ }
  > .down { /* ... */ }
  > .count { /* ... */ }
}
```

ในกรณีนี้ ถ้า `.article-link > .count` ไม่มี `>` (child selector) ค่านี้จะถูกนำไปใช้กับ element `.vote-box .count`  ด้วย นี่เป็นหนึ่งในเหตุผลที่อยากให้ใส่ child selector ไว้เสมอ
