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
