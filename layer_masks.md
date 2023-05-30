## **Работа с масками слоев**

Ограничения при работе с Масками Слоёв:

- При булевых операция с масками, тип Intersect не должен идти первым. В этом случае, первую маску в режиме Intersect следует поменять на Add.
![AE_Intersect](_images/image11.png "Intersect")
![Carrot_Intersect](_images/image11.png "Intersect")
- Мask Feather использует исключительно билинейную интерполяцию (важно учитывать при масках с острыми углами и высоким значением Feather).
- Отрицательное значение свойства Мask Expansion использует проприетарный алгоритм отличный от After Effects, результат необходимо контролировать в Template Preview.
- Тип маски None в Carrot делает весь слой невидимым.
![AE_None](_images/image11.png "None")
![Carrot_None](_images/image11.png "None")

---

[Вернуться на прошлую страницу](layers.md)