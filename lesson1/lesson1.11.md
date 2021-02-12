## Работа со строками

#### Строки выделяются одинарными или двойными кавычками

```
my_string = "This is a double-quoted string."
my_string = 'This is a single-quoted string.'
```

```
quote = "Linus Torvalds once said, 'Any program is only as good as it is useful.'"
```

```
first_name = 'eric'

print(first_name)
print(first_name.title())
```

#### Разные регистры

```
first_name = 'eric'

print(first_name)
print(first_name.title())
print(first_name.upper())

first_name = 'Eric'
print(first_name.lower())
```

*upper()*, *lower()* и *title()* - это методы.

Синтаксис: variable_name.action()

*action* - это название метода, который можно применить к переменной *variable_name*. В скобках можно указывать другие переменные (аргументы) метода.

#### Конкатенация ("склеивание") строк

```
first_name = 'ada'
last_name = 'lovelace'

full_name = first_name + ' ' + last_name

print(full_name.title())
Ada Lovelace
```

```
first_name = 'ada'
last_name = 'lovelace'
full_name = first_name + ' ' + last_name

message = full_name.title() + ' ' + "was considered the world's first computer programmer."

print(message)
Ada Lovelace was considered the world's first computer programmer.
```

#### Пробельные символы (whitespaces)

- " " - пробел (очевидно)
- "\t" - табуляция
- "\n" - перенос строки

```
print("Hello everyone!")
```

```
print("\tHello everyone!")
```

```
print("Hello \teveryone!")
```

```
print("Hello everyone!")
```

```
print("Hello!")
print("\nHello everyone!")
Hello!

Hello everyone!
```

```
print("Hello \neveryone!")
```

```
print("\n\n\nHello everyone!")
Hello everyone!
```

#### Удаление лишних пробельных символов

Часто при заполнении веб-форм появляются лишние пробелы слева и/или справа. От них можно избавиться

```
name = ' eric '

print(name.lstrip())
print(name.rstrip())
print(name.strip())
```

Так нагляднее:

```
name = ' eric '

print('-' + name.lstrip() + '-')
print('-' + name.rstrip() + '-')
print('-' + name.strip() + '-')
-eric -
- eric-
-eric-
```

Избавляться можно не только от пробелов. Здесь ',' - аргумент методов *lstrip()*, *rstrip()* и *strip()*

```
name = ',,eric,,'

print('-' + name.lstrip(',') + '-')
print('-' + name.rstrip(',') + '-')
print('-' + name.strip(',') + '-')
-eric,,-
-,,eric-
-eric-
```

### Методы для работы со строками

Обзор на [Pythonworld](http://pythonworld.ru/tipy-dannyx-v-python/stroki-funkcii-i-metody-strok.html)

Все методы строк:

```
dir(str)
```

```
['__add__',
 '__class__',
 '__contains__',
 '__delattr__',
 '__dir__',
 '__doc__',
 '__eq__',
 '__format__',
 '__ge__',
 '__getattribute__',
 '__getitem__',
 '__getnewargs__',
 '__gt__',
 '__hash__',
 '__init__',
 '__iter__',
 '__le__',
 '__len__',
 '__lt__',
 '__mod__',
 '__mul__',
 '__ne__',
 '__new__',
 '__reduce__',
 '__reduce_ex__',
 '__repr__',
 '__rmod__',
 '__rmul__',
 '__setattr__',
 '__sizeof__',
 '__str__',
 '__subclasshook__',
 'capitalize',
 'casefold',
 'center',
 'count',
 'encode',
 'endswith',
 'expandtabs',
 'find',
 'format',
 'format_map',
 'index',
 'isalnum',
 'isalpha',
 'isdecimal',
 'isdigit',
 'isidentifier',
 'islower',
 'isnumeric',
 'isprintable',
 'isspace',
 'istitle',
 'isupper',
 'join',
 'ljust',
 'lower',
 'lstrip',
 'maketrans',
 'partition',
 'replace',
 'rfind',
 'rindex',
 'rjust',
 'rpartition',
 'rsplit',
 'rstrip',
 'split',
 'splitlines',
 'startswith',
 'strip',
 'swapcase',
 'title',
 'translate',
 'upper',
 'zfill']
```

**find** - поиск подстроки в строке. Возвращает номер первого вхождения или -1

```
"we bought a new house and we are happy".find("we")
```

```
0
```

**rfind** - поиск подстроки в строке. Возвращает номер последнего вхождения или -1

```
"we bought a new house and we are happy".rfind("we")
```

```
26
```

**index** - поиск подстроки в строке. Возвращает номер первого вхождения или вызывает ValueError

```
"we bought a new house and we are happy".index("we")
```

```
0
```

```
"we bought a new house and we are happy".index("land")
---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
<ipython-input-12-2f14ee96f516> in <module>()
----> 1 "we bought a new house and we are happy".index("land")

ValueError: substring not found
```

**rindex** - поиск подстроки в строке. Возвращает номер последнего вхождения или вызывает ValueError

```
"we bought a new house and we are happy".rindex("we")
```

```
26
```

```
"we bought a new house and we are happy".rindex("land")
---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
<ipython-input-14-474bfeca915e> in <module>()
----> 1 "we bought a new house and we are happy".rindex("land")

ValueError: substring not found
```

**replace** - замена по шаблону

```
help(str.replace)
Help on method_descriptor:

replace(...)
    S.replace(old, new[, count]) -> str
    
    Return a copy of S with all occurrences of substring
    old replaced by new.  If the optional argument count is
    given, only the first count occurrences are replaced.
```

```
"we bought a new house".replace("house", "building")
```

```
'we bought a new building'
```

```
"bla bla bla".replace("bla", "wow", 3)
```

```
'wow wow wow'
```

**split** - разбиение строки по разделителю

```
"hello#$great#$to#$see#$you".split("#$")
```

```
['hello', 'great', 'to', 'see', 'you']
```

- **isdigit** - состоит ли строка из цифр;
- **isalpha** - состоит ли строка из букв;
- **isalnum** - состоит ли строка из цифр или букв;
- **islower** - состоит ли строка из символов в нижнем регистре;
- **isupper** - состоит ли строка из символов в верхнем регистре;
- **istitle** - начинаются ли слова в строке с заглавной буквы.

**join** - сборка строки из списка по разделителю, применяется к разделителю

```
",".join(["Ann", "Leo", "Tiffany"])
```

```
'Ann,Leo,Tiffany'
```

**format** - форматирование строки

Пример

```
# key-value pairs: client_id, (name, age, occupation)
personal_data = {1: ("Ann", 29, "Artist"), 
               2: ("Leo", 54, "Programmer"), 
               3: ("Tiffany", 43, "Shop Assistant")}
for (name, age, occupation) in personal_data.values():
    print("{0} (age {1}) is a {2}".format(name, age, occupation))
Ann (age 29) is a Artist
Leo (age 54) is a Programmer
Tiffany (age 43) is a Shop Assistant
```