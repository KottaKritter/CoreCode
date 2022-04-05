# CoreCode

- [Monday](#week-5-monday-challenges)
- [Tuesday](#week-5-tuesday-challenges)
- [Wednesday](#week-5-wednesday-challenges)
- [Thursday](#week-5-thursday-challenges)


## Week 5 Monday Challenges

### Challenge 1

**Read [this](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html) from The primitives: string, number and boolean to Differences Between Type Aliases and Interfaces section**

### Challenge 2

``` typescript
export function squareSum(numbers: number[]): number {
  return numbers.reduce((prev: number, curr: number) => {
    return prev + Math.pow(curr, 2);
  }, 0);
}

```

### Challenge 3

```typescript
export class G964 {
  public static nbYear = (
    p0: number,
    percent: number,
    aug: number,
    p: number
  ) => {
    let years = 0;
    while (p > p0) {
      p0 += p0 * (percent / 100) + aug;
      years++;
    }
    return years;
  };
}

```

### Challenge 4

```typescript
export function accum(s: string): string {
  return s.split("").reduce((prev, curr, index, arr) => {
    return `${prev}${curr[0].toUpperCase()}${curr.repeat(index).toLowerCase()}${
      index < arr.length - 1 ? "-" : ""
    }`;
  }, "");
}

```

### Challenge 5

```typescript
export function warnTheSheep(queue: string[]): string {
  const wolfPosition = queue.indexOf("wolf");
  if (wolfPosition != queue.length - 1) {
    return `Oi! Sheep number ${
      queue.length - 1 - wolfPosition
    }! You are about to be eaten by a wolf!`;
  }
  return "Pls go away and stop eating my sheep";
}

```

## Week 5 Tuesday Challenges

### Challenge 1

```typescript
const rem = [1, 10, 9, 12, 3, 4];

function process(n: number): number {
  let counter: number = 0;
  let sumMultiply = n
    .toString()
    .split("")
    .reverse()
    .reduce((prev, curr) => {
      if (counter > 5) counter = 0;
      return prev + Number(curr) * rem[counter++];
    }, 0);
  if (sumMultiply == n) return sumMultiply;
  return process(sumMultiply);
}

export function thirt(n: number): number {
  return process(n);
}

```

### Challenge 2

```typescript
export class G964 {
  public static digPow = (n: number, p: number) => {
    let number = n
      .toString()
      .split("")
      .reduce((prev, curr) => {
        p++;
        return prev + Math.pow(Number(curr), p - 1);
      }, 0);
    return number % n == 0 ? number / n : -1;
  };
}

```

### Challenge 3

```typescript
export function validBraces(braces: string): boolean {
  const arrayBraces = braces.split("");
  let counter: number = 0;
  let result: boolean = false;
  for (let i = 0; i < arrayBraces.length; i++) {
    if (arrayBraces[i] == ")") {
      counter--;
      if (arrayBraces[i - 1] == "(") result = true;
    } else if (arrayBraces[i] == "}") {
      counter--;
      if (arrayBraces[i - 1] == "{") result = true;
    } else if (arrayBraces[i] == "]") {
      counter--;
      if (arrayBraces[i - 1] == "[") result = true;
    } else {
      counter++;
    }
    if (counter < 0) return false;
  }
  return result;
}

```

### Challenge 4

```javascript

```

### Challenge 5

```javascript
function displayBoard(board, width) {
  let finishBoard = "";
  const rows = board.length / width;
  const rowSeparate = "-";
  let positions = 0;
  for (let i = 0; i < rows; i++) {
    for (let j = 0; j < width; j++) {
      finishBoard += ` ${board[positions++]} ${j < width - 1 ? "|" : ""}`;
    }
    finishBoard += `${
      i < rows - 1 ? `\n${rowSeparate.repeat(width * 4 - 1)}\n` : ""
    }`;
  }

  return finishBoard;
}

```

## Week 5 Wednesday Challenges

### Challenge 1

```typescript
export function duplicateEncode(word: string) {
  return word
    .toLowerCase()
    .split("")
    .reduce((prev, curr, index, array) => {
      let regex = new RegExp(`[${curr}]|\curr`, "g");
      return prev + `${array.join("").match(regex)?.length == 1 ? "(" : ")"}`;
    }, "");
}

```

### CHallenge 2

```typescript
function findOdd(A) {
  let counter = 1;
  let result = 0;
  A.sort((a, b) => a - b).forEach((value, index, array) => {
    if (value == array[index + 1]) {
      counter++;
    } else {
      if (counter % 2 != 0) {
        result = value;
      }
      counter = 1;
    }
  });
  return result;
}

```

### Challenge 3

```typescript
export class G964 {
  public static inArray(a1: string[], a2: string[]): string[] {
    let result: Array<string> = [];
    a1.forEach((val) => {
      for (let i = 0; i < a2.length; i++) {
        if (a2[i].match(val) && result.indexOf(val) == -1) result.push(val);
      }
    });
    return result.sort();
  }
}

```

### Challenge 4

```typescript
export function partsSums(ls: number[]): number[] {
  let result: Array<number> = ls.map((num, i, arr) => {
    return arr.slice(i).reduce((p, c) => p + c);
  });
  result.push(0);
  return result;
}

```

### Challenge 5

```typescript
export function longestConsec(strarr: string[], k: number): string {
  let concatStrings: string[] = strarr.map((v, i, a) => {
    return a.slice(i, i + k).join("");
  });

  let greatest: number = concatStrings
    .map((val) => val.length)
    .sort((a, b) => b - a)[0];

  if (strarr.length == 0 || k > strarr.length || k <= 0) return "";
  return concatStrings.find((val) => val.length == greatest) || "";
}

```

## Week 5 Thursday Challenges

### Challenge 1

```typescript
import { Tile } from "./Tile";
export class Main {
  start() {
    const A = new Tile("A", 10);
    A.printTile(); // Example of a reader-friendly format above
    /*
      ==================
        Letter: A
        Value: 10
      ==================
    */
    const W = new Tile("W", "50"); // This should show and error
  }
}

```

### Challenge 2

```typescript
import { Time } from "./Time";
export class Main {
  start() {
    const t = new Time(10, 45, 1);
    t.printTime(); // Example of a reader-friendly format above
    /*
      ==================
        Hours: 10
        Minutes: 45
        Seconds: 1
      ==================
    */
    console.log(t.getInSeconds()); // 38701
  }
}

```

### Challenge 3

```typescript
import { Rational } from "./Rational";
export class Main {
  start() {
    const r1 = new Rational(36, 120);
    r1.printRational(); // 36 / 120
    console.log(r1.toFloat()); // 0.3
    r1.reduce();
    r1.printRational(); // 3 / 10
    r1.invert();
    r1.printRational(); // 10 / 3
    r1.reduce();
    r1.printRational(); // 10 / 3
  }
}

```
