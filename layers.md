# **1. Работа со слоями**

## 1.1. Поддерживаемые типы слоев

**Carrot Engine** поддерживает следующие типы слоев из **After Effects** при экспорте с помощью **Carrot AE Plugin**:

### 1.1.1. Null Layer

Работает аналогично **AE**, к нему можно парентить другие слои, анимировать и применять эффекты, использовать в эскпрешенах и т.д. 

![AE_Null Layer](_images/image101.jpg "Null Layer")

---

### 1.1.2. Solid Layer
   Аналогично **АЕ**. Отличие только в том, что в **Carrot** этот тип слоя рисуется в режиме **Bicubic sampling** (*пример на рис. ниже*)

   ![AE_CARROT_Solid Layer](_images/image102.jpg "Solid Layer")

---

### 1.1.3. Shape Layer
   Для работы с **Shape Layers** их необходимо перед экспортом из After Effects в Carrot конвертировать в **кривые Безье**

   ![AE_BezierPath](_images/image103.jpg "Convert to Bezier Path")

   Поддерживается **Stroke** со скругленными краями, с возможностью редактирования толщины обводки (*Stroke Width*) и применения сплошной заливки (*Fill*)

   ![AE_Stroke](_images/image104.jpg "Stroke")

   Для применения масок на слое **Shape** необходимо предварительно переместить данный слой в **Precomposition** или использовать **Track Matte**
   
   ![AE_Carrot_Masks](_images/image105.jpg "AE_Carrot_Masks") 

   Векторные слои имеют ограничения по размеру композиции. Это нужно учитывать при построении архитектуры композиции. Для работы в режиме реального времени векторный слой растрируется и его **масштабирование более 100% может вызвать появление артефактов**. Аналогичным образом слой может обрезаться по границе композиции при масштабировании.

   ![AE_Carrot_Scale](_images/image106.jpg "AE_Carrot_Scale")

---

### 1.1.4. Text Layer

О работа с текстовыми блоками можно ознакомиться по [ссылке](texts.md)

---

### 1.1.5. Media Layer
   Для циклического воспроизведения видео в **Carrot** нужно указать **Loop Times больше 1**

   ![AE_InterpretFootage](_images/image107.jpg "Interpret Footage")
   ![AE_Loop Times](_images/image108.jpg "Loop Times")
   
   Важно учитывать **Frame Rate** шаблона и тракта (*настроенного в Carrot Flow Chart*), проигрывание всей медиа будет происходить с этим **FPS** (*ускорение или замедление при несоответствии Frame Rate*)

   ![AE_FrameRate](_images/image109.jpg "Frame Rate")

---

### 1.1.6. 3D слои

**Carrot Engine** считывает систему измерений из **After Effects** в **миллиметрах**, 

*1000px в After Effects = 1000mm в Carrot Engine*

![AE_Distance](_images/image110.jpg "Distance")
![AE_Distance](_images/image111.jpg "Distance")
![AE_Distance](_images/image112.jpg "Distance")
![AE_Distance](_images/image113.jpg "Distance")

---
---

## 1.2. Эффекты наложения слоев и Track Matte

- Track Matte (Подложки отслеживания);
- Parent Link к другому слою или его свойствам (Привязка);
- Blending Modes (Режимы наложения).

---

### 1.2.1. Поддерживаемые типы наложений слоев и их особенности

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

## 1.3. Работа с масками слоев

Ограничения при работе с Масками Слоёв:

- При булевых операция с масками, тип Intersect не должен идти первым. В этом случае, первую маску в режиме Intersect следует поменять на Add.

![AE_Carrot_Intersect](_images/image114_2.gif "Intersect")

- Мask Feather использует исключительно билинейную интерполяцию (важно учитывать при масках с острыми углами и высоким значением Feather).
- Отрицательное значение свойства Мask Expansion использует проприетарный алгоритм отличный от After Effects, результат необходимо контролировать в Template Preview.
- Тип маски None в Carrot делает весь слой невидимым.

![AE_Carrot_None](_images/image115.jpg "Mask - None")

---
---

## 1.4. Анимация слоев

Необходимо ставить ключи анимации на всех вложенных композициях, иначе содержимое не будет обновляться при воспроизведении в Carrot. Более подробно о подготовке ключей анимации при экспорте шаблонов в Сarrot [читайте в п. 7.1.](export.md)

![AE_Keys](_images/image116.jpg "Keys")

---

[Вернуться на прошлую страницу](user-guide.md)