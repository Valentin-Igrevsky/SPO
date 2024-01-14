<h3>Задание №1</h3>

Суммирование

Напишите программу, которая находит суммирование каждого числа от 1 до num. Число всегда будет целым положительным числом, большим 0.

Например:

sum(2) -> 3

1 + 2

sum(8) -> 36

1 + 2 + 3 + 4 + 5 + 6 + 7 + 8

```bash
#! /bin/bash

if  [ -n "$1" ]
then
   sum=0
   for ((i=1; i<="$1"; ++i)); do
      sum=$((sum+i))
   done
   echo $sum
else
echo "Specify a number!"
fi
```

<h3>Задание №2</h3>

Возьмите 2 строки s1 и s2, включающие только буквы от a до z.

Возвращает новую отсортированную строку, максимально длинную, содержащую различные буквы - каждая из которых берется только один раз - исходящие из s1 или s2.

a = "xyaabbbccccdefww"

b = "xxxxyyyyabklmopq"

longest(a, b) -> "abcdefklmopqwxy"

a = "abcdefghijklmnopqrstuvwxyz"

longest(a, a) -> "abcdefghijklmnopqrstuvwxyz"

```bash
#! /bin/bash

if  [ -n "$2" ]
then
   echo -n "$1$2" | grep -o . | sort | uniq | tr -d '\n'
   echo
else
   echo "Specify two strings!"
fi
```

<h3>Задание №3</h3>

Джон пригласил друзей. Его список:

s="Ann:Russel;John:Gates;Paul:Wahl;Alex:Tolkien;Ann:Bell;Lewis:Kern;Sarah:Rudd;Sydney:Korn;Madison:Meta";

Нужно написать программу, которая переводит эту строку в верхний регистр и сортирует ее в алфавитном порядке по фамилии.

Если фамилии совпадают, отсортируйте их по имени. Фамилия и имя гостя вводятся в результате в скобках через запятую.

Таким образом, результатом будет:

"(BELL, ANN)(GATES, JOHN)(KERN, LEWIS)(KORN, SYDNEY)(META, MADISON)(RUDD, SARAH)(RUSSEL, ANN)(TOLKIEN, ALEX)(WAHL, PAUL)"

Может случиться так, что в двух разных семьях с одинаковой фамилией два человека также имеют одинаковое имя.

```bash
#! /bin/bash

if  [ -n "$1" ]
then
   IFS=';' read -ra guests <<< "$1"

   to_upper() {
      name=$(echo $1 | tr '[:lower:]' '[:upper:]')
      echo $name
   }

   sorted_result=$(for guest in "${guests[@]}"; do to_upper "$guest"; done | awk -F: '{print $2,$1}' | sort | awk '{print "("$1", "$2")"}' | paste -sd "" -)

   echo $sorted_result
else
   echo "Specify string in format: name:surname;name:surname;..."
fi
```