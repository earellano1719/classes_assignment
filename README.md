# Class Exercises

1.
  * Create a Human class that takes in a name and age.
  * Add the function `ageOneYear` that ages the human.
  * Add the function `eating`, that logs "mmm, mmm, mmm, I'm love'n it".
  * Create an instance of the Human class.
    * console log your humans age
    * call ageOneYear on your human
    * console log their age again.
    * call eating on your human.

    class Human {
      constructor (name, age) {
        this.name = name;
        this.age = age;
      }
      ageOneYear() {
        this.age++;
        return this.age;
      }
      eating(str) {
        return `Mmmm, mmmm, mmmm, I'm loving it, I'm eating ${str}.`;
      }
    }

    let person = new Human("Dwight" , 38)
    console.log(person.age);
    person.ageOneYear();
    console.log(person.age);
    console.log(person.eating("a big mak-me fat"));

2.
Write a class Vector that represents a vector in two-dimensional space.
It takes two number arguments: `x` and `y` parameters, which it should be saved to properties of the same name.

Give the Vector two methods, `plus` and `minus`, that take another vector as an argument and
returns a new vector that has the sum or difference of the two vectors’ (the one in `this` and the parameter) x and y values.

Add a method `getLength` to the prototype that computes the length of the vector ;
that is, the distance of the point (x, y) from the origin (0, 0).(a^2 + b^2 = c^2)

```js
var v1 = new Vector(1, 2)
var v2 = new Vector(2, 3)
console.log(v1.plus(v2));
// => Vector {x: 3, y: 5}
console.log(v1.minus(v2));
// => Vector {x: -1, y: -1}

var v3 = new Vector(3, 4)
console.log(v3.getLength());
// => 5
```



class Vector {
  constructor (x, y){
    this.x = x;
    this.y = y;
  }
  plus (el) {
    return new Vector (this.x + el.x , this.y + el.y)
  }
  minus (el) {
    return new Vector (this.x - el.x , this.y - el.y)
  }
  getLength () {
    return Math.sqrt(Math.pow(this.x, 2) + Math.pow(this.y, 2))
  }
}

let v1 = new Vector (1, 2)
let v2 = new Vector (2, 3)
let v3 = new Vector (3, 4)

console.log(v1.plus(v2));
console.log(v1.minus(v2));
console.log(v3.getLength());
