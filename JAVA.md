
Lambda Expression
`(param)-> code`


use a functional interface 
util class{java.util.function.Function}
FUNCTION<T,R>

```
Function<Integer, Integer> mul2 = x -> x * 2;
int res = mul.apply(5);
System.out.println(res);
```


import java.util.stream.Stream;  / import java.util.*;


creation (collection , array , directl}

#collection
`Stream<type> var = arraylist.stream()`

#arrays

`Stream<type> var = Arrays.strea(array)`

#direct

`Stream<String> stream = Stream.of("Red", "Green", "Blue");`


map()

```
List<Integer> num = Arrays.asList(1,2,3,4,5);
List<Integer> sqnum= num.stream()
						.map(n->n*n)
						.collect(Collectors.toList());
System.out.println(sqnum);
```


distinct()
```
List<Integer> numbers = Arrays.asList(1, 2, 3, 2, 1, 4, 5, 4);
     
List<Integer> uniqueNumbers = numbers.stream()
									 .distinct()
                                   .collect(Collectors.toList());
System.out.println(uniqueNumbers);
```
 `o/p  [1, 2, 3, 4, 5]`
 