# Homework4
## todo

### Домашнее задание к лекции "Функции"

Сожержание дз можно изучить здесь https://github.com/obulygin/pyda_homeworks/tree/master/functions

Вам нужно помочь секретарю автоматизировать работу. Для этого нужно написать программу, которая будет на основе хранимых данных исполнять пользовательские команды.

Исходные данные имеют следующую структуру:

1. перечень всех документов

documents = [
{‘type’: ‘passport’, ‘number’: ‘2207 876234’, ‘name’: ‘Василий Гупкин’},
{‘type’: ‘invoice’, ‘number’: ‘11-2’, ‘name’: ‘Геннадий Покемонов’},
{‘type’: ‘insurance’, ‘number’: ‘10006’, ‘name’: ‘Аристарх Павлов’}
]

2.перечень полок, на которых хранятся документы (если документ есть в documents, то он обязательно должен быть и в directories)

directories = {
‘1’: [‘2207 876234’, ‘11-2’],
‘2’: [‘10006’],
‘3’: []
}

Общие требования к программе:

код должен быть грамотно декомпозирован (каждая функция отвечает за свою конкретную задачу, дублирующийся функционал переиспользуется, а его код не повторяется);
в коде отсутствуют глобальные переменные (за исключением documents и directories);
пользовательский ввод обрабатывается в цикле while до тех пор, пока пользователь явно не завершит программу (вводом команды “q”).

**Задание 1**

**Пункт 1.**

Пользователь по команде “p” может узнать владельца документа по его номеру
Примеры работы:

Введите команду:
p

Введите номер документа:
10006

Результат:
Владелец документа: Аристарх Павлов

Введите команду:
p

Введите номер документа:
12345

Результат:
Документ не найден в базе

**Пункт 2.**

Пользователь по команде “s” может по номеру документа узнать на какой полке он хранится
Примеры работы:

Введите команду:
s

Введите номер документа:
10006

Результат:
Документ хранится на полке: 2

Введите команду:
p

Введите номер документа:
12345

Результат:
Документ не найден в базе

**Пункт 3.**

Пользователь по команде “l” может увидеть полную информацию по всем документам
Пример работы:

Введите команду:
l
Результат:

№: 2207 876234, тип: passport, владелец: Василий Гупкин, полка хранения: 1
№: 11-2, тип: invoice, владелец: Геннадий Покемонов, полка хранения: 1
№: 10006, тип: insurance, владелец: Аристарх Павлов, полка хранения: 2

**Пункт 4.**

Пользователь по команде “as” может добавить новую полку
Примеры работы:

Введите команду:
as

Введите номер полки:
10

Результат:
Полка добавлена. Текущий перечень полок: 1, 2, 3, 10.

Введите команду:
as

Введите номер полки:
1

Результат:
Такая полка уже существует. Текущий перечень полок: 1, 2, 3.

**Пункт 5.**

Пользователь по команде “ds” может удалить существующую полку из данных (только если она пустая)
Примеры работы:

Введите команду:
ds

Введите номер полки:
3
Результат:
Полка удалена. Текущий перечень полок: 1, 2.

Введите команду:
ds

Введите номер полки:
1
Результат:
На полке есть документа, удалите их перед удалением полки. Текущий перечень полок: 1, 2, 3.

Введите команду:
ds

Введите номер полки:
4
Результат:
Такой полки не существует. Текущий перечень полок: 1, 2, 3.