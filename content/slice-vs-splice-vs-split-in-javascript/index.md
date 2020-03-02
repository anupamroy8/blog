---
title: "Slice vs Splice vs Split in Javascript"
description: "JavaScript has plenty of useful methods to help programmers, but there are few methods which sometimes confuses us alot. And one of the…"
date: "2020-03-01T18:24:50.240Z"
categories: []
published: true
canonical_link: https://medium.com/@anupamroy8/slice-vs-splice-vs-split-in-javascript-344c41cb94a5
redirect_from:
  - /slice-vs-splice-vs-split-in-javascript-344c41cb94a5
---

JavaScript has plenty of useful methods to help programmers, but there are few methods which sometimes confuses us alot. And one of the most confusing in the lot is understanding the difference between slice, splice and split methods.

Let’s use divide them and conquer to win over them. Yes, divide them according to method type:

1.  **Array method**: **Slice**( ) and **Splice**( )
2.  **String method**: **Split**( )

---

![](./asset-1.jpeg)

To me visualizing a problem makes it easier to tackle & solve.

So, I will use example of the above bread loaf. Let’s suppose the whole bread loaf as our given array and consider each slice of bread as elements in the array. Now will move to slice first & then differentiate with splice.

### **Slice( )**

S**lice( )** is an array method can be used to copy a desired part of an array. It copies the desired part and returns it as a new array . It **doesn’t mutate** (or change the original array).

```
array.slice(fromElement, untilElement);
```

**Important:**

1.  Does **not** **mutate**, i.e not changes the original array.
2.  INPUT is `**[array]**` \====> OUTPUT is `**[array]**`.

```
eg: if we need a copy of loaf3 to loaf5 in a new array.

let bread = ['loaf1','loaf2','loaf3','loaf4','loaf5','loaf6'];

newArr = bread.slice(2, 5);

console.log(newArr);

//output: ["loaf3", "loaf4", "loaf5"]

Note: Here bread[5] is not included.
```

### Splice( )

**Splice( )** is also an array method, but this one can be used to add or remove desired number of elements to our array. As Splice( ) adds or removes elements, it leads to **mutation** of the original array.

```
array.splice(indexToStart, numberOfElementsToBeDeleted, elementToBeAdded1, elementToBeAdded2, ...);
```

Lets see with our example:

1.  **Removing only:**

```
let bread = ['loaf1','loaf2','loaf3','loaf4','loaf5','loaf6'];

bread.splice(1, 3);

["loaf2", "loaf3", "loaf4"]

console.log(bread);

//output:["loaf1", "loaf5", "loaf6"]
```

2\. **Removing and adding new elements:**

```
let bread = ['loaf1','loaf2','loaf3','loaf4','loaf5','loaf6'];

bread.splice(1, 3, 'newLoaf1', 'newLoaf2');

console.log(bread);

//output:["loaf1", "newLoaf1", "newLoaf2", "loaf5", "loaf6"]
```

**3\. Adding new elements only:**

```
let bread = ['loaf1','loaf2','loaf3','loaf4','loaf5','loaf6'];

bread.splice(3, 0, 'newLoaf1', 'newLoaf2');

console.log(bread);

//output:["loaf1", "loaf2", "loaf3", "newLoaf1", "newLoaf2", "loaf4", "loaf5", "loaf6"]
```

**Important:**

1.  Changes the original array, so **mutates**.
2.  INPUT is `**[array]**` ===> OUTPUT is `**[array]**`.

---

![](./asset-2.jpeg)

### Split( )

**Split( )** is a **string** method, but it returns an **array.** This can be useful when we need to convert a string to an array.

Yes, you guessed it right. Our example string for this methos will be:

**“_the quick brown fox jumps over the lazy dog_”.**

```
string.split(separator, limit);
```

1.  **Separator:** This tells the condition where the split will target, it can be a empty space, comma or any value.
2.  **Limit: (optional)** the number of splits; **_default is whole string._**

```
let myString = "the quick brown fox jumps over the lazy dog";

//For a comma separated array use " ":

myString.split(" ");

//output: ["the", "quick", "brown", "fox", "jumps", "over", "the", "lazy", "dog"]

//For each alphabet as element of array use "":

myString.split("");

//output: ["t", "h", "e", " ", "q", "u", "i", "c", "k", " ", "b", "r", "o", "w", "n", " ", "f", "o", "x", " ", "j", "u", "m", "p", "s", " ", "o", "v", "e", "r", " ", "t", "h", "e", " ", "l", "a", "z", "y", " ", "d", "o", "g"]
```

#### **Quick tips:**

1.  To apply **split( )** to an **array**, convert it to string using `**.toString( )**`.

```
var myString = array.toString();
```

2\. To convert a **string** to an **array,** use split with (“ ”) as separator.

```
myString.split(" ");
```

**Important:**

1.  Does not changes the original string, so no **mutation**.
2.  INPUT is `**string**`  \===> OUTPUT is `**[array]**`.

---

This concludes my article hope you enjoyed reading it. If you like it please press clap & also provide your valauable feedback.
