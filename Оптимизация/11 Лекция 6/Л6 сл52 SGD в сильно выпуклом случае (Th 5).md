---
пройдено: false
экзамен: ответ
---
# Л6 сл52 SGD в сильно выпуклом случае (Th 5)

> [!abstract] Theorem 5 · [[OptChapter_Lecture6_slides.pdf#page=52|сл. 52–55]]
> Пусть $F$ $\mu$-сильно выпукла и $L$-гладка, $\mathbb E[g_k \mid x_k] = \nabla F(x_k)$, $\mathbb E[\|g_k - \nabla F(x_k)\|^2 \mid x_k] \le \sigma^2$. Выберем $c \ge 2L/\mu$ и $\alpha_k = \frac{2}{\mu (k + c)}$. Тогда
> $$\mathbb E[F(x_k) - F^\star] \le \frac{C}{k + c - 1}, \qquad C = \max\Big\{(c - 1)\big(F(x_0) - F^\star\big), \ \frac{2L\sigma^2}{\mu^2}\Big\};$$
> в частности, $\mathbb E[F(x_k) - F^\star] = O(1/k)$.
> **Доказательство.**
> 1. По $L$-гладкости $F(x_{k+1}) \le F(x_k) - \alpha_k \langle \nabla F(x_k), g_k \rangle + \frac{L\alpha_k^2}{2} \|g_k\|^2$. Условное ожидание и $\mathbb E[\|g_k\|^2 \mid x_k] \le \|\nabla F(x_k)\|^2 + \sigma^2$ дают $\mathbb E[F(x_{k+1}) - F^\star \mid x_k] \le F(x_k) - F^\star - \alpha_k \big(1 - \frac{L\alpha_k}{2}\big) \|\nabla F(x_k)\|^2 + \frac{L\alpha_k^2 \sigma^2}{2}$. Из $c \ge 2L/\mu$ следует $\alpha_k \le 1/L$.
> 2. Из сильной выпуклости $\|\nabla F(x)\|^2 \ge 2\mu \big(F(x) - F^\star\big)$, и для $a_k = \mathbb E[F(x_k) - F^\star]$: $a_{k+1} \le (1 - \mu\alpha_k)\, a_k + \frac{L\alpha_k^2 \sigma^2}{2}$.
> 3. Подстановка шага: $a_{k+1} \le \big(1 - \frac{2}{k + c}\big) a_k + \frac{B}{(k + c)^2}$, $B = \frac{2L\sigma^2}{\mu^2}$. Индукция: если $s = k + c$, $a_k \le \frac{C}{s - 1}$ и $C \ge \max\{(c - 1) a_0, B\}$, то $a_{k+1} \le \frac{s - 2}{s} \cdot \frac{C}{s - 1} + \frac{C}{s^2} \le \frac Cs$.

## На пальцах
«Монетка»: $\mu = L = 1$, $\sigma^2 = 1$. Берём $c = 2 = \frac{2L}{\mu}$, шаги $\alpha_k = \frac{2}{k + 2}$: $1, \frac23, \frac12, \frac25, \dots$
- Константа $C = \max\{F(x_0) - F^\star, 2\} = 2$ при $x_0 \in [-1, 3]$, и оценка $\mathbb E[F(x_k) - F^\star] \le \frac{2}{k + 1}$.
- Точно: $\mathbb E[F(x_k) - F^\star] = \frac{2k + 1}{3k(k + 1)}$ при $k \ge 1$ — от $x_0$ не зависит: первый шаг $\alpha_0 = 1$ ставит $x_1$ прямо в $c_{I_0}$.

| $k$ | точно | оценка $\frac{2}{k + 1}$ |
|---|---|---|
| $1$ | $0{,}5$ | $1$ |
| $9$ | $0{,}070$ | $0{,}2$ |
| $99$ | $0{,}0067$ | $0{,}02$ |

Обе убывают как $\frac1k$; оценка выше примерно втрое, потому что $\frac{2k + 1}{3k(k + 1)} \approx \frac{2}{3k}$.

Упрощение: шаг $\alpha_k = \frac{2}{k + 2}$ здесь даёт точную формулу через сумму квадратов. Теорема даёт тот же порядок $\frac1k$ для любой $\mu$-сильно выпуклой $L$-гладкой $F$ с ограниченным шумом.

```desmos-graph
left=0; right=50;
bottom=0; top=1.05;
---
k=[1...50]
(k,\frac{2k+1}{3k(k+1)})|red
y=\frac{2}{x+1}|orange|x>0
```
На что смотреть: красные точки — точная ошибка по значению функции, оранжевая — оценка теоремы $\frac{2}{k + 1}$. Обе спадают как $\frac1k$, красные — примерно втрое ниже.


<!-- exam:auto:start -->
**Экзамен:** основа [[Э31 SGD для сильно выпуклой гладкой функции|Э31]]
<!-- exam:auto:end -->

---

> [!quote]- Мои заметки
> **Своими словами:**
> 
> **Опирается на:**
