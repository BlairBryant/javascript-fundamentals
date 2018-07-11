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