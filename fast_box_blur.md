## Fast Box Blur особенности и ограничения

Доступный для изменения параметр **Fast Box Blur** в **Carrot** — **Blur** **Radius**, остальные параметры эффекта фиксированные:
- Repeat Edge Pixels – On,
- Iterations - 3,
- Blur Dimensions – Horizontal and Vertical.

---

- *При необходимости работы с Track Matte со слоем, к которому применён Fast Box Blur, данный слой предварительно переносится в Precomposition.*
- *Для корректной работы Fast Box Blur должен находится первым в списке эффектов на слое. Аналогичным, но не предпочтительным, способом можно разместить слой с другими эффектами в Precomposition, на который уже применить Fast Box Blur.*

---

[Вернуться на прошлую страницу](effects.md)