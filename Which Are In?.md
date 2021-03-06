# Codewars 2: Which Are In?

## Kata Description:

Given two arrays of strings a1 and a2 return a sorted array r in lexicographical order of the strings of a1 which are substrings of strings of a2.

#Example 1: a1 = ["arp", "live", "strong"]
a2 = ["lively", "alive", "harp", "sharp", "armstrong"]
returns ["arp", "live", "strong"]

#Example 2: a1 = ["tarp", "mice", "bull"]
a2 = ["lively", "alive", "harp", "sharp", "armstrong"]
returns []

**Sudo-Code**

1.  Start with the first element N1 in Array1
2.  Loop through Array2 and find the element that contains N1 using ".includes" method
3.  If ".includes" returns true, push N1 into results array
4.  Loop through all elements in Array1
5.  Sort result array
6.  Write a function that filters out the unique elements in an array
7.  Update the result array

**My Solution**

```
function inArray(array1,array2){
  var result = [];

  for (var i = 0; i < array1.length; i++){
    for (var j = 0; j <array2.length; j++) {
      if (array2[j].includes(array1[i])){
        result.push(array1[i]);
      }
    }
  }

  result.sort();

  var prims = {"boolean":{}, "number":{}, "string":{}}, objs = [];

  return result.filter(function(item) {
    var type = typeof item;
    if(type in prims)
      return prims[type].hasOwnProperty(item) ? false : (prims[type][item] = true);
        else
      return objs.indexOf(item) >= 0 ? false : objs.push(item);
    });

  return result;
}
```

######Special Note / Credits:

> Unique function comes from [Stackoverflow answer](https://stackoverflow.com/questions/9229645/remove-duplicate-values-from-js-array):

**Solution 1:**

```

```

**Solution 2:**

```

```
