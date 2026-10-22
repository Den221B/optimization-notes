---
пройдено: false
экзамен: понимание
---
# С4-4 Нерастягиваемость prox

> [!question] Условие · семинар 4, [[OptChapter_Sem4_slides.pdf#page=14|сл. 14–16]]
> $g : \mathbb R^n \to (-\infty, +\infty]$ — собственная замкнутая выпуклая функция, $\alpha > 0$. Используя характеристику $u = \operatorname{prox}_{\alpha g}(x) \iff \frac{x - u}{\alpha} \in \partial g(u)$, докажите, что для любых $x, y$
> $$\|\operatorname{prox}_{\alpha g}(x) - \operatorname{prox}_{\alpha g}(y)\| \le \|x - y\|,$$
> а по дороге — более сильное неравенство $\|u - v\|^2 \le \langle u - v, x - y \rangle$, где $u = \operatorname{prox}_{\alpha g}(x)$, $v = \operatorname{prox}_{\alpha g}(y)$.

> [!success]- Итог семинара — открыть после своей попытки
> Монотонность субдифференциала: для $p \in \partial g(u)$, $q \in \partial g(v)$ сложение двух субградиентных неравенств даёт $\langle p - q, u - v \rangle \ge 0$. Подставляем $p = \frac{x - u}{\alpha}$, $q = \frac{y - v}{\alpha}$: $\langle x - y - (u - v), u - v \rangle \ge 0$, то есть $\|u - v\|^2 \le \langle u - v, x - y \rangle$. По Коши–Буняковскому $\le \|u - v\| \|x - y\|$; при $u \ne v$ делим на $\|u - v\|$.


<!-- exam:auto:start -->
**Экзамен:** практика [[Э17 Проксимальный оператор|Э17]], [[Э19 Сходимость проксимального градиента|Э19]]
<!-- exam:auto:end -->

---

> [!quote]- Мои заметки
> **Метод в одну строку:**
> 
> **Опирается на:**
