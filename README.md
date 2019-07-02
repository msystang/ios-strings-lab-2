# Strings Lab 2

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.

## Question 1

You are given a string stored in variable `problem`. Write code so that you print each word of the string on a new line.

```swift
var problem = "split this string into words and print them on separate lines"
```

Example

Input:
`var problem ="split this string into words and print them on separate lines"`

Output:
```swift
split
this
string
into
words
and
print
them
on
separate
lines
```

Answer:
```swift
var problem = "split this string into words and print them on separate lines"
var problemArray = problem.components(separatedBy: " ")

for word in problemArray {
print(word)
}
```


## Question 2

Given a string `testString` create a new variable called `condensedString` that has any consecutive spaces in `testString` replaced with a single space.

```swift
let testString = "  How   about      thesespaces  ?  "
//condensedString = " How about these spaces ? "
```

Answer:
```swift
let testString = "  How   about      these spaces  ?  "
//condensedString = " How about these spaces ? "
//
let testStringArray = testString.components(separatedBy:" ")
//print(testStringArray)

var emptyArray =  [String]()

for characters in testStringArray {
if characters == "" {
continue
}
emptyArray.append(characters)
}
//print(emptyArray, terminator: "")

for i in emptyArray {
print(i + " ", terminator: "")
}
```

## Question 3

Given a string with multiple words. Reverse the string word by word.

Example:

Sample Input: `"Swift is the best language"`

Sample Output: `"language best the is Swift"`

Answer:
```swift
var string = "Swift is the best language"
let stringArray = string.components(separatedBy: " ")

var emptyString = ""
for word in stringArray {
emptyString =  "\(word) " + emptyString
}
print(emptyString, terminator: "")
```

## Question 4

Given a string with multiple words. Write code that prints how many of them are palindromes.

Example:

Sample Input: `"danaerys dad cat civic bottle"`

Sample Output: `2`

Answer:
```swift
var string = "danaerys dad cat civic bottle"
let stringArray = string.components(separatedBy: " ")
var count = 0

for words in stringArray {
if String(words) == String(words.reversed()) {
count += 1
}
}
print(count)
```

## Question 5

You are given a string representing an **attendance record** for a student. The record only contains the following three characters:

`'A' : Absent.`

`'L' : Late.`

`'P' : Present.`

If a student has more than one 'A' or more than 2 continuous 'L's that student should not be rewarded. Print true if student is to be rewarded and False if they shouldn't.

Example:

Sample Input: `"PPALLP"`

Sample Output: `true`

```swift
var attendance = "PPALLP"
let absent = "A"
let late = "LLL"
var absentCount = 0

for letter in attendance {
if letter == "A" {
absentCount += 1
continue
}
}

print(absentCount)

if attendance.contains(late) == true || absentCount > 1 {
print("false")
} else {
print("true")
}
```

## Question 6

Given a tuple with two strings. The first string is a **ransom note**, the second string being the characters from a magazine. Determine whether or not you can construct the ransom note using the characters from the magazine.

Each letter from the magazine can only be used once. You can assume all letters are lowercased.

Examples:

Sample Input1: `("a", "b")`

Sample Output1: `False`

Sample Input2: `("aa", "aab")`

Sample Output2: `True`


Answer:
```swift
var tuple = (ransom: "aaa", mag: "baaab")

var ransomArray = [Character] ()
var magArray = [Character] ()

for ransomLetter in tuple.0 {
ransomArray.append(ransomLetter)
}
//print(ransomArray)

for magLetter in tuple.1 {
magArray.append(magLetter)
}
//print(magArray)


for a in ransomArray {
var counterRansom = 0
var counterMag = 0
for b in magArray {
if ransomArray.count == counterRansom {
break
}
if a == b {
ransomArray.remove(at:counterRansom)
magArray.remove(at:counterMag)
continue
}
counterMag += 1
}
counterRansom += 1

}
print(ransomArray)

if ransomArray.count == 0 {
print("true")
} else {
print("false")
}
```
