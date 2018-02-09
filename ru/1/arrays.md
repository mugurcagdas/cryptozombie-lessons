---
title: Массивы
actions: ['Проверить', 'Подсказать']
material:
  editor:
    language: sol
    startingCode: |
      pragma solidity ^0.4.19;

      contract ZombieFactory {

          uint dnaDigits = 16;
          uint dnaModulus = 10 ** dnaDigits;

          struct Zombie {
              string name;
              uint dna;
          }

          // Начало здесь

      }
    answer: >
      pragma solidity ^0.4.19;


      contract ZombieFactory {

          uint dnaDigits = 16;
          uint dnaModulus = 10 ** dnaDigits;

          struct Zombie {
              string name;
              uint dna;
          }

          Zombie[] public zombies;

      }
---

Если нужен список из похожих элементов, подойдет **_массив_**. В Solidity есть два типа массивов: **_фиксированный_** и **_динамический_**:

```
// Массив фиксированной длины из 2 элементов:
uint[2] fixedArray;
// Другой фиксированный массив из 5 строк:
string[5] stringArray;
// Динамический массив не ограничен по размеру и может увеличиваться:
uint[] dynamicArray;
```

Ты можешь создать массив из **_структур_**. Возьми структуру `Person` из предыдущей части:

```
Person[] people; // Динамический массив позволяет добавлять в него данные
```

Ты не забыл, что переменные состояния сохраняются в блокчейне навсегда? Создание динамического массива из подобных структур полезно для хранения структурированных данных внутри контракта, как в базе данных. 

## Открытые массивы

Можно задать массив как `public` (открытый), и Solidity автоматически создаст для него **_геттер_** (способ получения). Синтаксис:

```
Person[] public people;
```

В этом случае другие контракты смогут читать этот массив (но не писать в него). Это образец хранения открытых данных в контракте.

# Проверь себя

Армию зомби надо где-то разместить. Мы хотим, чтобы другие приложения видели зомби, поэтому сделаем массив открытым.

1. Создай открытый массив **_структур_** `Zombie` и назови его `zombies`.