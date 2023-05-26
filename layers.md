# <b>Работа со слоями</b>
## <b>Поддерживаемые типы слоев</b>

**Carrot Engine** поддерживает следующие типы слоев из **After Effects** при экспорте с помощью **Carrot AE Plugin**:

### **Null Layer**

Работает аналогично **AE**, к нему можно парентить другие слои, анимировать и применять эффекты, использовать в эскпрешенах и т.д. 

![AE_Null Layer](_images/image11.png "Null Layer")

### **Solid Layer**
   Аналогично **АЕ**. Отличие только в том, что в **Carrot** этот тип слоя рисуется в режиме **Bicubic sampling** (*пример на рис. ниже*)

   ![AE_Solid Layer](_images/image11.png "Solid Layer_AE")
   ![AE_Solid Layer](_images/image11.png "Solid Layer_Carrot")

### **Shape Layer**
   Для работы с **Shape Layers** их необходимо перед экспортом из After Effects в Carrot конвертировать в **кривые Безье**

   ![AE_BezierPath](_images/image11.png "Convert to Bezier Path")

   Поддерживается **Stroke** со скругленными краями, с возможностью редактирования толщины обводки (*Stroke Width*) и применения сплошной заливки (*Fill*)

   ![AE_Stroke](_images/image11.png "Stroke")

   Для применения масок на слое **Shape** необходимо предварительно переместить данный слой в **Precomposition** или использовать **Track Matte**
   
   ![AE_Masks](_images/image11.png "Masks_AE")
   ![Carrot_Masks](_images/image11.png "Masks_Carrot")   

   Векторные слои имеют ограничения по размеру композиции. Это нужно учитывать при построении архитектуры композиции. Для работы в режиме реального времени векторный слой растрируется и его **масштабирование более 100% может вызвать появление артефактов**. Аналогичным образом слой может обрезаться по границе композиции при масштабировании.

   ![AE_Scale](_images/image11.png "AE_Scale")
   ![Carrot_Scale](_images/image11.png "Carrot_Scale")  

### **Text Layer**
   **Поддерживаемые параметры текстового слоя:**
   - Поддерживаемый кернинг — **Metrics**
   - Поддерживаются: гарнитура, стиль, толщина, межстрочное и межсимвольное расстояние, капитализация текста, выравнивание.
   - Не импортируются: для **point text** переносы текста (*расставленные в After Effect*), посимвольные эффекты (*Text Animator*).
   - При работе с текстовыми блоками необходимо учитывать что для отображений всего текстового блока в *Carrot* используется стиль первого символа этого блока

   ![AE_Text Layer](_images/image11.png "Text Layer_AE")
   ![Carrot_Text Layer](_images/image11.png "Text Layer_Carrot")

### **Media Layer**
   Для циклического воспроизведения видео в **Carrot** нужно указать **Loop Times больше 1**

   ![AE_InterpretFootage](_images/image11.png "Interpret Footage")
   ![AE_Loop Times](_images/image11.png "Loop Times")
   
   Важно учитывать **Frame Rate** шаблона и тракта (*настроенного в Carrot Flow Chart*), проигрывание всей медиа будет происходить с этим **FPS** (*ускорение или замедление при несоответствии Frame Rate*)

   ![AE_FrameRate](_images/image11.png "Frame Rate")

### **3D слои**

**Carrot Engine** считывает систему измерений из **After Effects** в **миллиметрах**, 

*1000px в After Effects = 1000mm в Carrot Engine*

![AE_Distance](_images/image11.png "Distance")
![AE_Distance](_images/image11.png "Distance")
![AE_Distance](_images/image11.png "Distance")

[Вернуться на прошлую страницу](user-guide.md)

