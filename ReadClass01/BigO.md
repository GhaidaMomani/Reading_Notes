# A beginner's guide to Big O Notation
Read: Class 01

<!-- This is the reading notes repository where I keep my favorite articles with their sources.
       
       Hope you'll benefit from my reads, Enjoy!


-->



Summary of A beginner's guide to Big O Notation Artcicle: <br/>
By Rob Bell (https://rob-bell.net/2009/06/a-beginners-guide-to-big-o-notation).
<br/>
<hr/>
<br/>

## Description
**A beginner's guide to Big O Notation.** 



<hr/>
<br/>


## Introduction
* Big O notation is used in Computer Science to describe the performance or complexity of an algorithm.
* Big O specifically describes the worst-case scenario, and can be used to describe the execution time required or the space used (e.g. in memory or on disk) by an algorithm.
* You must know maths in order to know the Big O notaion 


<br/>

![](./OOO.jpg)


<hr/>
    <p align="right">(<a href="#top">back to top</a>)</p>

<!-- Content  -->

## orders of growth

## O(1) :
```
   bool IsFirstElementNull(IList<String> elements)
{
    return elements[0] == null;
}

```

# O(N):
```
bool ContainsValue(IEnumerable<string> elements, string value)
{
    foreach (var element in elements)
    {
        if (element == value) return true; 
    }     
    return false; 
}
```


# O(N²):
```
bool ContainsDuplicates(IList<string> elements)
{
    for (var outer = 0; outer < elements.Count; outer++) 
    {
        for (var inner = 0; inner < elements.Count; inner++) 
        { 
            // Don't compare with self 
            if (outer == inner) continue;             
            
            if (elements[outer] == elements[inner]) return true; 
        }
    }    
    return false;
}
```


# O(2^N):

```
int Fibonacci(int number)
{
    if (number <= 1) return number;
       
    return Fibonacci(number - 2) + Fibonacci(number - 1); 
}


```
<hr/>

# So we can tell wich time complexity is good and which to aviod using the O()
![](big.jpeg)



<hr/>
 <p align="right">(<a href="#top">back to top</a>)</p>







  <br/><br/>

<p align="right">Ghaida Al Momani, Software Engineer</p>
<p align="right">Jordan, Amman</p>
  <p align="right">22, 26 Feb </p>