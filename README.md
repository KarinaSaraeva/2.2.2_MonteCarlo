# Константа **π** и метод Монте-Карло

Вычислить константу **π** методом Монте-Карло можно по-разному. Один из способов сводится к следующему алгоритму:

1. Сгенерировать **N** случайных точек на плоскости, равномерно распределенных в квадрате `[0, 1] × [0, 1]`
2. Подсчитать долю **f** точек, попавших во круг, вписанный в квадрат

Покажите, что при **N → ∞** величина **f** стремится к **π**. Какова точность такого вычисления **π** для данного **N**? 
_Подсказка. Число точек, попавших внутрь окружности, подчиняется биномальному распределению с параметром **p = π/4**. Математическое ожидание для такого распределения равно **Np**, а дисперсия
равна **Np(1 − p)**._

Покажите на графике, что точность вычисления повышается с количеством точек. Допустим, `pi_error` вычисляет оценку ошибки от количества точек. Тогда следующий код отобразит эту зависимость на графике:

```python
import matplotlib.pyplot as plt
xs = [2**k for k in range(10, 25)]
ys = [pi_error(x) for x in xs]
plt.plot(xs, ys)
plt.xscale("log")
plt.show()
```
