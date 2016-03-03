# Layouts

![](images/layouts.png)

## ระวังการกำหนด properties

Components ควรออกแบบให้สามารถใช้ช้ำได้ในหลากหลายบริบท ให้ระวังการกำหนด property เหล่านี้

  * Positioning (`position`, `top`, `left`, `right`, `bottom`)
  * Floats (`float`, `clear`)
  * Margins (`margin`)
  * Dimensions (`width`, `height`) *

## การกำหนดขนาดตายตัว

ให้ใช้เฉพาะ element ที่มีความกว้าง ความสูงแน่นอน อย่าง avatars หรือ logos

## กำหนดตำแหน่งตาม component ด้านนอก

ถ้าต้องกำหนดลักษณะให้อะไรควรเขียนให้อยู่ใต้บริบทที่มันอยู่ เช่นในตัวอย่างข้างล่าง เราอ่านแล้วจะเดาได้เลยว่า width และ float เกิดขึ้นเฉพาะใน *list* ไม่เกี่ยวกับ *card*

  ```css
  .article-list {
    & {
      @include clearfix;
    }

    > .article-card {
      width: 33.3%;
      float: left;
    }
  }

  .article-card {
    & { /* ... */ }
    > .image { /* ... */ }
    > .title { /* ... */ }
    > .category { /* ... */ }
  }
  ```

แล้วจะกำหนด margins นอก layout ได้อย่างไร? มาลองใช้ Helpers กัน
[อ่านต่อ →](helpers.md)
<!-- {p:.pull-box} -->
