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
