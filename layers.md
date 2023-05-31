# **Работа со слоями**

## Поддерживаемые типы слоев

**Carrot Engine** поддерживает следующие типы слоев из **After Effects** при экспорте с помощью **Carrot AE Plugin**:

### Null Layer

Работает аналогично **AE**, к нему можно парентить другие слои, анимировать и применять эффекты, использовать в эскпрешенах и т.д. 

![AE_Null Layer](_images/image101.png "Null Layer")

---

### Solid Layer
   Аналогично **АЕ**. Отличие только в том, что в **Carrot** этот тип слоя рисуется в режиме **Bicubic sampling** (*пример на рис. ниже*)

   ![AE_CARROT_Solid Layer](_images/image12.png "AE_CARROT_Solid Layer")

---

### Shape Layer
   Для работы с **Shape Layers** их необходимо перед экспортом из After Effects в Carrot конвертировать в **кривые Безье**

   ![AE_BezierPath](_images/image13.png "Convert to Bezier Path")

   Поддерживается **Stroke** со скругленными краями, с возможностью редактирования толщины обводки (*Stroke Width*) и применения сплошной заливки (*Fill*)

   ![AE_Stroke](_images/image14.png "Stroke")

   Для применения масок на слое **Shape** необходимо предварительно переместить данный слой в **Precomposition** или использовать **Track Matte**
   
   ![AE_Carrot_Masks](_images/image15.png "AE_Carrot_Masks") 

   Векторные слои имеют ограничения по размеру композиции. Это нужно учитывать при построении архитектуры композиции. Для работы в режиме реального времени векторный слой растрируется и его **масштабирование более 100% может вызвать появление артефактов**. Аналогичным образом слой может обрезаться по границе композиции при масштабировании.

   ![AE_Carrot_Scale](_images/image16.png "AE_Carrot_Scale")

---

### Text Layer
   **Поддерживаемые параметры текстового слоя:**
   - Поддерживаемый кернинг — **Metrics**
   - Поддерживаются: гарнитура, стиль, толщина, межстрочное и межсимвольное расстояние, капитализация текста, выравнивание.
   - Не импортируются: для **point text** переносы текста (*расставленные в After Effect*), посимвольные эффекты (*Text Animator*).
   - При работе с текстовыми блоками необходимо учитывать что для отображений всего текстового блока в *Carrot* используется стиль первого символа этого блока

   ![AE_Carrot_Text Layer](_images/image17.png "AE_Carrot_Text Layer")

---

### Media Layer
   Для циклического воспроизведения видео в **Carrot** нужно указать **Loop Times больше 1**

   ![AE_InterpretFootage](_images/image18.png "Interpret Footage")
   ![AE_Loop Times](_images/image19.png "Loop Times")
   
   Важно учитывать **Frame Rate** шаблона и тракта (*настроенного в Carrot Flow Chart*), проигрывание всей медиа будет происходить с этим **FPS** (*ускорение или замедление при несоответствии Frame Rate*)

   ![AE_FrameRate](_images/image110.png "Frame Rate")

---

### 3D слои

**Carrot Engine** считывает систему измерений из **After Effects** в **миллиметрах**, 

*1000px в After Effects = 1000mm в Carrot Engine*

![AE_Distance](_images/image111.png "Distance")
![AE_Distance](_images/image112.png "Distance")
![AE_Distance](_images/image113.png "Distance")
![AE_Distance](_images/image114.png "Distance")

---
---

## Эффекты наложения слоев и Track Matte

- Track Matte (Подложки отслеживания);
- Parent Link к другому слою или его свойствам (Привязка);
- Blending Modes (Режимы наложения).

---

### Поддерживаемые типы наложений слоев и их особенности

| Поддерживаемые режимы наложения из AE в данный момент | Ограниченная поддержка (результат может отличаться от After Effects) |
|:-----------------------------------------------------:|:--------------------------------------------------------------------:|
|  Linear Color | Pin Light |
| Silhouette Alpha | Hard Mix |
| Screen | Linear Light |
| Add | Difference |
| Lighten | Classic Color Dodge |
| Dissolve | Exclusion |
| Dancing Dissolve | Subtract |
| Darken | Divide |
| Multiply | Hue |
| Color Burn | Saturation |
| Linear Burn | Color |
| Darker Color | Luminosity |
| Linear Dodge | Stencil Alpha |
| Lighter Color | Stencil Luma |
| Soft Light | Silhouette Luma |
| Color Dodge | Classic Color Burn |
| Vivid Light | Lighter Color Dodge |
| | Hard Light |
| | Overlay |

---
---

## Работа с масками слоев

Ограничения при работе с Масками Слоёв:

- При булевых операция с масками, тип Intersect не должен идти первым. В этом случае, первую маску в режиме Intersect следует поменять на Add.
![AE_Carrot_Intersect](_images/image115.png "Intersect")
- Мask Feather использует исключительно билинейную интерполяцию (важно учитывать при масках с острыми углами и высоким значением Feather).
- Отрицательное значение свойства Мask Expansion использует проприетарный алгоритм отличный от After Effects, результат необходимо контролировать в Template Preview.
- Тип маски None в Carrot делает весь слой невидимым.
![AE_Carrot_None](_images/image116.png "Mask - None")

---
---

## Анимация слоев

Необходимо ставить ключи анимации на всех вложенных композициях, иначе содержимое не будет обновляться при воспроизведении в Carrot. Более подробно о подготовке ключей анимации при экспорте шаблонов в Сarrot [читайте в п. 7.1.](export.md)

![AE_Keys](_images/image117.png "Keys")

---

[Вернуться на прошлую страницу](user-guide.md)