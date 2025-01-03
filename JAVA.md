
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
List<Integer> sqnum= num.stream().map(n->n*n).collect(Collectors.toList());
System.out.println(sqnum);
```


distinct()
```
List<Integer> numbers = Arrays.asList(1, 2, 3, 2, 1, 4, 5, 4);
     
List<Integer> uniqueNumbers = numbers.stream().distinct().collect(Collectors.toList());
System.out.println(uniqueNumbers);
```
 `o/p  [1, 2, 3, 4, 5]`

filter()

```
List<Integer> nums = Arrays.asList(1,2,3,4,5,6,7,8,9);
List<Integer> num = nums.stream().filter(n->n%2==0).collect(Collectors.toList());
System.out.println(nums);
```

sorted()

```
List<Integer> nums = Arrays.asList(1,2,3,4,5,6,7,8,9);
List<Integer> num = nums.stream().sorted().collect(Collectors.toList());
System.out.println(nums);
```

limit()
```
nums.stream().limit(5).forEach(System.out::println);
```

skip()
```
nums.stream().skip(5).forEach(System.out::println);
```

anyMatch(),allMatch(),noneMatch()
all returns boolean value 
```
boolean greater = numbers.stream().anyMatch(n -> n > 5);
```


foreach(),reduce(),count(),collect()
these are terminal operations 
 
 foreach()

```
List<Integer> nums = Arrays.asList(1,2,3,4,5,6,7,8,9);
num.stream().forEach(number->System.out.println(number))
```

reduce()
```
int sum = nums.stream().reduce((a, b) -> a + b);
```

count()

```
int c = numbers.stream().count();
```


arrayList(integer value) to array(int value)

```
class Main {
    public static void main(String[] args) {
        List<Integer> integerList = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 5));
        int[] intArray = integerList.stream()
                                    .mapToInt(Integer::intValue)  
                                    .toArray();                   

        
    
    }
}

```