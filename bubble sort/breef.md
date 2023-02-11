## Bubble sort 

### Bubble sort алгоритм который сравнивает два соседних элемента и меняет их местами до тех пор, пока они не окажутся в нужном порядке.
### Подобно движению пузырьков воздуха в воде, которые поднимаются на поверхность, каждый элемент массива движется к концу в каждой итерации. 
### Поэтому его называют пузырьковой сортировкой.

### Working of Bubble Sort
Suppose we are trying to sort the elements in ascending order.

1. Первая итерация (сравнение и замена)
   1. Начиная с первого индекса, сравните первый и второй элементы.
   2. Если первый элемент больше второго, они меняются местами. 
   3. Теперь сравните второй и третий элементы. Поменяйте местами, если они не в порядке.
   4. Описанный выше процесс продолжается до последнего элемента.
```
---------------------------------------------------------------------------
|        step = 0 
|        ------------------------------------------------------------------
|
|           i = 0    | -2 | 45 | 0 | 11 | -9 |
|                      ^    ^   
|                      |____|
|
|           i = 1    | -2 | 45 | 0 | 11 | -9 |
|                            ^   ^   
|                            |___|
|
|           i = 2    | -2 | 0 | 45 | 11 | -9 |
|                                ^   ^
|                                |___|
|
|           i = 3    | -2 | 0 | 11 | 45 | -9 |
|                                     ^    ^
|                                     |____|
|
|                    | -2 | 0 | 11 | -9 | 45 |
|
|                  Compare the Adjacent Elements
|___________________________________________________________________________
```
2. Оставшаяся итерация
Тот же процесс продолжается для остальных итераций.
После каждой итерации самый большой элемент среди 
несортированных элементов помещается в конец.

```
----------------------------------------------------------------
|        step = 1
|        -------------------------------------------------------
|
|        i = 0    | -2 | 0 | 11 | -9 | 45 |
|                    ^   ^
|                    |___|
|
|        i = 1    | -2 | 0 | 11 | -9 | 45 |
|                        ^   ^
|                        |___|
|
|        i = 2    | -2 | 0 | 11 | -9 | 45 |
|                             ^    ^
|                             |____|
|
|        i = 3    | -2 | 0 | 11 | 45 | -9 |
|                                  ^    ^
|                                  |____|
|
|                 | -2 | 0 | 11 | -9 | 45 |
|______________________________________________________________
|     
|              Compare the Adjacent Elements
|______________________________________________________________
```

```
         На каждой итерации сравнение происходит до последнего 
         несортированного элемента.
----------------------------------------------------------------
|        step = 2
|        -------------------------------------------------------
|
|        i = 0    | -2 | 0 | -9 | 11 | 45 |
|                    ^   ^  
|                    |___|
|
|        i = 1    | -2 | 0 | -9 | 11 | 45 |
|                        ^   ^ 
|                        |___|
|
|                 | -2 | -9 | 0 | 11 | 45 |
|
|---------------------------------------------------------------
|              Сравните соседние элементы                       |
|_______________________________________________________________|
```

```
         Массив считается отсортированным, когда все несортированные 
         элементы размещаются на своих местах.
----------------------------------------------------------------
|        step = 3
|        -------------------------------------------------------
|
|        i = 0    | -2 | -9 | 0 | 11 | 45 |
|                    ^    ^
|                    |____|
|
|                 | -9 | -2 | - | 11 | 45 |
|_______________________________________________________________
|        Массив отсортирован когда все елементы находятся в правильно порядке
----------------------------------------------------------------
```

###
```code
   bubbleSort(array)
     for i <- 1 to indexOfLastUnsortedElement-1
       if leftElement > rightElement
         swap leftElement and rightElement
   end bubbleSort
```

## Optimized Bubble Sort Algorithm
```
   В приведенном выше алгоритме все сравнения производятся, 
   даже если массив уже отсортирован. Это увеличивает время выполнения.
   Чтобы решить эту проблему, мы можем ввести дополнительную переменную swapped. 
   Значение swapped устанавливается в true, если происходит перестановка элементов. 
   В противном случае устанавливается значение false.
   После итерации, если обмена нет, значение swapped будет ложным. 
   Это означает, что элементы уже отсортированы и нет необходимости выполнять дальнейшие итерации.
   Это сократит время выполнения и поможет оптимизировать пузырьковую сортировку.
```

`Bubble Sort Complexity`
#### Time Complexity
________________________________
| Best:                | O(n)
| Worst:               | O(n^2)
| Average:             | O(n^2)
| Space Complexity:    | O(1)
| Stability:           | Yes

#### Complexity in Detail
Bubble Sort compares the adjacent elements.
________________________________
| Cycle  |  Number of Comparisons
| 1st    |  (n-1)
| 2nd    |  (n-2)
| 3rd    |  (n-3)
| ....   |  ....
| last   |    1

Hence, the number of comparisons is
`(n-1) + (n-2) + (n-3) +......+ 1 = n(n-1)/2`
nearly equals to `n^2`

Hence, Complexity: `O(n^2)`

Also, if we observe the code, bubble sort requires two loops. Hence, the
complexity is `n*n = n^2`
1. Time Complexities:
   - Worst Case Complexity: `0(n^2)`
     Если мы хотим отсортировать в порядке возрастания, а массив находится в порядке убывания, тогда возникает наихудший случай.
   - Best Case Complexity: `0(n^2)`
     Если массив уже отсортирован, то сортировка не нужна.
   - Average Case Complexity: `O(n^2)`
     Это происходит, когда элементы массива находятся в перемешанном порядке (ни по возрастанию, ни по убыванию).
2. Space Complexity:
   - Space complexity is `O(1)` because an extra variable is used for swapping.
   - In the *optimized bubble sort algorithm*, two extra variables are used. Hence,
     the space complexity will be `0(2)`.

### Bubble Sort Application
Bubble sort is used if:
     - complexity does not matter
     - short and simple code is preferred