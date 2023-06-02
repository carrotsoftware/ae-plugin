# 7. Экспорт шаблонов в Carrot

## 7.1. Подготовка проекта, сохранение, экспорт и настройка шаблона

1. Выберите меню **Composition - Export Carrot Template**.

![AE_Export Carrot Template](_images/image701.jpg "Export Carrot Template")

*Примечание: если этот пункт не активен, нажмите на раздел с композициями в нижней части интерфейса After Effects.*

![AE_Export Carrot Template](_images/image702.jpg "Export Carrot Template")

2. Появится окно **Template Preview**.

3. Откройте вкладку Animation в центральном разделе Viewport.

![AE_Template Preview](_images/image703.jpg "Template Preview")

4. В поле **Composition** выберите композицию, которая была экспортирована. Благодаря маркерам здесь появились три стейта:

![AE_Template Preview](_images/image704.jpg "Template Preview")

- IN (*соответствует промежутку OUT-IN*)
- ANIM (*соответствует промежутку IN-ANIM*)
- OUT (*соответствует промежутку ANIM-OUT*)

![AE_Template Preview](_images/image705.jpg "Template Preview")

5. Проверьте правильность воспроизведения анимации:
- Нажмите на название стейта.

![AE_Animation](_images/image706.jpg "Animation")

- Дождитесь завершения проигрывания.
6. Нажмите кнопку **Save Template**.

![AE_Save Template](_images/image707.jpg "Save Template")

7. В новом окне выберите директорию для сохранения шаблона.
8. В поле **Name** задайте название шаблона.
9. Нажмите на поле **Container**.
10. В появившемся окне выберите нужную схему движка и укажите
соответствующий контейнер ( [подробнее о контейнерах и схемах Carrot Engine](https://carrotsoftware.github.io/docs/#/settings?id=%d0%a0%d0%b0%d0%b7%d0%b4%d0%b5%d0%bb-engines) ).

![AE_Carrot Engine](_images/image708.jpg "Carrot Engine")

11. Нажмите на кнопку Save Template.
12. Закройте Template Preview.

---

## 7.2. Работа с текстом в Carrot. Настройки растеризации (StepCount) и вертикального выравнивания (VerticalAlignment).

1. Выберите текстовой слой.

![AE_Text Layer](_images/image709.jpg "Text Layer")

2. В разделе Properties измените параметр StepCount на желаемый:

![AE_StepCount](_images/image710.jpg "StepCount")

Примеры значений параметра StepCount:

StepCount = 1:

![AE_StepCount1](_images/image711.jpg "StepCount1")

StepCount = 2:

![AE_StepCount2](_images/image712.jpg "StepCount2")

StepCount = 4:

![AE_StepCount4](_images/image713.jpg "StepCount4")

>Примечание: чем больше значение параметра StepCount, тем больше потребляется ресурсов ГП на отрисовку текста.

В Carrot присутствует функционал вертикального выравнивания текстового блока, недоступный в After Effects. Выбор режима выравнивания происходит следующим образом:
1. Раскройте свойства текстового слоя
2. Выберите свойство Source Text
3. В окне Properties укажите параметр VerticalAlignment

![AE_Vertical Alignment](_images/image714.jpg "Vertical Alignment")

Сохранение параметра выравнивания текстового слоя не поддерживается.

---

[Вернуться на прошлую страницу](user-guide.md)