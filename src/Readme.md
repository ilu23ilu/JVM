```
public class JvmComprehension {
```
Класс JvmComprehension поступает для загрузки в систему ClassLoader, далее перемещается в Metaspace для сохранения данных о классе.


```
public static void main(String[] args) {
```
После вызова метода main создается фрейм в Stack.


```
int i = 1;
```
1. Во фрейме main создается переменная i со значением 1.


```
Object o = new Object();
```
2. В Heap создается объект Object и во фрейме main создается переменная o, ей присваивается ссылка на этот объект.


```
Integer ii = 2;
```
3. В Heap создается объект Integer со значением 2, а во фрейме main появляется переменная ii со ссылкой на этот объект.
```
printAll(o, i, ii);
```
4. В Stack создается фрейм printAll, и в нем записываются переменные o, i, ii.
```
private static void printAll(Object o, int i, Integer ii) {
Integer uselessVar = 700;
```
5. В Heap создается объект Integer со значением 700, а во фрейме printAll появляется переменная uselessVar со ссылкой на этот объект.
```
System.out.println(o.toString() + i + ii);
```
6. В Stack создается фрейм println, куда передаются ссылки на o, i, ii. В Stack создается фрейм toString.

```
System.out.println("finished");
```
7. В Stack создается фрейм println, ему передается ссылка на созданный в Heap объект String со значением "finished".

В процессе работы программы отрабатывает Garbage Collection.