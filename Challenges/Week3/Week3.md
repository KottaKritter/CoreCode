# CoreCode

- [Monday](#week-3-monday-challenges)
- [Tuesday](#week-3-tuesday-challenges)
- [Wednesday](#week-3-wednesday-challenges)
- [Thursday](#week-3-thursday-challenges)


## Week 3 Monday Challenges

### Challenge 1
```javascript

function likes(names) {
    names = names || [];
    switch(names.length){
      case 0: return 'no one likes this'; break;
      case 1: return names[0] + ' likes this'; break;
      case 2: return names[0] + ' and ' + names[1] + ' like this'; break;
      case 3: return names[0] + ', ' + names[1] + ' and ' + names[2] + ' like this'; break;
      default: return names[0] + ', ' + names[1] + ' and ' + (names.length - 2) + ' others like this';
    }
  }
  
  ```
  
### Challenge 2
  ```javascript
  
var countBits = function(n) {
    n = n.toString(2).replace(/0/g,'').split('');
    let count = 0;
    for (let i = 0; i < n.length; i++){
        count += parseInt(n[i]);
    }
    return count;
};
  
```

### Challenge 3
```javascript

decodeMorse = function(morseCode){
  return morseCode.split('   ').map(word => word.split(' ').map(character => MORSE_CODE[character]).join('')).join(' ').trim();
}

```

## Week 3 Tuesday Challenges

### Challenge 1

```javascript

function order(sentence){
   if (sentence) {
    let finalArr = []
    sentence.split(' ').forEach(sentence => {
      let index = Number(sentence.match(/\d+/g));
      finalArr[index - 1] = sentence
    })
    return finalArr.join(' ')
  }
  return sentence;
}

```

### Challenge 2
```javascript

function duplicateCount(text){
    let count = 0;
    let obj = {};

    for (let i of text) {
        i = i.toLowerCase();
        if (!obj[i]) {
            obj[i] = 1;
        } else {
            obj[i]++;
        }
    }
    for (let i in obj){
        if(obj[i] > 1){
            count++;
        }
    }
    return count;
}

```

### Challenge 3
```javascript

function pigIt(str){
 let newArr = [],
     strArr = str.split(' ')
 strArr.forEach(x => {
   let wordArr = x.split('')
   wordArr.push(wordArr[0] , 'ay'), wordArr.shift()
   if(x === '!' || x === '?' || x === '.'){
     newArr.push(x)
   }else {
     newArr.push(wordArr.join(''))
   }
 })
  return newArr.join(' ')
}

```

## Week 3 Wednesday Challenges

### Challenge 1
```javascript

function validParentheses(p) {
  let stack = [];
  let closings = {
    '(': ')',
  };
  
  for (let i = 0; i < p.length; i++) {
    if (p[i] === '(' ) {
      stack.push(closings[p[i]])
      continue;
    }
    
    let requiredElement = stack.pop();
    
    if (p[i] !== requiredElement) return false;
  }
  
  if (stack.length > 0) return false;
  
  return true;
};

```

### Challenge 2
```javascript

function toCamelCase(str){
  str = str.split('');
  return str.map(function(c, i){
    if(c == '-' || c == '_'){
      c = str[i+1].toUpperCase();
      str.splice(i+1, 1);
    }
    return c;
  }).join('');
}

```

### Challenge 3
```javascript

var uniqueInOrder=function(iterable){
    let newArr = [];
    for (let i = 0; i < iterable.length; i++){
        if (iterable[i] != iterable[i+1]){
            newArr.push(iterable[i]);
        }
    }
    return newArr;
}

```

## Week 3 Thursday Challenges

### Challenge 1
```javascript

function foldArray(array, runs){
  var final = [];
  var newArray = array.slice();

  while(newArray.length > 1){
    final.push(newArray[0] + newArray[newArray.length -1]);
    newArray = newArray.slice(1, newArray.length-1);
  }
  if(newArray.length > 0){
    final.push(newArray[0]); 
  }
  if(runs > 1){
    return foldArray(final, runs-1)
  }
  return final;
}

```

### Challenge 2
```javascript

function encryptThis(text) {
  let strArr = text.split(' ');
  let output = [];
  
  strArr.forEach(str => {
    if (str.length === 1) {
      output.push(str.charCodeAt(0));
    } 
    else {
      let tempStr = str.split('');
      tempStr[0] = str.charCodeAt(0);
      tempStr[1] = str[str.length - 1];
      tempStr[str.length - 1] = str[1];
      output.push(tempStr.join(''));
    }
  });
  
  return output.join(' ');
}

```

### Challenge 3
```javascript

function list(names){
 if (names.length > 1) {
   return `${otherNames(names)} & ${names[names.length - 1].name}`
 } else if (names.length === 1) {
   return names[0].name
 }
  return '';
}

function otherNames(array) {
  return array.splice(0, array.length - 1).map(person => person.name).join(', ');
}

```
