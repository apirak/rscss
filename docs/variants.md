# Variants

Component ชื่อเดียวกันบางทีก็ไม่อยากให้เหมือนกัน Elements ก็เช่นกัน

![](images/component-modifiers.png)

<br>

## การตั้งชื่อ variants

ชื่อ class ของ variants ให้ขึ้นต้นด้วยขีดกลาง (`-`).

  ```scss
  .like-button {
    &.-wide { /* ... */ }
    &.-short { /* ... */ }
    &.-disabled { /* ... */ }
  }
  ```

## Element variants
Varants ของ element ก็ใช้รูปแบบเดียวกัน

  ```scss
  .shopping-card {
    > .title { /* ... */ }
    > .title.-small { /* ... */ }
  }
  ```

## ทำไมใช้ขีดกลางนำหน้า
เราอยากให้ใช้ขีดกลางนำหน้าสำหรับ variants เพราะ

  * มันช่วยให้เราไม่สับสนกับ elements
  * class ใน CSS สามารถนำหน้าได้ด้วยตัวอักษร `_` หรือ `-` เท่านั้น
  * ขีดกลางพิมพ์ง่ายกว่าขีดล่าง
  * มันเป็นรูปแบบเดียวกับ switches ใน UNIX command line (`gcc -O2 -Wall -emit-last`)

เราจะจัดการ element ที่ซับซ้อนอย่างไร? จับมันซ้อนกัน
[อ่านต่อ →](nested-components.md)
<!-- {p:.pull-box} -->
