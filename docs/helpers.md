# Helpers

โดยทั่วไป class เหล่านี้จะหมายถึงการแทนที่ค่าบางอย่าง ให้เราแยกไฟล์ออกไป แลัวตั้งชื่อนำหน้าด้วยขีดล่าง class พวกนี้มักจะใส่ *!important* ไว้ด้วย ให้พยายามใช้เฉพาะที่จำเป็นจริง ๆ

```css
._unmargin { margin: 0 !important; }
._center { text-align: center !important; }
._pull-left { float: left !important; }
._pull-right { float: right !important; }
```

## การตั้งชื่อ helpers

ให้นำหน้าชื่อด้วยขีดล่าง จะช่วยให้เรามองออกอย่างรวดเร็วว่ามันไม่ได้เป็นส่วนกำหนดรูปแบบของ component นอกจากนั้นขีดล่างยังดูไม่สวยงาม ช่วยให้เราไม่อยากใช้มันบ่อย ๆ

  ```html
  <div class='order-graphs -slim _unmargin'>
  </div>
  ```

## การจัดระเบียบ helpers

รวบรวม helpers ไว้เป็นไฟล์เดียว ตั้งชื่อว่า `helpers` แทนที่จะแยกมันเป็นหลายไฟล์ จะช่วยให้เรารักษาจำนวน helpers ให้มีอยู่น้อยที่สุด ไปในตัว
