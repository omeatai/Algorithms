# Algorithms

Learn Algorithms by Ifeanyi Omeata

## Tutorial

---

### [1-CODE WARS](#)

+KATA 8

<details>
  <summary>1. Gravity Flip</summary>

Question:

Bob is bored during his physics lessons so he's built himself a toy box to help pass the time. The box is special because it has the ability to change gravity.

There are some columns of toy cubes in the box arranged in a line. The i-th column contains a_i cubes. At first, the gravity in the box is pulling the cubes downwards. When Bob switches the gravity, it begins to pull all the cubes to a certain side of the box, d, which can be either 'L' or 'R' (left or right). Below is an example of what a box of cubes might look like before and after switching gravity.

Example:

```md
- 'R', [3, 2, 1, 2] -> [1, 2, 2, 3]
- 'L', [1, 4, 5, 3, 5 ] -> [5, 5, 4, 3, 1]
```

Console:

```js
const flip = (d, a) => {
  //TODO
  return;
};
```

Solution:

JavaScript:

```js
const flip = (d, a) =>
  d === "R"
    ? a.sort(function (a, b) {
        return a - b;
      })
    : a
        .sort(function (a, b) {
          return a - b;
        })
        .reverse();
```

```js
const flip = (d, a) => a.sort((x, y) => (d === "R" ? x - y : y - x));
```

Python:

```py
def flip(d, a):
    a.sort() if d=='R' else a.sort(reverse=True)
    return a
```

```py
def flip(d,a):
    return sorted(a, reverse=d=='L')
```

</details>

<details>
  <summary>2. Check same case</summary>

Question:

Write a function that will check if two given characters are the same case.

If either of the characters is not a letter, return -1
If both characters are the same case, return 1
If both characters are letters, but not the same case, return 0

Example:

```md
'a' and 'g' returns 1

'A' and 'C' returns 1

'b' and 'G' returns 0
```

Console:

```js
function sameCase(a, b) {
  return 0;
}
```

Solution:

JavaScript:

```js
function sameCase(a, b) {
  if (
    a.toLowerCase() === a.toUpperCase() ||
    b.toLowerCase() === b.toUpperCase()
  ) {
    return -1;
  } else if (
    (a === a.toUpperCase() && b === b.toUpperCase()) ||
    (a === a.toLowerCase() && b === b.toLowerCase())
  ) {
    return 1;
  } else {
    return 0;
  }
}
```

```js
function sameCase(a, b){
  const alphabets = /[a-z]/i;
  const lower = /[a-z]/;
  const upper = /[A-Z]/;

  if(!a.match(alphabets) || !b.match(/[a-z]/i)){
    return -1
  }else if(a.match(lower) && b.match(lower) || a.match(upper) && b.match(upper)){
    return 1
  }else{
    return 0;
  }
```

```js
function sameCase(a, b) {
  return /[a-z]/i.test(a) && /[a-z]/i.test(b)
    ? Number(/[a-z]/.test(a) == /[a-z]/.test(b))
    : -1;
}
```

Python:

```py
def same_case(a, b):
    if not a.isalpha() or not b.isalpha():
        return -1;
    elif a.islower() and b.islower() or a.isupper() and b.isupper():
        return 1;
    else:
        return 0;
```

```py
def same_case(a, b):
    return int(a.isupper() == b.isupper()) if a.isalpha() and b.isalpha() else -1
```

</details>

<details>
  <summary>3. Coefficients of the Quadratic Equation</summary>

Question:

In this Kata you are expected to find the coefficients of quadratic equation of the given two roots (x1 and x2).

Equation will be the form of ax^2 + bx + c = 0

Return type is a Vector (tuple in Rust, Array in Ruby) containing coefficients of the equations in the order (a, b, c).

Since there are infinitely many solutions to this problem, we fix a = 1.

Remember, the roots can be written like (x-x1) \* (x-x2) = 0

Example:

```md
quadratic(1,2) = (1, -3, 2)
```

This means (x-1) \* (x-2) = 0; when we do the multiplication this becomes x^2 - 3x + 2 = 0

```md
quadratic(0,1) = (1, -1, 0)
```

This means (x-0) \* (x-1) = 0; when we do the multiplication this becomes x^2 - x + 0 = 0

Notes
Inputs will be integers.
When x1 == x2, this means the root has the multiplicity of two.

Console:

```js
function quadratic(x1, x2) {
  return [1, 0, 0];
}
```

Solution:

JavaScript:

```js
function quadratic(x1, x2) {
  //   (x-x1)*(x-x2) = (Math.pow(x,2)) + (-x2)(x) + (-x1)(x) + (-x1)(-x2)
  //   (x-x1)*(x-x2) = (Math.pow(x,2)) + (-x2-x1)(x) + (-x1*-x2)
  //   a + b + c = 1 + (-x2-x1) + (-x1*-x2)
  let a, b, c;
  [a, b, c] = [1, -x2 - x1, -x1 * -x2];
  return [a, b, c];
}
```

```js
function quadratic(x1, x2) {
  return [1, -(x2 + x1), x1 * x2];
}
```

Python:

```py
def quadratic(x1, x2):
    return (1,-(x2+x1),(x1 * x2))
```

```py
import numpy as np

def quadratic(*args):
    return tuple(np.poly(args))
```

</details>

<details>
  <summary>4. Quarter of the year</summary>

Question:

Given a month as an integer from 1 to 12, return to which quarter of the year it belongs as an integer number.

