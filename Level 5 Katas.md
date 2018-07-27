//Calculating with Functions

There must be a function for each number from 0 ("zero") to 9 ("nine")
There must be a function for each of the following mathematical operations: plus, minus, times, dividedBy (divided_by in Ruby)
Each calculation consist of exactly one operation and two numbers
The most outer function represents the left operand, the most inner function represents the right operand
Divison should be integer division, e.g eight(dividedBy(three()))/eight(divided_by(three)) should return 2, not 2.666666...

seven(times(five())); // must return 35
four(plus(nine())); // must return 13
eight(minus(three())); // must return 5
six(dividedBy(two())); // must return 3

function zero(arr) {
  if(arr) {
    if (arr[0] === 'plus') return 0 + arr[1]
    if (arr[0] === 'minus') return 0 - arr[1]
    if (arr[0] === 'multiply') return 0 * arr[1]
    if (arr[0] === 'divide') return Math.floor(0 / arr[1]))
  } else {
    return 0
  }
}
function one(arr) {
  if(arr) {
    if (arr[0] === 'plus') return 1 + arr[1]
    if (arr[0] === 'minus') return 1 - arr[1]
    if (arr[0] === 'multiply') return 1 * arr[1]
    if (arr[0] === 'divide') return Math.floor(1 / arr[1])
  } else {
    return 1
  }
}
function two(arr) {
  if(arr) {
    if (arr[0] === 'plus') return 2 + arr[1]
    if (arr[0] === 'minus') return 2 - arr[1]
    if (arr[0] === 'multiply') return 2 * arr[1]
    if (arr[0] === 'divide') return Math.floor(2 / arr[1])
  } else {
    return 2
  }
}
function three(arr) {
  if(arr) {
    if (arr[0] === 'plus') return 3 + arr[1]
    if (arr[0] === 'minus') return 3 - arr[1]
    if (arr[0] === 'multiply') return 3 * arr[1]
    if (arr[0] === 'divide') return Math.floor(3 / arr[1])
  } 
    return 3
}
function four(arr) {
  if(arr) {
    if (arr[0] === 'plus') return 4 + arr[1]
    if (arr[0] === 'minus') return 4 - arr[1]
    if (arr[0] === 'multiply') return 4 * arr[1]
    if (arr[0] === 'divide') return Math.floor(4 / arr[1])
  } 
    return 4
}
function five(arr) {
  if(arr) {
    if (arr[0] === 'plus') return 5 + arr[1]
    if (arr[0] === 'minus') return 5 - arr[1]
    if (arr[0] === 'multiply') return 5 * arr[1]
    if (arr[0] === 'divide') return Math.floor(5 / arr[1])
  } 
    return 5
}
function six(arr) {
  )if(arr) {
    if (arr[0] === 'plus') return 6 + arr[1]
    if (arr[0] === 'minus') return 6 - arr[1]
    if (arr[0] === 'multiply') return 6 * arr[1]
    if (arr[0] === 'divide') return Math.floor(6 / arr[1])
  } 
    return 6
}
function seven(arr) {
  if(arr) {
    if (arr[0] === 'plus') return 7 + arr[1]
    if (arr[0] === 'minus') return 7 - arr[1]
    if (arr[0] === 'multiply') return 7 * arr[1]
    if (arr[0] === 'divide') return Math.floor(7 / arr[1])
  } 
    return 7
}
function eight(arr) {
  if(arr) {
    if (arr[0] === 'plus') return 8 + arr[1]
    if (arr[0] === 'minus') return 8 - arr[1]
    if (arr[0] === 'multiply') return 8 * arr[1]
    if (arr[0] === 'divide') return Math.floor(8 / arr[1])
  } 
    return 8
}
function nine(arr) {
  if(arr) {
    if (arr[0] === 'plus') return 9 + arr[1]
    if (arr[0] === 'minus') return 9 - arr[1]
    if (arr[0] === 'multiply') return 9 * arr[1]
    if (arr[0] === 'divide') return Math.floor(9 / arr[1])
  } 
    return 9
}

function plus(num) {
  return ['plus', num]
}
function minus(num) {
  return ['minus', num]
}
function times(num) {
  return ['multiply', num]
}
function dividedBy(num) {
  return ['divide', num]
}

six(dividedBy(eight()))


---------------------------------------------------------


//Weight for weight

https://www.codewars.com/kata/weight-for-weight/train/javascript

