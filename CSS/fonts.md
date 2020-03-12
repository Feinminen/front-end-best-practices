1. **Если клиент предоставил макеты с кастомными шрифтами - проверить, свободные ли они и если нет, то запросить купленные файлы шрифтов**;

2. **Шрифты должны быть в форматах  `.ttf`, `.woff`, `.svg`, для их генерации воспользуйтесь [Font Squirrel](https://www.fontsquirrel.com/)**;

3. **Если в проекте должна быть поддержка нелатинских символов (например, русских), проверьте, что в файле шрифта эти символы есть и при генерации через [Font Squirrel](https://www.fontsquirrel.com/) обязательно укажите поддержку этих subsettings**;

4. **Разные начертания одного и того же шрифта подключайте под одним именем, но для разных `font-weight` и `font-style`**;
      > ```css
      > @font-face {
      >  font-family: "Lato";
      >  src: url("../fonts/lato-regular.woff2") ...;  /* Pay attention: font is regulat and "..." replaced for other formats */
      >  font-weight: 400;
      >  font-style: normal; 
      >}
      >@font-face {
      >  font-family: "Lato";
      >  src: url("../fonts/lato-italic.woff2") ...;  /* Pay attention: font is regular italic and "..." replaced for other formats */
      >  font-weight: 400;
      >  font-style: italic; 
      >}
      >@font-face {
      >  font-family: "Lato"; 
      >  src: url("../fonts/lato-light.woff2") ...;  /* Pay attention: font is light and "..." replaced for other formats */
      > font-weight: 300;
      >  font-style: normal; 
      >}
      >@font-face {
      >  font-family: "Lato";
      >  src: url("../fonts/lato-lightitalic.woff2") ...;  /* Pay attention: font is light italic and "..." replaced for other formats */
      >  font-weight: 300;
      >  font-style: italic; 
      >}
    >```

6. **Всегда использовать как минимум один запасной шрифт и одно запасное семейство**;
    > Их перечисляют через запятую в `font-family`, так что каждое использование `font-family` должно проиходить по схеме
    >`font-family: Helvetica, Arial, sans-serif;`

    > Здесь `Helvetica` - нестандартный подключаемый шрифт

    > `Arial` - стандартный шрифт, который используется почти на всех клиентах, он будет использоваться, если не удалось подключить `Helvetica`.

    > `sans-serif` - это семейство всех шрифтов без засечек (каковыми являются и `Helvetica` и `Arial`). Если даже `Arial-а` на компе нет, то поставится какой-то системный дефолтный шрифт без засечек. Выбор здесь надо делать из `"serif,"` `"sans-serif,"` или `"monospace"`.  Для шрифтов без засечек использовать по умолчанию `Arial`, для шрифтов с засечками `Georgia` (А не `Times New Roman`), а для моноширинных `"Courier New"`

7. **Названия шрифтов, содержащие пробелы, цифры или знаки пунктуации кроме дефисов заключать в кавычки**;
    > quote font family names that contain white space, digits, or punctuation characters other than hyphens

    > Пример:
    >  ```css
    >  .font-family: "Times New Roman", serif.
    >  ```
