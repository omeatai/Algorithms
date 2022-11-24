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
sameCase = (a, b) =>
  /[a-z]/i.test(a) && /[a-z]/i.test(b)
    ? Number(/[a-z]/.test(a) == /[a-z]/.test(b))
    : -1;
```

Python:

```py

```

</details>

<details>
  <summary>3. sample</summary>

Question:

Example:

```md

```

Console:

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
  <summary>4. sample</summary>

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
  <summary>5. sample</summary>

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
