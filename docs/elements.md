# Elements

Elements คือของที่อยู่ข้างใน component

![](images/component-elements.png)

## การตั้งชื่อ elements
Element ไหนที่อยู่ภายใต้ component ชื่อของ class ควรมีเพียง **หนึ่งคำ**

```scss
.search-form {
  > .field { /* ... */ }
  > .action { /* ... */ }
}
```

## Element selectors
ถ้าทำได้ให้ใช้ `>` สำหรับ child selector (element ที่ลึกลงไปแค่ชั้นเดียว) เพื่อป้องกันไม่ให้มันไปเลือก component ลึก ๆ และช่วยให้ได้ประสิทธิภาพดีกว่าด้วย

```scss
.article-card {
  .title     { /* okay */ }
  > .author  { /* ✓ better */ }
}
```

## ถ้าต้องใช้หลายคำ
สำหรับชื่อ class ที่ต้องยาวสองคำหรือมากกว่า ให้เอาคำมาต่อกันเลย โดยไม่ต้องมีเส้นกลางหรือเส้นใต้

```scss
.profile-box {
  > .firstname { /* ... */ }
  > .lastname { /* ... */ }
  > .avatar { /* ... */ }
}
```

## ระวังการใช้ tag selectors
ให้ใช้ classname ไว้ก่อน ถึงแม้การใช้ Tag selectors จะใช้ได้เหมือนกัน บางทีอาจจะมีปัญหาเรื่องประสิทธิภาพเล็กน้อย ตามมาโดยไม่รู้ตัว

```scss
.article-card {
  > h3    { /* ✗ avoid */ }
  > .name { /* ✓ better */ }
}
```

Element เดียวกัน ก็ใช่ว่าจะหน้าตาเหมือนกันหมด ให้ใช้ Variants ช่วย
[ดูต่อ →](variants.md)
<!-- {p:.pull-box} -->
