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

## Week 3 Wednesday Challenges

## Week 3 Thursday Challenges