function orderWeight(str) {
  if (str.length === 0) return ""
  let arr = []
  str.split(' ').forEach(x => {
    let newNum = 0
    for (let i = 0; i < x.length; i++) {
      newNum += +x[i]
    }
    arr.push(newNum)
    arr.sort((a, b) => a - b)
  })

  str.split(' ').sort().forEach(x => {
    let newNum = 0
    for (let j = 0; j < x.length; j++) {
      newNum += +x[j]
    }
    arr[arr.indexOf(newNum)] = x
  })
  return arr.join(' ')
}


// Moving Zeroes To The End
https://www.codewars.com/kata/52597aa56021e91c93000cb0/solutions/javascript

var moveZeros = function (arr) {
  let count = 0
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === 0) {
      arr.splice(i, 1)
      i--
      count++
    }
  }
  for (let i = 0; i < count; i++) {
    arr.push(0)
  }
  return arr
}

--------------------------------------------------------------------------
############
Integers: Recreation One
https://www.codewars.com/kata/integers-recreation-one/train/javascript
Doesn't run within time limit.

function squaring(num) {
  let arr = []
  for (let i = 1; i <= num; i++) {
    if (num % i === 0) arr.push(Math.pow(i, 2))
  }
  let squaredSum = arr.reduce((x, y) => x + y)
  if (Number.isInteger(Math.sqrt(squaredSum))) return squaredSum
  return false
}

function listSquared(m, n) {
  let ans = []
  let currentNum;
  for (let i = m; i <= n; i++) {
    currentNum = squaring(i)
    if (currentNum) ans.push([i, currentNum]) 
  }
  return ans
}

listSquared(1, 5000)


----------------------------------------------------------------------
Did I Finish my Sudoku?
https://www.codewars.com/kata/did-i-finish-my-sudoku/train/javascript


function doneOrNot(board){
  let tempArr = []
  let squareArr = [[],[],[],[],[],[],[],[],[]]
  for(let i = 0; i < 9; i++) {
    if (board[i].reduce((x, y) => x + y) !== 45) return 'Try again!'
    for (let j = 0; j < 9; j++) {
      if(!board[i][j]) return 'Try again'
      tempArr.push(board[j][i])
      if (i < 3) {
        if (j < 3) squareArr[0].push(board[i][j])
        else if (j < 6) squareArr[1].push(board[i][j])
        else squareArr[2].push(board[i][j])
      }
      else if (i < 6) {
        if (j < 3) squareArr[3].push(board[i][j])
        else if (j < 6) squareArr[4].push(board[i][j])
        else squareArr[5].push(board[i][j])
      } else {
          if (j < 3) squareArr[6].push(board[i][j])
          else if (j < 6) squareArr[7].push(board[i][j])
          else squareArr[8].push(board[i][j])
      }
    }
    if (tempArr.reduce((x, y) => x + y) !== 45) return 'Try again!'
    tempArr = []
  }
  squareArr.forEach(x => {
    if (x.reduce((x, y) => x + y !== 45)) return 'Try again!'
  })
  let toggle = true
  squareArr.forEach(x => {
    x.forEach((y, i) => {
      if (x.indexOf(y) !== i) toggle = false
    })
  })
  if (!toggle) return 'Try again!'
  return 'Finished!'
}

-----------------------------------------------------------------------
Pick peaks
https://www.codewars.com/kata/pick-peaks/train/javascript
I was able to do this problem with only loop, where most people used multiple.

function pickPeaks(arr){
  let current = []
  let pos = []
  let peaks = []
  for (let i = 1; i < arr.length; i++) {
    if (arr[i] > arr[i-1]) current = [i, arr[i]]
    if (current[1] > arr[i]) {
      pos.push(current[0])
      peaks.push(current[1])
      current = 0
    }
  }
  return {pos,peaks}
}

----------------------------------------------------------------------
Pete, the baker
https://www.codewars.com/kata/pete-the-baker/javascript

function cakes(recipe, available) {
  let arr = []
  for (let x in available) {
    if (recipe.hasOwnProperty(x)) arr.push(Math.floor([available[x] / recipe[x]]))
  }
  return arr.length === Object.keys(recipe).length ? arr.sort((a, b) => a -b)[0] : 0
}

----------------------------------------------------------------------
############
First non-repeating character
https://www.codewars.com/kata/first-non-repeating-character

function firstNonRepeatingLetter(s) {
  let obj = {}
  for (let i = 0; i < s.length; i++) {
    if (obj.hasOwnProperty(s[i])) s[i].toUpperCase() === s[i] ? obj[s[i]] += 'u' : obj[s[i]] += 'l'
    else s[i].toUpperCase() === s[i] ? obj[s[i].toUpperCase()] = 'u' : obj[s[i].toUpperCase()] = 'l'
  }
  console.log(obj)
  for (let x in obj) {
    if (obj[x].length === 1) return obj[x] === 'u' ? x : x.toLowerCase() 
  }
  return ''
}

