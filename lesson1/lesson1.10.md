## Числа и основные арифметические операции

Числа в Python бывают разные:

- Целые числа (int): 122, -4, 99999999999, 0o177, 0x9ff, 0b101010
- Вещественные числа (float): 1.0, 3.14, .5, 4E21, 4.0e21
- Комплексные числа (complex): 3 + 4j, 3.0 + 4.0j,
- Числа фиксированной точности: decimal.Decimal('0.1')
- Рациональные числа: fractions.Fraction(3, 4)

### Операции с целыми и вещественными числами

![img](.\img\l1.10_operations.png)

### Целые числа

```
print(3+2)
5
```

```
print(3-2)
1
```

```
print(3*2)
6
```

```
print(3 / 2)
1
```

```
print(3 ** 2)
9
```

Можно использовать скобки для управления порядком операций

```
standard_order = 2 + 3*4
print(standard_order)
my_order = (2 + 3)*4
print(my_order)
14
20
```

### Вещественные числа

```
print(.1 + .1)
0.2
```

#### Целые числа в Python 2 и Python 3

В Python 2 результат деления двух челых чисел - тоже целое, а в Python 3 - float.

```
print(3 / 2)
1.5
```

В Python 3 результат - 1.5, в Python 2 (без подключения future) - 1

### Комплексные числа

```
print "|{0}| = {1}".format(complex(2, 3), abs(complex(2, 3)))
print "{0} * {1} = {2}".format(complex(1, 1), complex(2, 3), complex(1, 1) * complex(2, 3))
|(2+3j)| = 3.60555127546
(1+1j) * (2+3j) = (-1+5j)
```

```
(1 + 2j) * (3+4j)
```

```
(-5+10j)
```

### Числа фиксированной точности и рациональные числа

Для решения проблем, связанных с точностью представления простых вещественных чисел введены вещественные числа с фиксированной точностью и рациональные числа (числа, представленные дробью, то есть парой целых чисел – числителем и знаменателем).

```
print(1.1/3)
from decimal import Decimal
from decimal import getcontext
getcontext().prec = 3
Decimal('4') / 3 == Decimal('1.33')
0.366666666667
```

```
True
```

```
from decimal import Decimal
from decimal import getcontext
getcontext().prec = 2
print(Decimal('1.10') / 3)
0.37
```

```
print(7/71)
print(7/71*71 == 7)
0
False
```

```
from fractions import Fraction
print(Fraction(7, 71) * 71 == 7)
True
```

### Приоритет арифметических операций в Python

![img](.\img\l1.10_operations_priority.png)