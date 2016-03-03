# แหล่งศึกษาที่อื่น ๆ

 * [ITCSS](https://speakerdeck.com/dafed/managing-css-projects-with-itcss#49) ("Inverted Triangle CSS") เป็นแนวทางการสร้าง component ที่ดีสำหรับใช้ใน rscss structure.
 * [rsjs](http://ricostacruz.com/rsjs/) ("Reasonable Standard of JavaScript Structure") กำลังพัฒนาเอกสารในการออกแบบโครงสร้าง JavaScript สำหรับเว็บทั่วไป

แนวทางอื่น ๆ
---------------

### BEM
[BEM] ดูดีมาก จะมีข้อเสียที่ syntax ดูไม่ดี ตัว RSCSS ส่วนมากก็ทำตามแนวทาง BEM แต่ใช้ syntax ต่างออกไป

```html
<!-- BEM -->
<form class='site-search site-search--full'>
  <input  class='site-search__field' type='text'>
  <button class='site-search__button'></button>
</form>
```

```html
<!-- rscss -->
<form class='site-search -full'>
  <input  class='field' type='text'>
  <button class='button'></button>
</form>
```

## คำศํพท์ที่ใช้

หลายแนวคิดพยายามจะแก้ปัญหาเดียวกัน แต่ใช้วิธีต่างกันในการวางโครงสร้าง CSS

| RSCSS     | BEM      | SMACSS        |
| ---       | ---      | ---           |
| Component | Block    | Module        |
| Element   | Element  | Sub-Component |
| Layout    | ?        | Layout        |
| Variant   | Modifier | Sub-Module & State |

[BEM]: http://bem.info/
[Smacss]: https://smacss.com/
