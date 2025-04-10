
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
        List<Integer> nums = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 5));
        int[] arr = nums.stream()
                                    .mapToInt(Integer::intValue)  
                                    .toArray();                   

        
    
    }
}

```


Alt..
To swap numbers
```
a = a^b
b = a^b
a = a^b
```

Prime number
```
BigInteger.valueOf(n).isProbablePrime(10);
```

Count no.of digits 
```
int count = (int)Math.log10(n) + 1;
```

```
int count = String.valueOf(n).length();
```

Power of 2 
```
if(n && !(n & (n-1)))
```

sum of  n numbers 

odd 
```
n = 5;
sum = n *n;
```

even 
```
n= 5;
sum=n*(n+1);
```

Number is odd or even 
```
(n&1)==0?"Even":"Odd";
```

Unique element in an array 
```
for(int n:a)res^=n;
```

GCD

```
int gcd(int a, int b) {
    return b == 0 ? a : gcd(b, a % b);
}
```
LCM
```
int lcm(int a, int b) {
    return a * (b / gcd(a, b));
}
```
Sum of digits 
```
for(s=0;n;n/=10) s+=n%10;
```