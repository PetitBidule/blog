# Class Exo Résolution:

```js
class Rectangle{
	constructor(widht, height){
		this.width = width 
		this.height = height 
	}	
	get perimeter(){
		return (this.width + this.height)*2
	}
	get isValid(){
		return this.width > 0 && this.height > 0
	}
	isBiggerThan (shape){
		return this.perimeter > shape.perimeter
	}
}
class Square extends Rectangle{
	constructor(width){
		super(width, width);
	}
}

const r = new Rectangle(10, 30)
console.log(r.perimeter)
console.log(r.isValid)
const r2 = new Rectangle(-30, 100)
const c = new Square(10)
console.log(c.perimeter)
console.log(r.isBiggerThan(c))

// nous obtenons:
// 60
// true
// false
// 40
// true

