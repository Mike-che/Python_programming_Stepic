## Условные операторы:

```
**If - Else условный оператор**
If условие_1:
    -тело
elif:
    -тело
else:
    -тело


elif/else - опциональны, могут быть не использованы.

Пример:
    Проверка на четность
    if x % 2 == 0:
        print("Четное")
    else:
        print("Нечетное")
```

## Цикл While с предусловием
```
while условие > условие: (до тех пор пока выполняется условие, делать тело цикла)
    что-то делаем
    обновляем условие.
```
## Цикл For

```
Стандартная практика в Python, левая граница включается в интервал, правая не включается.

Range(5) - включает диапазон чисел от 0 до 4, с шагом 1
Range(1,5) - включает диапазон чисел от 1 до 4, с шагом 1
Range(1,15,2) - включает диапазон чисел от 1 до 14, с шагом 2
```

## Формат вывода
```
print("Привет {} !".format(name))
```
___
## ООП в Python
### Наследование


**Можно наследовать методы от классов не создавая их заново.**
~~~
Например:

Class Auto:
    def ride(self):
        print("Riding on a ground")

Class Boat: 
    def swim(self):
        print("Swimming on a water")
~~~

**Теперь создаем класс Амфибия который унаследует возможности и лодки и машины**

~~~
Class Amfibia(Auto,Boat):
    pass
a = Amfibia()
a.ride()
a.swim()
~~~
___

#### Примеси (Mixins) в Python

Мы хотим, чтобы у нас была возможность слушать музыку в машине. Конечно, можно просто добавить метод **play_music()** в класс Car:

~~~
class Car:
    def ride(self):
        print("Riding a car")
 
    def play_music(self, song):
        print("Now playing: {} ".format(song))
 
>>> c = Car()
>>> c.ride()
Riding a car
>>> c.play_music("Queen - Bohemian Rhapsody")
Now playing: Queen - Bohemian Rhapsody
~~~

Выносим функционал проигрывания музыки в отдельный класс-миксин:
~~~
class MusicPlayerMixin:
    def play_music(self, song):
        print("Now playing: {}".format(song))
~~~
**Домешиваем** этот класс в любой, где нужна функция проигрывания музыки:
~~~
class Smartphone(MusicPlayerMixin):
    pass
  
class Radio(MusicPlayerMixin):
    pass 
 
class Amphibian(Auto, Boat, MusicPlayerMixin):
   pass

~~~