firstNonRepeatingLetter('sT9reS2S')

I was able to solve this with only letters, but no numbers or symbols.


----------------------------------------------------------------------
XXXXXXXXXXXXXXXXXXXX
Find the smallest
https://www.codewars.com/kata/find-the-smallest

function smallest(n) {
  let str = n.toString().split('')
  
  let sorted = n.toString().split('').sort((a, b) => a - b)
  if (str[0] > sorted[0] && str[1] === sorted[0]) {
    let removed = str.splice(1, 1)
    str.splice(0,0,removed[0])
    return [+str.join(''), 0, 1]
  }
  for (let i = 0; i < str.length; i++) {
    if (str[0])
  }
  let idx = str.indexOf(sorted[0])
  let removed = str.splice(idx, 1)
  str.splice(0, 0, removed[0])
  console.log(str)
  return [+str.join(''), idx, 0]
}

smallest(285365)


----------------------------------------------------------------------
XXXXXXXXXXXXXXXXXXXXXXXXX
Vector class
https://www.codewars.com/kata/vector-class/train/javascript

var Vector = function (components) {
  this.components = components
  this.add = function(arr) {
    if(arr.components.length === this.components.length) {
      return this.components.map((x, i) => x += arr.components[i])
    }
    console.log('error')
  }
  this.subtract = function(arr) {
    if(arr.components.length === this.components.length) {
      return this.components.map((x, i) => x -= arr.components[i])
    }
    console.log('error')
  }
  this.dot = function(arr) {
    if(arr.components.length === this.components.length) {
      return this.components.map((x, i) => x *= arr.components[i]).reduce((a, b) => a + b)
    }
    console.log('error')
  }
  this.norm = function() {
    return Math.sqrt(this.components.map(x => x = Math.pow(x, 2)).reduce((a, b) => a + b))
  }
};

let a = new Vector([1, 4, 6])
let b = new Vector([2, 5, 6])

a.norm()


----------------------------------------------------------------------
Josephus Permutation
https://www.codewars.com/kata/josephus-permutation/train/javascript

function josephus(items,k){
  let itemsLength = items.length
  let ans = []
  let i = 0
  let current = 1
  while (ans.length < itemsLength) {
    if (i === items.length) i = 0
      else if (current === k) {
      ans.push(items[i])
      items.splice(i, 1)
      current = 1
    } else {
      i++
      current++
    }
  }
  return ans
}
----------------------------------------------------------------------
Greed is Good
https://www.codewars.com/kata/greed-is-good/train/javascript

function score(dice) {
  dice.sort()
  let points = 0
  let tripleCheck = 0
  for (let i = 1; i < dice.length; i++) {
    if (dice[i] === dice[i-1] && dice[i] === dice[i+1]) {
      tripleCheck = dice[i]
      break;
    }
  }
  if (tripleCheck === 1) points += 1000
  if (tripleCheck > 1 && tripleCheck < 7) points += tripleCheck * 100
  let idx = dice.indexOf(tripleCheck)
  console.log(tripleCheck)
  tripleCheck ? dice.splice(idx, 3) : null
  console.log(dice)
  for (let i = 0; i < dice.length; i++) {
    if (dice[i] === 1) points += 100
    if (dice[i] === 5) points += 50
  }
  return points
}

----------------------------------------------------------------------
Math Issues
https://www.codewars.com/kata/math-issues/train/javascript

Math.round = function(number) {
  let n = number.toString().split('')
  let plus = false
  for (let i = 0; i < n.length; i++) {
    if (n[i] === '.') {
      if (n[i+1] > 4) {
        plus = true
      }
      n.splice(i)
    }
  }
  return plus ? +n.join('') + 1 : +n.join('')
};

Math.ceil = function(number) {
  let n = number.toString().split('')
  let flag = false
  for (let i = 0; i < n.length; i++) {
    if (n[i] === '.') {
        n.splice(i)
        flag = true
    }
  }
  return flag ? +n.join('') + 1 : number
};

Math.floor = function(number) {
    let n = number.toString().split('')
  for (let i = 0; i < n.length; i++) {
    if (n[i] === '.') {
        n.splice(i)
    }
  }
  return + n.join('')
};
----------------------------------------------------------------------
Valid Parentheses
https://www.codewars.com/kata/valid-parentheses/train/javascript

function validParentheses(parens){
  let left = 0
  let right = 0
  if (parens[0] === ')' || parens[parens.length-1] === '(') return false
  parens.split('').forEach(x => x === '(' ? left++ : right++)
  return left === right
}

----------------------------------------------------------------------


