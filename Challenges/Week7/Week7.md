- [Tuesday](#week-7-tuesday-challenges)
- [Wednesday](#week-7-wednesday-challenges)
- [Thursday](#week-7-thursday-challenges)

## Week 7 Tuesday Challenges

### Encript this

```typescript
export const encryptThis = (str: string): string => {
  if (str.length === 0) return "";
  return str
    .split(" ")
    .reduce((pre, curr) => {
      return (
        pre +
        `${curr.charCodeAt(0)}${curr
          .slice(1)
          .replace(/(\w)(\w*)(\w)/, "$3$2$1")} `
      );
    }, "")
    .trim();
};


```

### Make the Deadfish Swim

```typescript
export function parse(data: string): number[] {
  let number: number = 0;
  let arrayResult: number[] = [];
  data.split("").forEach((letter) => {
    if (letter === "i") number++;
    if (letter === "s") number = Math.pow(number, 2);
    if (letter === "d") number--;
    if (letter === "o") arrayResult.push(number);
  });
  return arrayResult;
}

```

## Week 7 Wednesday Challenges

### Dashatize it

```typescript
export const dashatize = (num: number) => {
  const abNumber = Math.abs(num);
  if (isNaN(num)) return num.toString();
  return abNumber
    .toString()
    .split("")
    .reduce((ac, cur, i, ar) => {
      let odd: boolean = Number(cur) % 2 != 0;
      if (odd && ac[ac.length - 1] === "-") return ac + `${cur}-`;
      if (!odd) return ac + cur;
      return ac + `-${cur}-`;
    }, "")
    .replace(/(^-)/, "")
    .replace(/(-)$/, "");
};

```

## Week 7 Thursday Challenges

### Type practice

```typescript
interface User {
  type: "user";
  name: string;
  age: number;
  occupation: string;
}

interface Admin {
  type: "admin";
  name: string;
  age: number;
  role: string;
}

export type Person = User | Admin;

export const persons: Person[] = [
  {
    type: "user",
    name: "Max Mustermann",
    age: 25,
    occupation: "Chimney sweep",
  },
  { type: "admin", name: "Jane Doe", age: 32, role: "Administrator" },
  { type: "user", name: "Kate Müller", age: 23, occupation: "Astronaut" },
  { type: "admin", name: "Bruce Willis", age: 64, role: "World saver" },
];

export function isAdmin(person: Person): person is Admin {
  return person.type === "admin";
}

export function isUser(person: Person): person is User {
  return person.type === "user";
}

export function logPerson(person: Person) {
  let additionalInformation: string = "";
  if (isAdmin(person)) {
    additionalInformation = person.role;
  }
  if (isUser(person)) {
    additionalInformation = person.occupation;
  }
  console.log(` - ${person.name}, ${person.age}, ${additionalInformation}`);
}

console.log("Admins:");
persons.filter(isAdmin).forEach(logPerson);

console.log();

console.log("Users:");
persons.filter(isUser).forEach(logPerson);

```

### Count the smiley faces

```typescript
export function countSmileys(arr: string[]) {
  return arr.reduce((pv, cur) => {
    return cur.match(/[;:][~-]{0,1}[\)D]/) ? (pv += 1) : pv;
  }, 0);
}

```

### Human Readable Time

```typescript
export function humanReadable(seconds: number): string {
  let hours: number = 0;
  let minutes: number = 0;
  if (!seconds) return "00:00:00";
  if (seconds >= 3600) {
    hours = Math.trunc(seconds / 3600);
    seconds = seconds - 3600 * hours;
    minutes = Math.trunc(seconds / 60);
    seconds = seconds - 60 * minutes;
  }
  if (seconds >= 60) {
    hours = 0;
    minutes = Math.trunc(seconds / 60);
    seconds = seconds - 60 * minutes;
  }
  return `${hours >= 10 ? hours : `0${hours}`}:${
    minutes >= 10 ? minutes : `0${minutes}`
  }:${seconds >= 10 ? seconds : `0${seconds}`}`;
}

```
