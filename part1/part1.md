## part1a
------
_Q1_: The code will print "values added: " plus the addition result of num1 and num2, because variable "result", "num1", "num2" are defined and assigned with a value within the scope, therefore "result" will be the addition of "num1" and "num2", then "result" will be printed after "values added: " by console.log function. 

_Q2_: The code will print "final result: " plus the addition result of num1 and num2, since the result is declared with var keyword, which makes the variable accessible anywhere in the function scope. 

_Q3_: The code will print "values added: " plus the addition result of num1 and num2, because variable "result" is defined in the if scope, and "num1", "num2" are defined and assigned with a value within the scope, therefore "result" will be the assigned with the addition of "num1" and "num2", then "result" will be printed after "values added: " by console.log function. 

_Q4_: The code will return an error of "error: result is not defined", because result is defined with let keyword, which means result is only accessible within the if scope. Any expression outside that scope will not be able to access result.

_Q5_: The code will return an error of "error: can't reassign the constant", because result is declared with const keyword and assigned the value 0. Variable declared with const keyword cannot not be reassigned, while line 7 tries to reassign the const result. 

_Q6_: Since this expression is reachable only after executing the if scope, and the if scope already throws an error, we expect to see the error from line 7 before reaching this expression. However, this line 13 will also throw another error: "error: result is not defined", because result is only defined in the if scope, while lien 13 is outside of the if scope, therefore the variable is inaccessible. 

## part1b
-------
_Q1_: The code will print "3" because variable i is defined with var keyword, which means i is accessible anywhere within the function scope. Then, i is assigned to value 3 in the for block before line 12, so the line 12 will print out "3".

_Q2_: The code will print "150". From the code we know discountedPrice is defined with var keyword, therefore it is accessible at line 13 within the function scope. Also, var allows duplicate declaration. Then, the most recent value of discountedPrice is prices[2] * (1-0.5), which is 300*0.5 = 150. So, line 13 prints 150.

_Q3_: The code will also print "150" because of the same reason as Q2. The only difference is that the finalPrice removes the decimal in discountedPrice. 

_Q4_: The function will return [50, 100, 150] because discounted is an array that is being updated with finalPrice in the for loop. discounted is defined in the function scope, so it is accessible at return statement. 

_Q5_: Since i is defined with let keyword in for scope, i is no longer accessible outside of for scope. Therefore, console.log will throw an error of "error: i is not defined"

_Q6_: Since discountedPrice is defined with let keyword in for scope, discountedPrice is no longer accessible outside of for scope. Therefore, console.log will also throw an erorr of "error: discountedPrice is not defined".

_Q7_: Line 14 will print "150" because finalPrice is defined in the same function scope as line 14, therefore line 14 can access finalPrice. 

_Q8_: The function will return the same array [50, 100, 150] because discounted is also defined in the same function scope as the return statement. Therefore, the function returns the value of discounted, which is the array. 

_Q9_: Same reason as Q5. It will throw an error: "error: i is not defined"

_Q10_: Line 12 will print "3" because length is assigned with value 3 (the length of argument prices) and defined within the same scope as the line 12, so that line 12 can access the variable. 

_Q11_: The function will still return an array of [50, 100, 150]. Even though discounted is defined with const keyword, the array discounted referring to can still be modified. Since discounted is defined in the parent scope of the for scope, the statement within the for loop pushes the result of discountedPrice to discounted. And then, because the return statement is in the same scope with discounted, the function can access the array discounted is referring to and return it. 

_Q12_: 
    
    A: student.name
    B: student["Grad Year"]
    C: student.greeting()
    D: student["Favorite Teacher"].name
    E: student.courseLoad[0]

_Q13_: 

    A: "32" -> 2 is converted to string and append to '3'
    B: 1 -> 3 is converted to number for doing math operation
    C: 3 -> null is equivalent to number 0
    D: "3null" -> first obj is string not number, so that "+" operand becomes concating two string. 
    E: 4 -> true is equivalent to number 1
    F: 0 -> false and null are both equivalent to number 0
    G: "3undefined" -> undefined is converted to string in order to match the type of first obj, then two string concated by + operand
    H: NaN -> undefined is converted to NaN, and '3' is converted to number 3, since '-' operand is a math opeartion. Any math opeartion with NaN results in NaN

_Q14_: 

    A: true -> One side is number, so '2' is converted to number 2, and 2 > 1 == true
    B: false -> Both side is string, so compare as string: first letter of left side is '2', which is larger than the first letter of right side, '1'. Lexiconly, '2' > '1', so false. 
    C: true -> One side is number, so '2' is converted to number 2, and 2 == 2
    D: false -> Number is different from string
    E: false -> One side is number, convert true to 1. 1 != 2, so false
    F: true -> Both side is boolean, and Boolean(2) == true, so true === true is true

_Q15_: == compares with type conversion, but === does not compare with type conversion. 

_Q16_: See part1b-question16.js

_Q17_: 

    // Passed in array=[1,2,3], callback=doSomething
    function modifyArray(array, callback) { 
        const newArr = [];  // newArr refers to an empty array
        for (let i = 0; i < array.length; i++) {  // Loop until i < 3
            // calling callback() is equivalent to doSomething()
            // add result from doSomething(array[i]) to newArr
            newArr.push(callback(array[i])); 
        }
        return newArr;
    }

    function doSomething(num) {
        return num * 2;  // return the multiple of 2 of num
    }

    modifyArray([1,2,3], doSomething); // return [1,4,6]

_Q18_: See part1b-question18.js

_Q19_: Output should be: 

    1
    3
    4
    2

because only 2 is delayed 1s to print, others are having effectively 0s delay.