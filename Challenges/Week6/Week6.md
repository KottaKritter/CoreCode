- [Monday](#week-6-monday-challenges)
- [Wednesday](#week-6-wednesday-challenges)

## Week 6 Monday Challenges

### Menu 

#### Unique ID

```typescript
  $ npm install uuid
  $ npm install --save @types/uuid
  
  ```
  
  ```typescript
  import { v4 as uuidv4 } from "uuid";
  let uniqueId = uuidv4(); // this would return a unique id

```

#### App.ts

```typescript
import { Main } from "./Main";

const program = new Main();
program.start();

```


#### Main.ts

```typescript
import { Menu } from "./Menu";
export class Main {
  async start() {
    const menu = new Menu();
    await menu.showMainMenu();
  }
}

```

## Week 6 Wednesday Challenges

### Build Tower 

```typescript
export const towerBuilder = (nFloors: number): string[] => {
  let base: string = "*".repeat(nFloors * 2 - 1);
  let tower: Array<string> = [];
  tower.push(base);
  for (let i = 0; i < nFloors - 1; i++) {
    base = base.replace(/\S/, " ");
    base = base.replace(/\*$|\*(?=\s)/, " ");
    tower.push(base);
  }
  return tower.reverse();
};

```

### Highest Scoring Word

```typescript
export const high = (str: string): string => {
  let wordWheigt = str.split(" ").map((word) => {
    let hprev = word.split("").reduce((p, c) => {
      return p + c.charCodeAt(0) - 96;
    }, 0);
    return { word: word, wheight: hprev };
  });
  wordWheigt.sort((a, b) => b.wheight - a.wheight);

  return wordWheigt[0].word;
};

```

### Equals Side of an Array 

```typescript
export function findEvenIndex(arr: number[]): number {
  for (let i = 0; i < arr.length; i++) {
    let left = arr.slice(0, i).reduce((a, b) => a + b, 0);
    let right = arr.slice(i + 1, arr.length).reduce((a, b) => a + b, 0);
    if (left === right) return i;
  }
  return -1;
}

```

### Meeting

```typescript
export function meeting(s: string): string {
  let persons = s.split(";").map((person) => {
    let personNames = person.split(":");
    return {
      name: personNames[0].toUpperCase(),
      lastName: personNames[1].toUpperCase(),
    };
  });

  persons.sort((a, b) => {
    if (a.lastName < b.lastName) return -1;
    if (a.lastName > b.lastName) return 1;
    if (a.lastName == b.lastName) {
      if (a.name < b.name) return -1;
      if (a.name > b.name) return 1;
    }
    return 0;
  });

  return persons.reduce((prev, curr) => {
    return prev + `(${curr.lastName}, ${curr.name})`;
  }, "");
}

```

### Street Fighter 2 - Character Selection

```typescript
export function streetFighterSelection(
  fighters: Array<string[]>,
  position: number[],
  moves: string[]
) {
  let fightersHover: Array<string> = [];
  let vertical: number = position[0];
  let horizontal: number = position[1];
  moves.forEach((move) => {
    if (move === "up") vertical = 0;
    if (move === "down") vertical = 1;
    if (move === "right" && horizontal < 6) horizontal++;
    if (move === "right" && horizontal == 6) horizontal = 0;
    if (move == "left" && horizontal < 6) horizontal--;
    if (move == "left" && horizontal < 0) horizontal = fighters[0].length - 1;
    fightersHover.push(fighters[vertical][horizontal]);
  });
  return fightersHover;
}

```
