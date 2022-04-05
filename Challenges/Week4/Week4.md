# CoreCode

- [Tuesday](#week-4-tuesday-challenges)
- [Wednesday](#week-4-wednesday-challenges)
- [Thursday](#week-4-thursday-challenges)



## Week 4 Tuesday Challenges

###  TypeScript Object type

```typescript
export type User = { name: string; age: number; occupation: string };

export const users: User[] = [
  {
    name: "Max Mustermann",
    age: 25,
    occupation: "Chimney sweep",
  },
  {
    name: "Kate Müller",
    age: 23,
    occupation: "Astronaut",
  },
];

export function logPerson(user: User) {
  console.log(` - ${user.name}, ${user.age}`);
}

console.log("Users:");
users.forEach(logPerson);

```

### TypeScript Union types

```typescript
interface User {
  name: string;
  age: number;
  occupation: string;
}

interface Admin {
  name: string;
  age: number;
  role: string;
}

export type Person = User | Admin;

export const persons: Person[] /* <- Person[] */ = [
  {
    name: "Max Mustermann",
    age: 25,
    occupation: "Chimney sweep",
  },
  {
    name: "Jane Doe",
    age: 32,
    role: "Administrator",
  },
  {
    name: "Kate Müller",
    age: 23,
    occupation: "Astronaut",
  },
  {
    name: "Bruce Willis",
    age: 64,
    role: "World saver",
  },
];

export function logPerson(user: Person) {
  console.log(` - ${user.name}, ${user.age}`);
}

persons.forEach(logPerson);

```

### TypeScript in Operator

```typescript

interface User {
  name: string;
  age: number;
  occupation: string;
}

interface Admin {
  name: string;
  age: number;
  role: string;
}

export type Person = User | Admin;

export const persons: Person[] = [
  {
    name: "Max Mustermann",
    age: 25,
    occupation: "Chimney sweep",
  },
  {
    name: "Jane Doe",
    age: 32,
    role: "Administrator",
  },
  {
    name: "Kate Müller",
    age: 23,
    occupation: "Astronaut",
  },
  {
    name: "Bruce Willis",
    age: 64,
    role: "World saver",
  },
];

export function logPerson(person: Person) {
  let additionalInformation: string;
  if ("role" in person) {
    additionalInformation = person.role;
  } else {
    additionalInformation = person.occupation;
  }
  console.log(` - ${person.name}, ${person.age}, ${additionalInformation}`);
}

persons.forEach(logPerson);

```

### Find the odd int

```javascript
function findOdd(A) {
  let counter = 1;
  let result = 0;
  A.sort((a, b) => a - b).forEach((value, index, array) => {
    if (value == array[index + 1]) {
      counter++;
    } else {
      if (counter % 2 != 0) {
        console.log("No es numero par", value);
        result = value;
      }
      counter = 1;
    }
  });
  return result;
}

```

### Stop gninnipS My sdroW!

```javascript
function spinWords(string) {
  return string
    .split(" ")
    .reduce((prev, curr) => {
      return `${prev} ${
        curr.length >= 5 ? curr.split("").reverse().join("") : curr
      }`;
    }, "")
    .trim();
}

```
## Week 4 Wednesday Challenges

### Array.dif

```javascript
function arrayDiff(a, b) {
  return a.filter((num) => !b.includes(num));
}

```

### Create Phone Number

```javascript
function createPhoneNumber(numbers) {
  return numbers.join("").replace(/(\d{3})(\d{3})(\d{4})/, "($1) $2-$3");
}

```

## Week 4 Thursday Challenges

### Detect Pangram

```javascript
function isPangram(string) {
  const alphabeth = "abcdefghijklmnopqrstuvwxyz".split("");

  const otherString = string.toLowerCase().replace(/\s|\./g, "").split("");

  for (let i = 0; i < alphabeth.length; i++) {
    if (!otherString.includes(alphabeth[i])) return false;
  }

  return true;
}

```

### Find the missing letter

```javascript
function findMissingLetter(array) {
  const initArray = array.join("").charCodeAt(0);

  for (let i = 0; i < array.length; i++) {
    if (array.join("").charCodeAt(i) != initArray + i)
      return String.fromCharCode(initArray + i);
  }
}

```

### Find the unique number

```javascript
function findUniq(arr) {
  let array = {};
  arr.forEach((element) => {
    array[element] == undefined ? (array[element] = 1) : array[element]++;
  });
  for (const key in array) {
    if (array[key] == 1) return key * 1;
  }
}

```

### Reverse or rotate?

```javascript
function revrot(str, sz) {
  if (sz <= 0 || sz > str.length) return "";
  let regex = new RegExp(`(\\d){${sz}}`, "g");
  return str.match(regex).reduce((prev, curr) => {
    let mod = curr.split("").reduce((prev, cur) => {
      return prev + Math.pow(cur, 3);
    }, 0);
    return `${prev}${
      mod % 2 == 0
        ? curr.split("").reverse().join("")
        : `${curr.substring(1, curr.length)}${curr[0]}`
    }`;
  }, "");
}

```

### What's Your Poison?

```javascript
function find(rats) {
  let bottle = 0;
  rats.forEach((value) => (bottle += Math.pow(2, value)));
  return bottle;
}

```
