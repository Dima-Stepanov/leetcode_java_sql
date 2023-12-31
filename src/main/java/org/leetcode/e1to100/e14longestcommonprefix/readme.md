# [14. Longest Common Prefix](https://leetcode.com/problems/longest-common-prefix/)

Write a function to find the longest common prefix string amongst an array of strings. <b>
If there is no common prefix, return an empty string "". <b>
---

### Example 1:

> Input: strs = ["flower","flow","flight"] <b>
> Output: "fl" <p>

### Example 2:

> Input: strs = ["dog","racecar","car"] <p>
> Output: "" <p>
> Explanation: There is no common prefix among the input strings. <p>
___

### Constraints:

* 1 <= strs.length <= 200 <p>
* 0 <= strs[i].length <= 200 <p>
* strs[i] consists of only lowercase English letters. <p>
---
## FAQ

1) Самый простой вариант - это горизонтальный поиск последовательностей, <p>
   т.е. определение и поиск какой-то подстроки в остальных строках массива. <p>
   Алгоритм такой: Переменная искомой последовательности (rsl) инициализируется первой строкой. <p>
   Далее в цикле, начиная со следующей строки массива, начинаем искать через indexOf() присутствие rsl в текущей
   строке. <p>
   Для этого в цикле while каждый проход уменьшаем rsl на 1 символ, пока rsl не достигнет 0. <p>
   Если совпадения нет, значит возвращаем пустую строку, <p>
   так как остальные строки нет смысла проверять, так как уже нет совпадений между двумя первыми строками. <p>
   Если совпадения есть, то переходим к проверке присутствия полученного rsl в следующей строке и т.д. <p>
2) Следующий вариант - это вертикальный поиск. Данное решение - это ускоренный вариант предыдущего. При вертикальном <p>
   поиске мы просматриваем все строки массива сначала на совпадение первого символа, потом второго и т.д. Алгоритм<p>
   такой: открываем цикл и инициализируем первый символ первой строки в переменную типа char. Далее в другом цикле,<p>
   начиная со следующей строки, проверяем, что либо индекс первого цикла равен длине текущей строки (то есть индекс
   уже<p>
   вышел за ее пределы), либо искомый символ не равен текущему символу. В любом из этих случаев возвращается
   substring()<p>
   первой строки от 0 до индекса первого цикла.<p>
3) Существуют еще 2 варианта решения - через подход "Разделяй и властвуй" и через бинарный поиск. Суть первого<p>
   варианта - в делении массива строк на подмассивы, а суть второго - найти длиннейшую последовательность путём<p>
   бинарного поиска. Если вы хорошо владеете этими алгоритмами, можете попробовать решить с помощью них. Если нет, то<p>
   решения через второй вариант будет достаточно.<p>
