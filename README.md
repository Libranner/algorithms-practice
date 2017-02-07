# algorithms-practice

## Binary Gap
~~~~ 
let num = 529
let bin = String(num, radix: 2)
var count = 0
var gapSize = 0
for i in bin.characters {
	if(i == "0"){
		count += 1	
	}
	else {
		if(count >= 1 && count > gapSize){
			gapSize = count
		}
		count = 0
	}
}

print(gapSize)
~~~~ 

# Cyclic Rotation

~~~~
var array = [2,3,4,5,6]
let k = 6

for (index, element) in array.enumerated() {
	array[(index + k) % array.count] = element
}

print(array)
~~~~

# FrogJmp
~~~~~

import Foundation

var x = 10
let y = 85
let d = 30

let jumps = Double(y - x)/Double(d) 
print(ceil(jumps))

~~~~~

# Equi
~~~~~
var A = [-1,3,-4,5,1,-6,2,1]
let n = A.count

if (n==0) {
	print(-1)
}

var sum: Double = 0;
for i in 0..<n{
	sum += Double(A[i])
}

var sum_left: Double = 0
for i in 0..<n{
	let sum_right: Double = sum - sum_left - Double(A[i])
	if (sum_left == sum_right) {
		print(i)
	}
	sum_left += Double(A[i])
}
print(-1)

~~~~~

# PermMissingElem
~~~~~
let A = [1,2,4]

let size =  A.count
var sum: Double = 0
var sum_complementary: Double = 0
for index in 0..<size {
	sum += Double(A[index])
	sum_complementary += Double(index + 1)
}
sum_complementary += Double(size + 1)

print(Int(sum - sum_complementary))
~~~~~

#MissingInteger
~~~~~
public func solution(_ A : inout [Int]) -> Int {
	var result = 0
	let set = Set(A)
	repeat {
		result += 1
	}while (set.contains(result))
	
	return result
}

var A = [-1,-3,-6,-4,-1,-2]
print(solution(&A))
~~~~~

#Matching brackets
~~~~~
public func solution( _ S:String) -> Int{
	let S = "(())))("
	var totalClosedBrackets = 0

	for c in S.characters {
		if(c == ")") {
			totalClosedBrackets += 1
		}
	}

	var position = 0, closedBrackets = 0, openBrackets = 0
	for c in S.characters {
		position += 1
		if(c == "("){
			openBrackets += 1
		}
		else{
			closedBrackets += 1
		}

		if(openBrackets == totalClosedBrackets - closedBrackets){
			return position
		}
	}
	return position
}

print(solution("(())))("))
~~~~~

