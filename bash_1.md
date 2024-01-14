<h3>Задание №1</h3>
Напишите сценарий, который принимает целое число в качестве аргумента и возвращает «Четное» для четных чисел или «Нечетное» для нечетных чисел.

```bash
#! /bin/bash

if  [ -n "$1" ]; then
   if [ $(( $1 % 2 )) -eq 0 ]; then
      echo "Четное"
   else
      echo "Нечетное"
   fi
else
   echo "Specify two numbers!"
fi
```

<h3>Задание №2</h3>
Создайте функцию, которая проверяет, делится ли число n на два числа x И y. Все входные данные являются положительными, ненулевыми числами.

Пример:
1) n =   3, x = 1, y = 3 =>  true because   3 is divisible by 1 and 3
2) n =  12, x = 2, y = 6 =>  true because  12 is divisible by 2 and 6
3) n = 100, x = 5, y = 3 => false because 100 is not divisible by 3
4) n =  12, x = 7, y = 5 => false because  12 is neither divisible by 7 nor 5

```bash
#! /bin/bash

if  [ -n "$3" ]; then
   first=$(( $1 % $2 ))
   second=$(( $1 % $3 ))

   if [ $first -eq 0 ] && [ $second -eq 0 ]; then
      echo "true because "$1" is divisible by "$2" and "$3""
   elif [ $first -ne 0 ] && [ $second -ne 0 ]; then
      echo "false because "$1" is neither divisible by "$2" nor "$3""
   elif [ $first -ne 0 ]; then
      echo "false because "$1" is not divisible by "$2""
   elif [ $second -ne 0 ]; then
      echo "false because "$1" is not divisible by "$3""
   fi
else
   echo "Specify two numbers!"
fi
```