# Задачи рассматриваемые взяты отсюда: ➡️ https://codeforces.com/problemset?order=BY_RATING_ASC ⬅️

(сортировка по сложности (условные 800 это easy, 3500 это hard))

Пруфы о работоспособности и проверенности решений:

![image](https://github.com/sm-an/codeforces/assets/123721397/2b5f8e2f-e2bc-410c-9990-0e87ead2165b)

---

### 1) 4A - Watemelon - https://codeforces.com/problemset/problem/4/A

```python
w = int(input())
if w % 2 == 0 and w > 2:
    print('YES')
else:
    print('NO')
```

---

### 2) 71A - Way Too Long Words - https://codeforces.com/problemset/problem/71/A

```python
n = int(input())
for i in range(n):
    b = input()  # делаем столько вводов, сколько число в начале
    if len(b) > 10:
        p1 = b[0]  # первую букву
        p2 = len(b) - 2  # длина минус 2 крайние буквы
        p3 = b[-1]  # последнюю букву
        result = f'{p1}{p2}{p3}'  # формируем строку
        print(result)
    else:
        print(b)  # выводим слово без изменений
```

---

### 3) 231A - Team - https://codeforces.com/problemset/problem/231/A

```python
n = int(input())
s = 0  # будущая сумма
for i in range(n):
    a = input()  # сколько первое число, столько и инпутов
    num1, num2, num3 = int(a[0]), int(a[2]), int(a[4])  # можем себе позволить
    # так как гарантируется 3 числа из одного разряда(1,2 или 3)
    if num1 + num2 + num3 >= 2:
        s += 1
print(s)
```

---

### ❌ 158A - Next Round -> пропущена, душная и непонятная

---

### 4) 50A - Domino piling - https://codeforces.com/problemset/problem/50/A

```python
a = input().split(" ")  # раскалываем два числа на два элемента
num1, num2 = int(a[0]), int(a[1])
b = (num1 * num2) // 2  # всё вот так легко, оказывается :)
print(b)
```

---

### 5) 282A - Bit++ - https://codeforces.com/problemset/problem/282/A

```python
# декремент и инкремент в путхоне)
a = int(input())
x = 0  # начальное положение от нуля
for i in range(a):  # сколько int, столько и действий
    b = input()
    # Дальше есть рофл: условии сказано про "x", в примерах используется "X".
    # Правильный ответ: "X" -> опираемся на примеры :)
    if b == "X++" or b == "++X":
        x += 1
    elif b == "X--" or b == "--X":
        x -= 1
print(x)
```

---

### ❌ 263A - Beautiful Matrix -> Скипаем, душная и непонятная

---

### 6) 112A - Petya and Strings - https://codeforces.com/problemset/problem/112/A

Решение минималистичное, но отлично работающее:

```python
a, b = input().lower(), input().lower()
if a < b:
    print(-1)
elif a > b:
    print(1)
else:
    print(0)
```

Но будто резонее научить их лексикографическому сравнению ручками. Не всё же сахаром питонячьим пользоваться. Если так, то вот вариант:

```python
from string import ascii_lowercase as asc  # импортируем алфавит, потому что почему нет
a, b = input().lower(), input().lower()
result = 0
for i in range(len(a)):  # проходимся по каждой букве
    if a[i] != b[i]:  # до тех пор пока вводы не будут равны
        if asc.index(a[i]) < asc.index(b[i]):  # если индекс буквы меньше у первого ввода
            result = -1
            break  # до первого различия
        else:  # если у второго ввода буква раньше
            result = 1
            break
print(result)
```

---

### 7) 339A - Helpfull Maths - https://codeforces.com/problemset/problem/339/A

```python
s = sorted(input().split('+'))  # инпут разбитый по плюсам (получаем список чисел) сортируем
result = ''
for num in s:
    result += num  # прибавляем число
    result += '+'  # прибавляем плюсы
print(result[:-1])  # обрезаем плюс в конце
```

---
---
---

### 8) 236A - Boy or Girl - https://codeforces.com/problemset/problem/236/A

```
nick = input()
chars = set(nick)
if len(chars) % 2 == 1:
    print("IGNORE HIM!")
else:
    print("CHAT WITH HER!")
```

### 9) 266A - Stones on the Table - https://codeforces.com/problemset/problem/266/A

```python
count = int(input())  # по сути выдали len(stones) просто. бесполезное(
stones = input()
skolko_ubrat = 0
i = 0
while i < len(stones) - 1:  # -1 за длину -> индекс, -1 за предпоследний элемент
    if stones[i] == stones[i+1]:  # если текущая и след. буквы одинаковы
        stones = stones[:i] + stones[i+1:]  # вырезаем текущую букву
        skolko_ubrat += 1
        continue  # перезапуск цикла, не переходим к след. букве
    i += 1  # переходим к след. букве
print(skolko_ubrat)
```

### 10) 791A - Bear and Big Brother - https://codeforces.com/problemset/problem/791/A

```python
ages = input().split(" ")
years = 0
age_limak, age_bob = int(ages[0]), int(ages[1])
while age_limak <= age_bob:
    age_limak *= 3
    age_bob *= 2
    years += 1
print(years)
```
