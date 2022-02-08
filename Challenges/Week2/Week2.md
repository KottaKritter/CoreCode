# CoreCode

- [Tuesday](#week-2-tuesday-challenges)
- [Wednesday](#week-2-wednesday-challenges)
- [Thursday](#week-2-thursday-challenges)

## Week 2 Tuesday Challenges

### Challenge 1
```javascript

function multiply(a, b){
  return a * b
}

```

### Challenge 2
```javascript

function uniTotal (string) {
// total up dem unicodes!
let l = string.length;
let sum = 0;
let a = 0;

for(let i = 0; i < l; i++){
    a = string.charCodeAt(i);
    sum = sum + a;
}
return sum;
}

```

### Challenge 3
```javascript

function getChar(i){
 return String.fromCharCode(i);
}

```

### Challenge 4
```javascript

function addBinary(a,b) {
  return(a + b).toString(2);
}

```

### Challenge 5
```javascript

function finalGrade (exam, projects) {
  if (exam > 90 || projects > 10) return 100;
  else if (exam > 75 && projects >= 5) return 90;
  else if (exam > 50 && projects >= 2) return 75;
  else return 0;
}

```

## Week 2 Wednesday Challenges

### Challenge 1
```javascript

function dutyFree(normPrice, discount, hol){
  return Math.trunc( hol / ( normPrice * ( discount
/ 100)));
}

```

### Challenge 2
```javascript

function twiceAsOld(dadYearsOld, sonYearsOld) {
  return Math.abs(dadYearsOld - 2 * sonYearsOld);
}

```

### Challenge 3
```javascript

function validSpacing(s) {
 const reg = /(^\s|\s$|\s{2,})/;
  return !(reg.test(s));
}

```

### Challenge 4
```javascript

function fakeBin(x){
var bin = "";
for (var i = 0; i<x.length; i++){
if(x[i]<5){
bin+=0;}

else if (x[i]>=5){
bin+=1;
}
}
return bin;
}

```

## Week 2 Thursday Challenges

### Challenge 1
```javascript

function remove(s)
{
    while(s && s.slice(-1) == "!") 
    { 
        s = s.slice(0,-1) 
    }
    return s;
}

```

### Challenge 2
```javascript

function shortcut(string) {
  return string.replace(/[aeiou]+/g, '')
}

```

### Challenge 3
```javascript

const rps = (p1, p2) => {
  if (p1 === p2) return 'Draw!'
  
  const rules = { paper: 'rock', rock: 'scissors', scissors: 'paper'}
  return rules[p1] === p2 ? 'Player 1 won!' : 'Player 2 won!'
 
};

```

### Challenge 4
```javascript

function persistence(num) {
   let i = 0;
   while (num.toString().length !== 1) {
     num = num.toString().split("").reduce((a,b)=>a*b);
     i++;
   }
   return i;
}

```

### Core Challenge

**Let’s write our Mission Statement!** In **one paragraph**, please answer to the next 5 questions:

1. Who are you?
2. What background do you have?
3. Who do you want to be?
4. What do you want to do?
5. What are the core values and principles that govern your character and contributions?

```
I’m Ricardo. I've been working as a technical support technician for the last 10 years. I want to become a react developer.  
I want to create applications to automate processed to make our lives easier.  
I’m a curious and committed person that believes that efficiency is the key to a balanced life, and I will work hard to achieve that.

```
