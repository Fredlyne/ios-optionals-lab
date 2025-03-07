# Optionals lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1

`var userName: String?`

Write 3 different ways of safely unwrapping and printing the value of `userName`.  If it is nil, print "No name".

```
//Check for nil and force unwrap
var username: String?
username = "meh"
print(username!)

//Method two: Optional binding
if let username = username {
print(username)
} else {
print("no name")

}

//Method three: Nil coalescing
username = username ?? "no name"
print(username!)
```

## Question 2

Given optional string `backgroundColor`, write code that safely unwraps and prints it. If backgroundColor is nil, give it a value.

```
var backgroundColor: String?
if let backgroundColor = backgroundColor {
print("\(backgroundColor)")
} else {
print("no color")
}
```


## Question 3

Given an optional width and an optional height of a rectangle, write code that calculates and prints the area. Print an error message if either value is nil.

```
var width: Double?
var height: Double?
if let width = width, let height = height {
print(width * height)
}else {
print("area not available")
}
```


## Question 4

Given the following optional variables `name`, `age` and `height`. Write code so that it prints `name`, `age` and `height` if they all have a value. If any are nil, print an error message. Try using optional binding.

```swift
var name: String?
var age: Int?
var height: Double?

if let name = name {
if let age = age {
if let height = height {
print("\(name), \(age), \(height)" )
}
}
} else {
print("fraud")
}
```


## Question 5

Given the variables `firstName`, `middleName` and `lastName`. Create a variable called `fullName` that is a nicely formatted string.

```swift
var firstName: String = "Johnny"
var middleName: String?
var lastName: String = "Stone"

if var middleName = middleName{
} else {
middleName = "no middle name "
}
print("\(firstName), \(middleName!), \(lastName)")


```


## Question 6

Write code that adds 15 to `myIntString`, then prints the sum. Use the `Int()` constructor which returns an optional Int `(Int?)`.

```let myIntString = "35"
if let myIntString = Int(myIntString) {
print(myIntString + 15)
} else {
print("no b")
}
```

## Question 7

Given an optional tuple of optional Ints, write code to safely unwrap the tuple and calculate the sum of its contents that aren't nil.

```swift
var scores: (Int?, Int?, Int?)?
var testCaseOne: (Int?, Int?, Int?)? = (4, nil, 7)
var testCaseTwo: (Int?, Int?, Int?)? = (nil, nil, 9)
var testCaseThree: (Int?, Int?, Int?)? = (5, 10, 24)
let testCases = [testCaseOne, testCaseTwo, testCaseThree]

for testCase in testCases {
var sum = 0

if let unwrappedTestCase = testCase  {
if let firstNumber = unwrappedTestCase.0 {
sum += firstNumber
}
if let secondNumber = unwrappedTestCase.1 {
sum += secondNumber
}
if let thirdNumber = unwrappedTestCase.2 {
sum += thirdNumber
}
}
print(sum)
}


```


## Question 8

Safely unwrap `tuple` if there’s a non-nil tuple value and print it out.

```swift
var tuple: (Int, Int)?

if Bool.random() {
tuple = (5, 3)
if let unwrappedTuple = tuple {
print(unwrappedTuple)
}

} else {
print("its false")
}


```


## Question 9

Write code that either doubles `myInt` and then prints it, or prints an error message if myInt is nil.

```swift
let myInt: Int?

if Bool.random() {
myInt = 5
if let newInt = myInt {
print( newInt * 2)
}
}
else {
print( "value is not a double")
}

```


## Question 10

Write code that prints out the product of `myDouble` and `doubleTwo` or prints an error message if `myDouble` is nil.

```swift
var myDouble: Double?
let doubleTwo: Double = 5

if Bool.random() {
myDouble = 12
if let myDouble = myDouble {
print( myDouble * doubleTwo )
}
}
else {
print ("ERROR ERROR B")
}
```


## Question 11

Determine if the variable contains a Boolean or nil value. If nil set the variable to false, else keep it true.

```var isTheGreatest: Bool?

if Bool.random() {
isTheGreatest = true
}
if let unwrappedGreatest = isTheGreatest {
print(unwrappedGreatest)
} else {
isTheGreatest = false
print(isTheGreatest!)
}

```


## Question 12

Given the code below print the sum of each non-nil element in `myTuple`.

 ```swift
 var myTuple: (Int?, Int?, Int?, Int?)
 var sum = 0
 var arrayOfTuples = [myTuple]
 
 
 if Bool.random() {
 myTuple.0 = 5
 myTuple.2 = 14
 } else {
 myTuple.1 = 9
 myTuple.3 = 10
 }
 
 if let valueOne = myTuple.0  {
 sum += valueOne
 }
 if let valueTwo = myTuple.1 {
 sum += valueTwo
 }
 if let valueThree = myTuple.2 {
 sum += valueThree
 }
 if let valueFour = myTuple.3 {
 sum += valueFour
 }
 print(sum)

```


