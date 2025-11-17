#Interview Question for Node JS
------------------------------------------

##Q: Sorting Using reduce
- A: reduce() goes through an array and builds up a single result (accumulator).To "sort" using reduce(), we insert each item into the accumulator at the correct position.This gives you an insertion sort–style sorting implemented using reduce().
- In reduce(), the second parameter is the initial value of the accumulator (acc). The value you pass as the second argument becomes the starting value of acc.
- What if you DON'T give a second parameter?

--Then JavaScript will:

--take the first element of the array as the accumulator

--start the loop from index 1

```const arr = [5, 3, 8, 1, 2];

const sorted = arr.reduce((acc, curr) => {
  // Find position where curr should be inserted
  let index = acc.findIndex(item => item > curr);

  // If no larger element found → push at end
  if (index === -1) {
    acc.push(curr);
  } else {
    acc.splice(index, 0, curr);
  }

  return acc;
}, []);

console.log(sorted); // [1, 2, 3, 5, 8]
```