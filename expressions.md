# Работа с выражениями (Expression)

## Особенности работы с выражениями

В рамках работы с выражениями через Expressions и Carrot Scripts поддерживаются следующие методы:

| Global             | Other Math                | Comp             | Footage             | Property | Layer Sub-objects  | Layer General   | Layer Properties | Layer 3D          |
|:-------------------|:--------------------------|:-----------------|:--------------------|:---------|:-------------------|:----------------|:-----------------|:------------------|
| comp      (name)   | degreesToRadians(degrees) | Comp.layer(index)| Footage.width       | value    | Layer.effect(name) | Layer.width     | Layer.anchorPoint| Layer.orientation |
| footage   (name)   | radiansToDegrees(radians) | Comp.layer(name) | Footage.height      |          | Layer.effect(index)| Layer.height    | Layer.position   | Layer.rotationX   |
| thisProject        |                           | Comp.width       | Footage.duration    |          |                    | Layer.index     | Layer.scale      | Layer.rotationY   |
| thisComp           |                           | Comp.height      | Footage.pixelAspect |          |                    | Layer.parent    | Layer.rotation   | Layer.rotationZ   |
| thisLayer          |                           | Comp.duration    | Footage.name        |          |                    | Layer.hasParent | Layer.opacity    |                   |
| thisProperty       |                           | Comp.name        |                     |          |                    | Layer.inPoint   | Layer.name       |                   |
| time               |                           |                  |                     |          |                    | Layer.outPoint  |                  |                   |
| value              |                           |                  |                     |          |                    | Layer.startTime |                  |                   |

**Text:**

Text.Font - используйте TextSource.FontSize, т.к. Carrot использует свой метод отрисовки текста.

Поддержка остальных методов не гарантируется, но возможна после обращения в техническую поддержку.

Для выражений используется логика и синтаксис аналогично JavaScript Expression Engine, которая отличается от ExtendScript, который может быть выставлен по умолчанию.

![AE_ExtendScript](_images/image11.png "ExtendScript")

Подробнее по [ссылке.](https://helpx.adobe.com/au/after-effects/using/legacy-and-extend-script-engine.html)

---

**Особенности метрических систем Adobe After Effects и Carrot Engine/Unreal Engine!**

SourceRectAtTime.width (получение ширины слоя в пикселях), применяемый к текстовому слою вернет в Carrot значение аналогично AE (1000), если применять фунцию к Solid слою, вернется значение в 1000 меньше (0,5 вместо 500), соответственно расчёты станут неверными, если не делать доп преобразований. Для необходимости сопоставления объектов с трекинг данными от трекинг систем (stYpe, MoSys и т.д.) в Carrot используется преобразование входящих значений в unit, где 1 unit = 1/1000px (система измерения AE). Это преобразование не касается Text Layer. На производительность влияет по большей части не содержание выражений, а их количество в проекте.



| Layer Sub-objects  | Layer General   | Layer Properties | Layer 3D          |
|:-------------------|:----------------|:-----------------|:------------------|
| Layer.effect(name) | Layer.width     | Layer.anchorPoint| Layer.orientation |
| Layer.effect(index)| Layer.height    | Layer.position   | Layer.rotationX   |
|                    | Layer.index     | Layer.scale      | Layer.rotationY   |
|                    | Layer.parent    | Layer.rotation   | Layer.rotationZ   |
|                    | Layer.hasParent | Layer.opacity    |                   |
|                    | Layer.inPoint   | Layer.name       |                   |
|                    | Layer.outPoint  |                  |                   |
|                    | Layer.startTime |                  |                   |

---

[Вернуться на прошлую страницу](user-guide.md)