---
пройдено: false
экзамен: понимание
---
# С1-4 Log-sum-exp

> [!question] Условие · семинар 1, [[OptChapter_Sem1_slides.pdf#page=15|сл. 15–20]]
> $f(x) = \log \sum_{i=1}^n e^{x_i}$. (a) Найдите $\nabla f$. (b) Найдите $\nabla^2 f$. (c) Докажите, что $f$ выпукла.

> [!success]- Итог семинара — открыть после своей попытки
> $\nabla f = p$, $p_i = e^{x_i} / \sum_j e^{x_j}$ (softmax). $\nabla^2 f = \operatorname{Diag}(p) - p p^\top$. $v^\top \nabla^2 f \, v = \sum_i p_i (v_i - \bar v)^2 \ge 0$, где $\bar v = \sum_i p_i v_i$, — это дисперсия. Гессиан вырожден: $\nabla^2 f \, \mathbf 1 = 0$, потому что $f(x + c \mathbf 1) = f(x) + c$.


<!-- exam:auto:start -->
**Экзамен:** практика [[Э03 Критерий выпуклости второго порядка|Э03]]
<!-- exam:auto:end -->

---

> [!quote]- Мои заметки
> **Метод в одну строку:**
> 
> **Опирается на:**
