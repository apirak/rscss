# โครงสร้าง CSS

## หนึ่ง component ต่อหนึ่งไฟล์
แต่ละ component ให้วางมันไว้ในไฟล์ของตัวเอง

  ```scss
  /* css/components/search-form.scss */
  .search-form {
    > .button { /* ... */ }
    > .field { /* ... */ }
    > .label { /* ... */ }

    // variants
    &.-small { /* ... */ }
    &.-wide { /* ... */ }
  }
  ```

## Use glob matching
ถ้าใช้ sass-rails และ stylus จะทำให้รวบรวมไฟล์ทั้งหมดได้ง่าย

  ```scss
  @import 'components/*';
  ```

## Avoid over-nesting
## ระวังการซ้อนกันมากไป
ไม่ควรให้ซ่อนกันเกิน 1 ชั้น เพื่อป้องกันการซ้อนกันมากเกินไปโดยไม่รู้ตัว

  ```scss
  /* ✗ Avoid: 3 levels of nesting */
  .image-frame {
    > .description {
      /* ... */

      > .icon {
        /* ... */
      }
    }
  }

  /* ✓ Better: 2 levels */
  .image-frame {
    > .description { /* ... */ }
    > .description > .icon { /* ... */ }
  }
  ```
