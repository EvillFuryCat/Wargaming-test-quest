# Wargaming-test-quest 
# Тестовое задание на позицию Programming intern в компании Wargaming Санкт-Петербург #
# Задание:

## 1. На языке Python реализовать алгоритм (функцию) определения четности целого числа, который будет аналогичен нижеприведенному по функциональности, но отличен по своей сути. Объяснить плюсы и минусы обеих реализаций.
   ```Python example:

                def isEven(value):return value%2==0               
Плюсы: Код просто читается и понимается

## Решение

   ```Python example:
   
                def is_even(value):return value & 1 == 0
  ```

Число нечетно, когда его младший бит равен 1, и четно, когда младший бит равен 0
                 
Плюсы: битовые, низкоуровневые опперации быстрее

Минусы: Тяжелее в понимании

## 2. На языках Python(2.7) и/или С++, написать минимум по 2 класса реализовывающих циклический буфер. 
## Решение:
№1
```Python example:
    
 class CircularBuffer(object):
    def __init__(self, size):
        self.index= 0
        self.size= size
        self._data = []

    def record(self, value):
        if len(self._data) == self.size:
            self._data[self.index]= value
        else:
            self._data.append(value)
        self.index= (self.index + 1) % self.size

    def __getitem__(self, key):
        return(self._data[key])

    def __repr__(self):
        return self._data.__repr__() + ' (' + str(len(self._data))+' items)'

    def get_all(self):
        return(self._data)
```
№2
```Python example:
class RingBuffer:
    def __init__(self,size_max):
        self.max = size_max
        self.data = []

    class __Full:
        def append(self, x):
            self.data[self.cur] = x
            self.cur = (self.cur+1) % self.max
        def get(self):
            return self.data[self.cur:]+self.data[:self.cur]

    def append(self,x):
        self.data.append(x)
        if len(self.data) == self.max:
            self.cur = 0
            self.__class__ = self.__Full

    def get(self):
        return self.data
```
## 3. На языке Python реализовать функцию, которая быстрее всего (по процессорным тикам) отсортирует данный ей массив чисел. Массив может быть любого размера со случайным порядком чисел (в том числе и отсортированным). Объяснить почему вы считаете, что функция соответствует заданным критериям.

## Решение

Велосипед уже придуман, спроектирован и доработан.

Сортировка в Python реализована на алгоритме Timsort. Выполняется функцией sorted(), если это итерируемые объекты, и методом list.sort(), если это список
