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

If you need to define these, try to define them in whatever context they will be in. In this example below, notice that the widths and floats are applied on the *list* component, not the component itself.

ถ้าต้องกำหนดตำแหน่ง พยายามเขียนให้อยู่ในบริบทที่มันอยู่ เช่น ในตัวอย่างข้างล่าง เราอ่านแล้วจะเดารู้เลยว่า width และ float เกิดขึ้นเฉพาะใน *list* ไม่เกี่ยวกับ component card

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
[ดูต่อ →](helpers.md)
<!-- {p:.pull-box} -->
