# Домашнее задание по неделе 4
_Лучше делать его в том порядке, в котором написано_

Число в скобках - количество баллов.
### Sys
1. (1) Напишите программу, которая выводит количество переданных ей аргументов и печатает питоновский `list`, состоящий из этих аргументов.
2. (1) Напишите программу, которая выводит версию питона и используемое ядро ОС.

В заданиях 1-2 использовать модуль `sys`.
### Argparse
3. (2) Напишите консольную программу, которой на вход подается единственное число N (без имени или с именем -n), а программа печатает значение Nго числа Фибоначчи.
Использовать `argparse`.

4. (3) Напишите программу, которая на вход принимает три аргумента `--show-all (-a)`, `--file (-f) <file>` и один позиционный `number` и выводит n-ое простое число.
Если передан аргумент командной строки `--show-all` или `-a`, то необходимо показывать все предыдущие простые числа (иначе показать только последнее).
Если передан `--file` или `-f`, то нужно сохранить вывод программы в файл помимо печати в консоль (естественно, после `--file` надо считать путь к файлу).
Порядок именованных аргументов не должен иметь значения.
Для чтения файла использовать `argparse.FileType()`.

Примеры:
```bash
# 5-ое простое число, показываем все, записываем в файл ./1.txt
python numbers.py --show-all --file 1.txt 5
# То же самое
python numbers.py --file 1.txt --show-all 5
# Просто выводим 10-ое число и только его
python numbers.py 10
```

### Декораторы

5. (2) Напишите функцию, которая получает на вход список чисел и выдает ответ, сколько в данном списке четных чисел.
Напишите декоратор, который меняет поведение функции следующим образом: если четных чисел нет, то пишет "Нет(" а если их больше 10, то пишет "Очень много".

6. (2) Напишите декоратор `swap`, который делает так, что задекорированная функция принимает все свои неименованные аргументы в порядке, обратном тому, в котором их передали (для аргументов с именем не вполне правильно учитывать порядок, в котором они были переданы).
_Вы можете использовать `args` для получения всех неименованных аргументов, развернуть tuple и передать через звездочку `*`_

Пример ожидаемого поведения:

```python
@swap
def div(x, y, show=False):
    res = x / y
    if show:
        print(res)
    return res

div(2, 4, show=True)
# Вернет 2.0
```
7. (3) Напишите декоратор, который принимает в качестве аргумента путь к файлу. Если данный декоратор добавить к функции, то в указанный файл будет логироваться информация вида:
    - Время вызова функции
    - Входящие аргументы
    - Ответ return (если есть, если нет то логгировать '-')
    - Время завершения работы функции
    - Время работы функции