For example: month 2 (February), is part of the first quarter; month 6 (June), is part of the second quarter; and month 11 (November), is part of the fourth quarter.

Console:

```js
const quarterOf = (month) => {
  // Your code here
};
```

Solution:

JavaScript:

```js
const quarterOf = (month) => {
  if (month <= 3) {
    return 1;
  } else if (month <= 6) {
    return 2;
  } else if (month <= 9) {
    return 3;
  } else {
    return 4;
  }
};
```

```js
const quarterOf = (month) => Math.ceil(month / 3);
```

Python:

```py
def quarter_of(month):
    if month <= 3:
        return 1;
    elif month <=6:
        return 2;
    elif month <=9:
        return 3;
    else:
        return 4;
```

```py
from math import ceil
def quarter_of(month):
    return ceil(month / 3)
```

</details>

<details>
  <summary>5. A wolf in sheep's clothing</summary>

Question:

Wolves have been reintroduced to Great Britain. You are a sheep farmer, and are now plagued by wolves which pretend to be sheep. Fortunately, you are good at spotting them.

Warn the sheep in front of the wolf that it is about to be eaten. Remember that you are standing at the front of the queue which is at the end of the array:

```md
[sheep, sheep, sheep, sheep, sheep, wolf, sheep, sheep] (YOU ARE HERE AT THE FRONT OF THE QUEUE)
7 6 5 4 3 2 1
```

If the wolf is the closest animal to you, return "Pls go away and stop eating my sheep". Otherwise, return "Oi! Sheep number N! You are about to be eaten by a wolf!" where N is the sheep's position in the queue.

Note: there will always be exactly one wolf in the array.

Example:

```md
Input: ["sheep", "sheep", "sheep", "wolf", "sheep"]
Output: "Oi! Sheep number 1! You are about to be eaten by a wolf!"

Input: ["sheep", "sheep", "wolf"]
Output: "Pls go away and stop eating my sheep"
```

Console:

```js

```

```js

```

Solution:

JavaScript:

```js
function warnTheSheep(queue) {
  const positionOfWolf = queue.length - queue.indexOf("wolf");
  if (positionOfWolf === 1) {
    return "Pls go away and stop eating my sheep";
  } else {
    return `Oi! Sheep number ${
      positionOfWolf - 1
    }! You are about to be eaten by a wolf!`;
  }
}
```

```js
function warnTheSheep(queue) {
  const positionOfWolf = queue.length - queue.indexOf("wolf");
  return positionOfWolf === 1
    ? "Pls go away and stop eating my sheep"
    : `Oi! Sheep number ${
        positionOfWolf - 1
      }! You are about to be eaten by a wolf!`;
}
```

Python:

```py

```

```py

```

</details>

<details>
  <summary>6. sample</summary>

Question:

Example:

```md

```

Console:

```js

```

```js

```

Solution:

JavaScript:

```js

```

Python:

```py

```

</details>

<details>
  <summary>7. sample</summary>

Question:

Example:

```md

```

Console:

```js

```

```js

```

Solution:

JavaScript:

```js

```

Python:

```py

```

</details>

<details>
  <summary>8. sample</summary>

Question:

Example:

```md

```

Console:

```js

```

```js

```

Solution:

JavaScript:

```js

```

Python:

```py

```

</details>

<details>
  <summary>9. sample</summary>

Question:

Example:

```md

```

Console:

```js

```

```js

```

Solution:

JavaScript:

```js

```

Python:

```py

```

</details>

<details>
  <summary>10. sample</summary>

Question:

Example:

```md

```

Console:

```js

```

```js

```

Solution:

JavaScript:

```js

```

Python:

```py

```

</details>

<details>
  <summary>11. sample</summary>

Question:

Example:

```md

```

Console:

```js

```

```js

```

Solution:

JavaScript:

```js

```

Python:

```py

```

</details>

<details>
  <summary>12. sample</summary>

Question:

Example:

```md

```

Console:

```js

```

```js

```

Solution:

JavaScript:

```js

```

Python:

```py

```

</details>

<details>
  <summary>13. sample</summary>

Question:

Example:

```md

```

Console:

```js

```

```js

```

Solution:

JavaScript:

```js

```

Python:

```py

```

</details>

<details>
  <summary>14. sample</summary>

Question:

Example:

```md

```

Console:

```js

```

```js

```

Solution:

JavaScript:

```js

```

Python:

```py

```

</details>

<details>
  <summary>15. sample</summary>

Question:

Example:

```md

```

Console:

```js

```

```js

```

Solution:

JavaScript:

```js

```

Python:

```py

```

</details>

<details>
  <summary>16. sample</summary>

Question:

Example:

```md

```

Console:

```js

```

```js

```

Solution:

JavaScript:

```js

```

Python:

```py

```

</details>

<details>
  <summary>17. sample</summary>

Question:

Example:

```md

```

Console:

```js

```

```js

```

Solution:

JavaScript:

```js

```

Python:

```py

```

</details>

<details>
  <summary>18. sample</summary>

Question:

Example:

```md

```

Console:

```js

```

```js

```

Solution:

JavaScript:

```js

```

Python:

```py

```

</details>

<details>
  <summary>19. sample</summary>

Question:

Example:

```md

```

Console:

```js

```

```js

```

Solution:

JavaScript:

```js

```

Python:

```py

```

</details>

<details>
  <summary>20. sample</summary>

Question:

Example:

```md

```

Console:

```js

```

```js

```

Solution:

JavaScript:

```js

```

Python:

```py

```

</details>