## Question 13

Given the helper functions and code below, check to see if your `evolutionaryStone` is able to evolve your pokemon.  The table below shows the appropriate matches of pokemon to stone:

| Pokemon	   | Stone    |
| :--------: | :------: |
| Pikachu	   | Electric |
| Bulbasaur	 | Grass    |
| Charmander | Fire     |
| Squirtle	 | Water    |


```swift
// Helper Functions

func eStone() -> String {
let random = Int(arc4random_uniform(5))
switch random {
case 0:
return "Electric"
case 1:
return "Grass"
case 2:
return "Fire"
case 3:
return "Water"
default:
return "No Stone"
}
}

func starterPokemon() -> String {
let random = Int(arc4random_uniform(5))
switch random {
case 0:
return "Pikachu"
case 1:
return "Bulbasaur"
case 2:
return "Charmander"
case 3:
return "Squirtle"
default:
return "Not a Pokemon"
}
}

let pokemon: String?
var evolutionaryStone: String?
var nextOne = false
pokemon = starterPokemon()
evolutionaryStone = eStone()
let array = [("Pikachu", "Electric"), ("Bulbasaur", "Grass"), ("Charmander", "Fire"), ("Squirtle", "Water")]
if let e = pokemon, let m = evolutionaryStone {

for levelup in array {
if (e, m) == levelup {
print("Evolve")
}
}
}
```


## Question 14

Given an optional int `numberOfPeople`, write code that unwraps and prints it **only if it is even**. Try using optional binding with a condition.

```swift
var numberOfPeople: Int?

if Bool.random() {
numberOfPeople = 108
if let realPpl = numberOfPeople {
if realPpl % 2 == 0 {
print(realPpl)
}
}
}
else {
print("now youre ODD B")
}
```


## Question 15

Given the array of optional Ints `someNumbers`, write code to find the product of the array not including any nil values.

```swift
var someNumbers: [Int?] = []

for i in 0..<20 {
    someNumbers.append(Bool.random() ? i : nil)
}
```


## Question 16

Given the array `poorlyFormattedCityNames`, create a new array with the city names capitalized and any nil values removed.

```swift
let poorlyFormattedCityNames: [String?] = ["new york", "BOSTON", nil, "chicago", nil, "los angeles", nil, "Dallas",]

Output: ["New York", "Boston", "Chicago", "Los Angeles", "Dallas"]
```


## Question 17

Given a random array of optional numbers, create a new array of all the even numbers that aren't nil.

```swift
var aBunchOfNumbers: [Int?] = []

for _ in 0..<20 {
 aBunchOfNumbers.append(Bool.random() ? Int(arc4random_uniform(102)) : nil)
}
```


## Question 18

Given the following array of zip codes as strings, write code that turns them into an array of Ints.

`let zipCodeStrings = ["11377", "11101", "11373", "10014", "10003", "11223"]`


## Question 19

Some students were asked some questions about their favorite foods and colors and the answers were stored in an array `studentInfo`.

- Print the names of the students that do not have a favorite color.

- Print the names of the students that don't have a favorite color or a favorite food.

- Create a new array of type `[(String, String, String)]` that contains the students with both favorite colors and foods.

`let studentInfo: [(String, String?, String?)] = [("Bill", "Burgers", "Blue"), ("Rita", nil, "Red"), ("Peter", "Pizza", "Purple"), ("Sarah", "Sandwiches", nil), ("Jeff", nil, nil), ("Lucy", "Leftovers", "Lilac"), ("Mike", "Meat", "Mauve"), ("Gemma", nil, "Green")]`


## Question 20

Given an optional array of optional tuples of optional UInt8s,

- Write code to safely unwrap and print the tuples in the array with all 3 RGB values.

- Write code that counts all the nil values.

`let possibleColors: [(r: UInt8?, g: UInt8?, b: UInt8?)?]? = [(128, 21, 7), (0, 0, 0), nil, (nil, 25, 82), (255, 255, 255), nil, (200, 100, nil), (120, nil, 23), (0, 255, 106), (nil, nil, nil), nil, (100, 100, 200)]`


## Question 21

Consider the following nested optional. It corresponds to a number inside a box inside a box inside a box.

- Fully force unwrap and print number.

- Optionally bind and print number.

`let number: Int??? = 10`


## Question 22

Given an Array of Optional Strings, write code that concatenates all non-nil values together except for strings with 3 or more vowels.

`let monkeyingAround = ["orangutan", "apes",nil, "monkeys", "gorillas", "lemurs", nil]`

output: `"apesmonkeyslemurs"`


## Question 23

Given the value below, print out all of the non-nil Ints it contains by accessing each of them.

`var strangeStructure: ([Int]?, [[Int?]], [[Int]?], Int)? = ([1], [[2,3,4],[],[5,nil],[nil]], [nil, [6,7,8],nil,[],[9]], 10)`
