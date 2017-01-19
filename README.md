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
let array = [2,3,4,5,6]
let k = 6

var size =  array.count
var result = Array(repeating: 0, count: size)

var position = 0
for (index, element) in array.enumerated() {
	position = index + k
	while(position >= size) {
		position = position - size
	}
	result[position] = element
}

print(result)
~~~~
