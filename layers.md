# Работа со слоями
## Поддерживаемые типы слоев
---
Carrot Engine поддерживает следующие типы слоев из After Effects при экспорте с помощью Carrot AE Plugin:

 - <details>
   <summary><b>Null Layer</b></summary>
   <p>Работает аналогично AE, к нему можно парентить другие слои, анимировать и применять эффекты, использовать в эскпрешенах и т.д. <div align="center"><img src="_images/image11.png" alt="AE_Null Layer" title="Null Layer" width="500"></div></p>
   </details>

 - <details>
   <summary><b>Solid Layer</b></summary>
   <p>
   Аналогично АЕ. Отличие только в том, что в Carrot этот тип слоя рисуется в режиме bicubic sampling 
   <em>(пример на рис. ниже)</em>
   <div align="center"><img src="_images/image11.png" alt="AE_Solid Layer" title="Solid Layer_AE" width="500">
   <img src="_images/image11.png" alt="Carrot_Solid Layer" title="Solid Layer_Carrot" width="500"></div>
   </p>
   </details>

 - <details>
   <summary><b>Shape Layer</b></summary> 
   Для работы с Shape Layers их необходимо перед экспортом из After Effects в Carrot конвертировать в кривые Безье
   <p><div align="center"><img src="_images/image11.png" alt="AE_BezierPath" title="Convert to Bezier Path" width="500"></div></p>

   Поддерживается Stroke со скругленными краями, с возможностью редактирования толщины обводки (Stroke Width) и применения сплошной заливки (Fill)
   <p><div align="center"><img src="_images/image11.png" alt="AE_Stroke" title="Stroke" width="500"></div>
   </p>

   Для применения масок на слое Shape необходимо предварительно переместить данный слой в Precomposition или использовать Track Matte
   <p><div align="center"><img src="_images/image11.png" alt="AE_Masks" title="Masks_AE" width="500">
   <img src="_images/image11.png" alt="Carrot_Masks" title="Masks_Carrot" width="500"></div>
   </p>

   Векторные слои имеют ограничения по размеру композиции. Это нужно учитывать при построении архитектуры композиции. Для работы в режиме реального времени векторный слой растрируется и его масштабирование более 100% может вызвать появление артефактов. Аналогичным образом слой может обрезаться по границе композиции при масштабировании.
   <p><div align="center"><img src="_images/image11.png" alt="AE_Scale" title="Scale_AE" width="500">
   <img src="_images/image11.png" alt="Carrot_Scale" title="Scale_Carrot" width="500"></div>
   </p>
   </details>

 - <details>
   <summary><b>Text Layer</b></summary>
   <b>Поддерживаемые параметры текстового слоя:</b>
   <ul>
   <li>Поддерживаемый кернинг — Metrics</li>
   <li>Поддерживаются: гарнитура, стиль, толщина, межстрочное и межсимвольное расстояние, капитализация текста, выравнивание.</li>
   <li>Не импортируются: для point text переносы текста (расставленные в After Effect), посимвольные эффекты (Text Animator).</li>
   <li>При работе с текстовыми блоками необходимо учитывать что для отображений всего текстового блока в Carrot используется стиль первого символа этого блока</li>
   </ul>

   <p><div align="center"><img src="_images/image11.png" alt="AE_Text Layer" title="Text Layer_AE" width="500">
   <img src="_images/image11.png" alt="Carrot_Text Layer" title="Text Layer_Carrot" width="500"></div>
   </p>
 
 - <details>

   <summary><b>Media Layer</b></summary>
   Для циклического воспроизведения видео в Carrot нужно указать Loop Times больше 1
   <p><div align="center"><img src="_images/image11.png" alt="AE_InterpretFootage" title="Interpret Footage" width="500"></div></p>
   <p><div align="center"><img src="_images/image11.png" alt="AE_Loop Times" title="Loop Times" width="500"></div></p>
   Важно учитывать Frame Rate шаблона и тракта (настроенного в Carrot Flow Chart), проигрывание всей медиа будет происходить с этим FPS (ускорение или замедление при несоответствии Frame Rate)
   <p><div align="center"><img src="_images/image11.png" alt="AE_FrameRate" title="Frame Rate" width="500"></div></p>

   </details>

> ### **3D слои**
> Carrot Engine считывает систему измерений из After Effects в миллиметрах, 
> #### *1000px в After Effects = 1000mm в Carrot Engine*
<p><div align="center">
<img src="_images/image11.png" alt="AE_FrameRate" title="Frame Rate" width="375">
<img src="_images/image11.png" alt="AE_FrameRate" title="Frame Rate" width="375">
<img src="_images/image11.png" alt="AE_FrameRate" title="Frame Rate" width="375"></div></p>

[Вернуться на прошлую страницу](user-guide.md)

