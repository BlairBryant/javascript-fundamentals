A good use of recursion is to to pull data out of deeply nested objects. A for loop would not suffice for this if you don't know how far things are nested.

Have a base case.

Recursion Example:

//Problem
A young man asks as compensation only 1 grain of rice for the first square, 2 grains for the second, 4 for the third, 8 for the fourth and so on, always doubling the previous.
Your task is: Given an amount of grains, return up to which square of the chessboard one should count in order to get at least as many.


//This function recursively determines the number of grains that would be produced given the number of squares passed in as an argument.
//Samples of numbers returned: Day 1 - 1, Day 2 - 3, Day 3 - 7, Day 6 - 63...
function numberOfGrains(squares){
    //The base case will always end up returning 1 if the number of squares passed in is greater than 0.
    if(squares < 2) return squares
    return 2 * numberOfGrains(squares-1) + 1
}

//This function calls our recursive function to determine how many squares would be necessary.
function squaresNeeded(grains){
  //If the number of grains passed in is less than or equal to 1, it corresponds to the number of squares necessary.
  if(grains <= 1) return grains
  for (let i = 0; i <= grains; i++) {
    let newGrains = numberOfGrains(i)
    if(newGrains >= grains) return i
  }
}