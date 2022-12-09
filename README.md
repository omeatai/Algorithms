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
function warnTheSheep(queue) {}
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

```js
function warnTheSheep(queue) {
  const position = queue.reverse().indexOf("wolf");
  return position === 0
    ? "Pls go away and stop eating my sheep"
    : `Oi! Sheep number ${position}! You are about to be eaten by a wolf!`;
}
```

Python:

```py
def warn_the_sheep(queue):
    queue.reverse()
    position = queue.index("wolf")
    if position == 0:
        return "Pls go away and stop eating my sheep"
    else:
        return f"Oi! Sheep number {position}! You are about to be eaten by a wolf!"
```

```py
def warn_the_sheep(queue):
    queue.reverse()
    position = queue.index("wolf")
    return "Pls go away and stop eating my sheep" if position == 0 else f"Oi! Sheep number {position}! You are about to be eaten by a wolf!"
```

</details>

<details>
  <summary>6. Closest elevator</summary>

Question:

Given 2 elevators (named "left" and "right") in a building with 3 floors (numbered 0 to 2), write a function elevator accepting 3 arguments (in order):

left - The current floor of the left elevator
right - The current floor of the right elevator
call - The floor that called an elevator
It should return the name of the elevator closest to the called floor ("left"/"right").

In the case where both elevators are equally distant from the called floor, choose the elevator to the right.

You can assume that the inputs will always be valid integers between 0-2.

Example:

```md
elevator(0, 1, 0) # => "left"
elevator(0, 1, 1) # => "right"
elevator(0, 1, 2) # => "right"
elevator(0, 0, 0) # => "right"
elevator(0, 2, 1) # => "right"
```

Console:

```js
function elevator(left, right, call) {
  // code on! :)
}
```

Solution:

JavaScript:

```js
function elevator(left, right, call) {
  //Conditions that favours left lift:
  const condition1 = left === call && right !== call;
  const condition2 = call < left && left < right;
  const condition3 = call > left && left > right;
  if (condition1 || condition2 || condition3) {
    return "left";
  } else {
    return "right";
  }
}
```

```js
const elevator = (left, right, call) =>
  Math.abs(call - left) < Math.abs(call - right) ? "left" : "right";
```

Python:

```py
def elevator(left, right, call):
    condition1 = left == call and not right == call
    condition2 = call < left and left < right
    condition3 = call > left and left > right

    return "left" if condition1 or condition2 or condition3 else "right"
```

```py
def elevator(left, right, call):
    return "left" if abs(call-left) < abs(call-right) else "right"
```

</details>

<details>
  <summary>7. Total amount of points</summary>

Question:

Our team's match results are recorded in a collection of strings. Each match is represented by a string in the format "x:y", where x is our team's score and y is our opponents score.

For example: ["3:1", "2:2", "0:1", ...]

Points are awarded for each match as follows:

if x > y: 3 points (win)
if x < y: 0 points (loss)
if x = y: 1 point (tie)

We need to write a function that takes this collection and returns the number of points our team (x) got in the championship by the rules given above.

Notes:

our team always plays 10 matches in the championship
0 <= x <= 4
0 <= y <= 4

Console:

```js
function points(games) {
  return 0;
}
```

Solution:

JavaScript:

```js
function points(games) {
  let total = 0;
  for (let score of games) {
    const x = parseInt(score[0]);
    const y = parseInt(score[2]);
    const num = x > y ? 3 : x === y ? 1 : 0;
    total += num;
  }
  return total;
}
```

```js
function points(games) {
  return games.reduce((output, current) => {
    let x = parseInt(current[0]);
    let y = parseInt(current[2]);
    let value = x > y ? 3 : x === y ? 1 : 0;
    return output + value;
  }, 0);
}
```

```js
const points = (games) =>
  games.reduce((output, current) => {
    return (output +=
      current[0] > current[2] ? 3 : current[0] === current[2] ? 1 : 0);
  }, 0);
```

Python:

```py
def points(games):
    total = 0
    for x in games:
        if x[0]>x[2]:
            total += 3
        elif x[0]==x[2]:
            total += 1
        else:
            pass
    return total
```

```py
def points(games):
	return sum([3 if x[0]>x[2] else 1 if x[0]==x[2] else 0 for x in games])
```

</details>

<details>
  <summary>8. Pillars</summary>

Question:

There are pillars near the road. The distance between the pillars is the same and the width of the pillars is the same. Your function accepts three arguments:

number of pillars (≥ 1);
distance between pillars (10 - 30 meters);
width of the pillar (10 - 50 centimeters).
Calculate the distance between the first and the last pillar in centimeters (without the width of the first and last pillar).

Console:

```js
function pillars(numPill, dist, width) {
  // your code here
}
```

Solution:

JavaScript:

```js
function pillars(numPill, dist, width) {
  return numPill === 1
    ? 0
    : (numPill - 1) * (dist * 100) + width * (numPill - 2);
}
```

```js
function pillars(numPill, dist, width) {
  return (numPill - 1) * (dist * 100) + Math.max(numPill - 2, 0) * width;
}
```

Python:

```py
def pillars(num_pill, dist, width):
    return 0 if num_pill == 1 else (num_pill-1)*(dist*100) + (num_pill-2)*width
```

```py
def pillars(n, dist, width):
    return (n-1) * dist * 100 + max(n-2, 0) * width
```

</details>

<details>
  <summary>9. Twice as old</summary>

Question:

Your function takes two arguments:

current father's age (years)
current age of his son (years)
Сalculate how many years ago the father was twice as old as his son (or in how many years he will be twice as old). The answer is always greater or equal to 0, no matter if it was in the past or it is in the future.

Console:

```js
function twiceAsOld(dadYearsOld, sonYearsOld) {
  // your code here
}
```

Solution:

JavaScript:

```js
function twiceAsOld(dadYearsOld, sonYearsOld) {
  let dadAge = dadYearsOld - sonYearsOld;
  let sonAge = 0;

  while (dadAge / 2 !== sonAge) {
    dadAge++;
    sonAge++;
  }
  return Math.abs(dadYearsOld - dadAge);
}
```

```js
function twiceAsOld(dadYearsOld, sonYearsOld) {
  return Math.abs(dadYearsOld - 2 * sonYearsOld);
}
```

Python:

```py
def twice_as_old(dad_years_old, son_years_old):
    dad_age = dad_years_old - son_years_old
    son_age = 0

    while True:
        dad_age += 1
        son_age += 1
        if dad_age/2 == son_age:
            break
    return abs(dad_years_old-dad_age)
```

```py
def twice_as_old(dad_years_old, son_years_old):
    return abs(dad_years_old - 2*son_years_old)
```

</details>

<details>
  <summary>10. Total pressure calculation</summary>

Question:

Given the molecular mass of two molecules M1 and M2, their masses present m1 and m2 in a vessel of volume V at a specific temperature T, find the total pressure Ptotal exerted by the molecules. Formula to calculate the pressure is:

```bs
Ptotal = (m1/M1+m2/M2)RT/V
```

Input
Six values :
-M1,M2: molar masses of both gases, in grams (g)
-m1 and m2: present mass of both gases, in g⋅mol−1
-V: volume of the vessel, in dm3
-T: temperature, in °C

Output
One value: Ptotal in units of atmatmatm.

Notes
Remember: Temperature is given in Celsius while SI unit is Kelvin (K).

```bs
0°C=273.15K
```

The gas constant R=0.082dm3⋅atm⋅K−1⋅mol−1

Console:

```js
solution = (molarMass1, molarMass2, givenMass1, givenMass2, volume, temp) => {
  // your code goes here
};
```

Solution:

JavaScript:

```js
solution = (molarMass1, molarMass2, givenMass1, givenMass2, volume, temp) => {
  temp = temp + 273.15;
  return (
    ((givenMass1 / molarMass1 + givenMass2 / molarMass2) * 0.082 * temp) /
    volume
  );
};
```

```js
solution = (molarMass1, molarMass2, givenMass1, givenMass2, volume, temp) => {
  return (
    ((givenMass1 / molarMass1 + givenMass2 / molarMass2) *
      0.082 *
      (temp + 273.15)) /
    volume
  );
};
```

Python:

```py
def solution(molar_mass1, molar_mass2, given_mass1, given_mass2, volume, temp) :
    temp = temp + 273.15
    return ((given_mass1/molar_mass1) + (given_mass2/molar_mass2)) * 0.082 * temp / volume
```

```py
def solution(molar_mass1, molar_mass2, given_mass1, given_mass2, volume, temp) :
    return (given_mass1/molar_mass1 + given_mass2/molar_mass2) * 0.082 * (temp + 273.15) / volume
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
