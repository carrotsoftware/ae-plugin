# <b>Работа со слоями</b>
## <b>Поддерживаемые типы слоев</b>
---
<b>Carrot Engine</b> поддерживает следующие типы слоев из <b>After Effects</b> при экспорте с помощью <b>Carrot AE Plugin</b>:

 - <details>
   <summary><b>Null Layer</b></summary>
   <p>Работает аналогично <b>AE</b>, к нему можно парентить другие слои, анимировать и применять эффекты, использовать в эскпрешенах и т.д. <div align="center"><img src="_images/image11.png" alt="AE_Null Layer" title="Null Layer" width="400"></div></p>
   </details>

 - <details>
   <summary><b>Solid Layer</b></summary>
   <p>
   Аналогично <b>АЕ</b>. Отличие только в том, что в <b>Carrot</b> этот тип слоя рисуется в режиме <b>Bicubic sampling</b> 
   <em>(пример на рис. ниже)</em>
   <div align="center"><img src="_images/image11.png" alt="AE_Solid Layer" title="Solid Layer_AE" width="400">
   <img src="_images/image11.png" alt="Carrot_Solid Layer" title="Solid Layer_Carrot" width="400"></div>
   </p>
   </details>

 - <details>
   <summary><b>Shape Layer</b></summary> 
   Для работы с <b>Shape Layers</b> их необходимо перед экспортом из After Effects в Carrot конвертировать в <b>кривые Безье</b>
   <p><div align="center"><img src="_images/image11.png" alt="AE_BezierPath" title="Convert to Bezier Path" width="400"></div></p>

   Поддерживается <b>Stroke</b> со скругленными краями, с возможностью редактирования толщины обводки (<em>Stroke Width</em>) и применения сплошной заливки (<em>Fill</em>)
   <p><div align="center"><img src="_images/image11.png" alt="AE_Stroke" title="Stroke" width="400"></div>
   </p>

   Для применения масок на слое <b>Shape</b> необходимо предварительно переместить данный слой в <b>Precomposition</b> или использовать <b>Track Matte</b>
   <p><div align="center"><img src="_images/image11.png" alt="AE_Masks" title="Masks_AE" width="400">
   <img src="_images/image11.png" alt="Carrot_Masks" title="Masks_Carrot" width="400"></div>
   </p>

   Векторные слои имеют ограничения по размеру композиции. Это нужно учитывать при построении архитектуры композиции. Для работы в режиме реального времени векторный слой растрируется и его <b>масштабирование более 100% может вызвать появление артефактов</b>. Аналогичным образом слой может обрезаться по границе композиции при масштабировании.
   <p><div align="center"><img src="_images/image11.png" alt="AE_Scale" title="Scale_AE" width="400">
   <img src="_images/image11.png" alt="Carrot_Scale" title="Scale_Carrot" width="400"></div>
   </p>
   </details>

 - <details>
   <summary><b>Text Layer</b></summary>
   <b>Поддерживаемые параметры текстового слоя:</b>
   <ul>
   <li>Поддерживаемый кернинг — <b>Metrics</b></li>
   <li>Поддерживаются: гарнитура, стиль, толщина, межстрочное и межсимвольное расстояние, капитализация текста, выравнивание.</li>
   <li>Не импортируются: для <b>point text</b> переносы текста (<em>расставленные в After Effect</em>), посимвольные эффекты (<em>Text Animator</em>).</li>
   <li>При работе с текстовыми блоками необходимо учитывать что для отображений всего текстового блока в <b>Carrot</b> используется стиль первого символа этого блока</li>
   </ul>

   <p><div align="center"><img src="_images/image11.png" alt="AE_Text Layer" title="Text Layer_AE" width="400">
   <img src="_images/image11.png" alt="Carrot_Text Layer" title="Text Layer_Carrot" width="400"></div>
   </p>
 
 - <details>

   <summary><b>Media Layer</b></summary>
   Для циклического воспроизведения видео в <b>Carrot</b> нужно указать <b>Loop Times больше 1</b>
   <p><div align="center"><img src="_images/image11.png" alt="AE_InterpretFootage" title="Interpret Footage" width="400"></div></p>
   <p><div align="center"><img src="_images/image11.png" alt="AE_Loop Times" title="Loop Times" width="400"></div></p>
   Важно учитывать <b>Frame Rate</b> шаблона и тракта (<em>настроенного в Carrot Flow Chart</em>), проигрывание всей медиа будет происходить с этим <b>FPS</b> (<em>ускорение или замедление при несоответствии Frame Rate</em>)
   <p><div align="center"><img src="_images/image11.png" alt="AE_FrameRate" title="Frame Rate" width="400"></div></p>

   </details>

> ### **3D слои**
> <b>Carrot Engine</b> считывает систему измерений из <b>After Effects</b> в <b>миллиметрах</b>, 
> #### *1000px в After Effects = 1000mm в Carrot Engine*
<p><div align="center">
<img src="_images/image11.png" alt="AE_FrameRate" title="Frame Rate" width="300">
<img src="_images/image11.png" alt="AE_FrameRate" title="Frame Rate" width="300">
<img src="_images/image11.png" alt="AE_FrameRate" title="Frame Rate" width="300"></div></p>

[Вернуться на прошлую страницу](user-guide.md)

