#Objects

If I want to alphebitize the keys of an object, how would i do so?


##Object.assign()
Creates a new object 

##Object.values()
Pulls all the values off of an object and creates an array containing each value in order

var stuff = {
        name: "Alfred",
        hobby: "Coding",
        color: "Gray",
    }

let upperCaseValues = Object.values(stuff).map(x => x.toUpperCase())
Object.values(stuff) === ["Alfred", "Coding", "Gray"]
upperCaseValues = ['CODING', 'ALFRED', 'GRAY']

This could be used in conjuction with Array.map() to change each of the values in an object with whatever callback function is passed into the Array.map().


