## Thursday 25/08/22
[**Declare and instantiate classes in TypeScript guided exercise, using Typescript**](https://docs.microsoft.com/en-us/learn/modules/typescript-declare-instantiate-classes/)

##### Exercise - Instantiate a class
```typescript
class Car {
    // Properties
    _make: string;
    _color: string;
    _doors: number;
    // Constructor
    constructor(make: string, color: string, doors = 4) {
        this._make = make;
        this._color = color;
        if ((doors % 2) === 0) {
            this._doors = doors;
        } else {
            throw new Error('Doors must be an even number');
        }
    }

    // Accessors
    get make() {
    return this._make;
    }
    set make(make) {
    this._make = make;
    }
    get color() {
    return 'The color of the car is ' + this._color;
    }
    set color(color) {
        this._color = color;
    }
    get doors() {
    return this._doors;
    }
    set doors(doors) {
        if ((doors % 2) === 0) {
            this._doors = doors;
        } else {
            throw new Error('Doors must be an even number');
        }
    }
    // Methods
    accelerate(speed: number): string {
        return `${this.worker()} is accelerating to ${speed} MPH.`
    }
    brake(): string {
        return `${this.worker()} is braking with the standard braking system.`
    }
    turn(direction: 'left' | 'right'): string {
        return `${this.worker()} is turning ${direction}`;
    }
    // This function performs work for the other method functions
    worker(): string {
        return this._make;
    }
}
let myCar1 = new Car('Cool Car Company', 'blue', 2);  // Instantiates the Car object with all parameters
console.log(myCar1.color);
console.log(myCar1._color);
let myCar2 = new Car('Galaxy Motors', 'red', 6);
let myCar3 = new Car('Galaxy Motors', 'gray');
console.log(myCar3.doors);  // returns 4, the default value
console.log(myCar1.accelerate(35));
console.log(myCar1.brake());
console.log(myCar1.turn('right'));

```

#####   Exercise - Apply access modifiers to a class
```typescript
class Car {
    // Properties
    private _make: string;
    private _color: string;
    private _doors: number;
    // Constructor
    constructor(make: string, color: string, doors = 4) {
        this._make = make;
        this._color = color;
        if ((doors % 2) === 0) {
            this._doors = doors;
        } else {
            throw new Error('Doors must be an even number');
        }
    }

    // Accessors
    get make() {
    return this._make;
    }
    set make(make) {
    this._make = make;
    }
    get color() {
    return 'The color of the car is ' + this._color;
    }
    set color(color) {
        this._color = color;
    }
    get doors() {
    return this._doors;
    }
    set doors(doors) {
        if ((doors % 2) === 0) {
            this._doors = doors;
        } else {
            throw new Error('Doors must be an even number');
        }
    }
    // Methods
    accelerate(speed: number): string {
        return `${this.worker()} is accelerating to ${speed} MPH.`
    }
    brake(): string {
        return `${this.worker()} is braking with the standard braking system.`
    }
    turn(direction: 'left' | 'right'): string {
        return `${this.worker()} is turning ${direction}`;
    }
    // This function performs work for the other method functions
    private worker(): string {
        return this._make;
    }
}
let myCar1 = new Car('Cool Car Company', 'blue', 2);  // Instantiates the Car object with all parameters
console.log(myCar1.color);
```

##### Exercise - Extend a Class
```typescript
class Car {
    // Properties
    private static numberOfCars: number = 0;  // New static property
    private _make: string;
    private _color: string;
    private _doors: number;
    // Constructor
    constructor(make: string, color: string, doors = 4) {
        this._make = make;
        this._color = color;
        if ((doors % 2) === 0) {
            this._doors = doors;
        } else {
            throw new Error('Doors must be an even number');
        }
        Car.numberOfCars++; // Increments the value of the static property
    }

    // Accessors
    get make() {
    return this._make;
    }
    set make(make) {
    this._make = make;
    }
    get color() {
    return 'The color of the car is ' + this._color;
    }
    set color(color) {
        this._color = color;
    }
    get doors() {
    return this._doors;
    }
    set doors(doors) {
        if ((doors % 2) === 0) {
            this._doors = doors;
        } else {
            throw new Error('Doors must be an even number');
        }
    }
    // Methods
    accelerate(speed: number): string {
        return `${this.worker()} is accelerating to ${speed} MPH.`
    }
    brake(): string {
        return `${this.worker()} is braking with the standard braking system.`
    }
    turn(direction: 'left' | 'right'): string {
        return `${this.worker()} is turning ${direction}`;
    }
    // This function performs work for the other method functions
    protected worker(): string {
        return this._make;
    }
    public static getNumberOfCars(): number {
    return Car.numberOfCars;
    }
}
let myCar1 = new Car('Cool Car Company', 'blue', 2);  // Instantiates the Car object with all parameters
console.log(myCar1.color);
console.log(Car.getNumberOfCars());

class ElectricCar extends Car {
    // Properties unique to ElectricCar
    private _range: number;
    // Constructor
    constructor(make: string, color: string, range: number, doors = 2) {
        super(make, color, doors);
        this._range = range;
    }
    // Accessors
    get range() {
    return this._range;
    }
    set range(range) {
        this._range = range;
    }
    // Methods
    charge() {
        console.log(this.worker() + " is charging.")
    }
    // Overrides the brake method of the Car class
    brake(): string {
        return `${this.worker()}  is braking with the regenerative braking system.`
    }
}

let spark = new ElectricCar('Spark Motors','silver', 124, 2);
let eCar = new ElectricCar('Electric Car Co.', 'black', 263);
console.log(eCar.doors);         // returns the default, 2
spark.charge();                  // returns "Spark Motors is charging"
console.log(spark.brake());  // returns "Spark Motors is braking with the regenerative braking system"
```

##### Exercise - Declare an interface to ensure class shape
```typescript
class Car implements Vehicle{
    // Properties
    private static numberOfCars: number = 0;  // New static property
    private _make: string;
    private _color: string;
    private _doors: number;
    // Constructor
    constructor(make: string, color: string, doors = 4) {
        this._make = make;
        this._color = color;
        if ((doors % 2) === 0) {
            this._doors = doors;
        } else {
            throw new Error('Doors must be an even number');
        }
        Car.numberOfCars++; // Increments the value of the static property
    }

    // Accessors
    get make() {
    return this._make;
    }
    set make(make) {
    this._make = make;
    }
    get color() {
    return 'The color of the car is ' + this._color;
    }
    set color(color) {
        this._color = color;
    }
    get doors() {
    return this._doors;
    }
    set doors(doors) {
        if ((doors % 2) === 0) {
            this._doors = doors;
        } else {
            throw new Error('Doors must be an even number');
        }
    }
    // Methods
    accelerate(speed: number): string {
        return `${this.worker()} is accelerating to ${speed} MPH.`
    }
    brake(): string {
        return `${this.worker()} is braking with the standard braking system.`
    }
    turn(direction: 'left' | 'right'): string {
        return `${this.worker()} is turning ${direction}`;
    }
    // This function performs work for the other method functions
    protected worker(): string {
        return this._make;
    }
    public static getNumberOfCars(): number {
    return Car.numberOfCars;
    }
}
let myCar1 = new Car('Cool Car Company', 'blue', 2);  // Instantiates the Car object with all parameters
console.log(myCar1.color);
console.log(Car.getNumberOfCars());

class ElectricCar extends Car {
    // Properties unique to ElectricCar
    private _range: number;
    // Constructor
    constructor(make: string, color: string, range: number, doors = 2) {
        super(make, color, doors);
        this._range = range;
    }
    // Accessors
    get range() {
    return this._range;
    }
    set range(range) {
        this._range = range;
    }
    // Methods
    charge() {
        console.log(this.worker() + " is charging.")
    }
    // Overrides the brake method of the Car class
    brake(): string {
        return `${this.worker()}  is braking with the regenerative braking system.`
    }
}

let spark = new ElectricCar('Spark Motors','silver', 124, 2);
let eCar = new ElectricCar('Electric Car Co.', 'black', 263);
console.log(eCar.doors);         // returns the default, 2
spark.charge();                  // returns "Spark Motors is charging"
console.log(spark.brake());  // returns "Spark Motors is braking with the regenerative braking system"

interface Vehicle {
    make: string;
    color: string;
    doors: number;
    accelerate(speed: number): string;
    brake(): string;
    turn(direction: 'left' | 'right'): string;
}
```
##### Lab - Convert three TypeScript functions to a class definition
```typescript
/*  Module 5: Declare and instantiate classes in TypeScript
    Lab Start  */

/*  EXERCISE 1 */

class BuildArray {
    // TODO Define the properties
    private _items: number;
    private _sortOrder: 'ascending' | 'descending';

    // TODO Define the constructor
    constructor (items: number, sortOrder: 'ascending' | 'descending') {
        this._items = items;
        this._sortOrder = sortOrder;
    }

    // TODO Define the accessors
    get items() {
        return this._items;
    }
    set items(items) {
        this._items = items;
    }
    get sortOrder() {
        return this._sortOrder;
    }
    set sortOrder(sortOrder) {
        this._sortOrder = sortOrder;
    }

    // TODO Define the methods
    /*  sortDescending is a comparison function that tells the sort method how to sort numbers
    in descending order. */
    private sortDescending = (a: number, b: number) => {
        if (a > b) {
            return -1;
        } else if (b > a) {
            return 1;
        } else {
            return 0; }
    }
    /*  sortAscending is a comparison function that tells the sort method how to sort numbers 
    in ascending order. */
    private sortAscending = (a: number, b: number) => {
        if (a > b) {
            return 1;
        } else if (b > a) {
            return -1;
        } else {
            return 0;
        }
    }
    /*  buildArray builds an array of unique random numbers containing the number of items 
    based on the number passed to it. The sortOrder parameter determines whether to sort 
    the array in ascending or descending order. */
    public buildArray(items: number, sortOrder: 'ascending' | 'descending'): number[] {
        let randomNumbers: number[] = [];
        let nextNumber: number;
        for (let counter = 0; counter < items; counter++) {
            nextNumber = Math.ceil(Math.random() * (100 - 1));
            if (randomNumbers.indexOf(nextNumber) === -1) {
                randomNumbers.push(nextNumber);
            } else {
                counter--;
            }
        }
        if (sortOrder === 'ascending') {
            return randomNumbers.sort(this.sortAscending);
        } else {
            return randomNumbers.sort(this.sortDescending);
        }
    }
}







/*  TODO: Instantiate the BuildArray objects. */

let testArray1 = new BuildArray(12, 'ascending');
let testArray2 = new BuildArray(8, 'descending');
console.log(testArray1);
console.log(testArray2);

```

[**Tile Exercise**](https://github.com/corecodeio/devguide-fundamentals-2022-03/tree/main/src/technologies/2022/week06/exercises/e09/desc)

In the board game Scrabble2, each tile contains a letter, which is used to spell words, and a score, which is used to determine the value of words.

1. Write a definition for a class named `Tile` that represents Scrabble tiles. The instance variables should be a `string` named `letter` and an `number` named `value`.
2. Write a constructor that takes parameters named `letter` and `value` and initializes the instance variables.
3. Write a method named `printTile` that prints the instance variables in a `reader-friendly` format (not the { ... } format way).
4. Don't worry you don't have to check if the letter is no more than one String length.
5. You can use this `Main` class to test your code.

```typescript
import Tile from './Tile';
export default class Main {
  start() {
    const A = new Tile('A', 10);
    A.printTile(); // Example of a reader-friendly format above
    /*
      ==================
        Letter: A
        Value: 10
      ==================
    */
    const W = new Tile('W', '50'); // This should show and error
  }
}
```
6. On your `index.ts` you can now use this to test your solution
```typescript
import Main from './Main';
const main = new Main();
main.start();
```

```typescript
export default class Tile {
    // Properties
    private _letter: string;
    private _value: number;

    // Constructor
    constructor(letter: string, value: number){
        this._letter = letter;
        this._value = value;
    }
    // Accesors
    get letter(){
        return this._letter;
    }
    set letter(letter){
        this._letter = letter;
    }
    get value(){
        return this._value;
    }
    set value(value){
        this._value = value;
    }
    // Methods
    printTile(){
        return console.log(
        "=================="+
        "\nLetter: "+this.letter+
        "\nValue: "+this.value+
        "\n==================");
    }
}
```

[**Time Exercise**](https://github.com/corecodeio/devguide-fundamentals-2022-03/tree/main/src/technologies/2022/week06/exercises/e10/desc)

You have been hired by a brand of digital watches to be able to create the functionality of keeping track of time, for this you have been asked to do the following:

1. Write a definition for the class name `Time` this class would be use to build a digital clock. This class should have 3 attributes of type number. `hour`, `minute` and `second`.
2. Write a constructor that takes parameters named `hour`, `minute` and `second` and initializes the instance variables.
3. Write a method called `getInSeconds` that returns a number representing the actual time in the instance represented in seconds.
4. Write a method named `printTime` that prints the instance variables in a `reader-friendly` format (not the { ... } format way).

```typescript
import Time from './Time';
export default class Main {
  start() {
    const t = new Time(10, 45, 1);
    t.printTime(); // Example of a reader-friendly format above
    /*
      ==================
        Hours: 10
        Minutes: 45
        Seconds: 1
      ==================
    */
    console.log(t.getInSeconds()); // 38701
  }
}
```
5. On your `index.ts` you can now use this to test your solution
```typescript
import Main from './Main';
const main = new Main();
main.start();
```

```typescript
export default class Time {
    private _hour: number;
    private _minute: number;
    private _second: number;

    constructor(hour: number, minute: number, second: number){
        this._hour = hour;
        this._minute = minute;
        this._second = second;
    }

    get hour(){
        return this._hour;
    }
    set hour(hour){
        this._hour = hour;
    }
    get minute(){
        return this._minute;
    }
    set minute(minute){
        this._minute = minute;
    }
    get second(){
        return this._second;
    }
    set second(second){
        this._second = second;
    }

    getInSeconds(){
        return (this.hour*3600 + this.minute*60 + this.second);
    }
    printTime(){
        return console.log(
        `
        ==================
            Hours: ${this.hour}
            Minutes: ${this.minute}
            Seconds: ${this.second}
        ==================
        `
        )
    }
}
```

[**Rational Exercise**](https://github.com/corecodeio/devguide-fundamentals-2022-03/tree/main/src/technologies/2022/week06/exercises/e11/desc)

A rational number is a number that can be represented as the ratio of two integers. For example, 2/3 is a rational number, and you can think of 7 as a rational number with an implicit 1 in the denominator (7/1). For this assignment, you are going to write a class definition for rational numbers.

1. Create a new class named Rational. A Rational object should have two number instance variables to store the `numerator` and `denominator`.
2. Write a constructor for your class that takes two arguments and that uses them to initalize the instance variables.
3. Write a method called printRational that prints the object in some reasonable format.
4. Write a method called invert that inverts the number by swapping the numerator and denominator. This method should modify the instance variables.
5. Write a method called toFloat that converts the rational number to a floating-point number and returns the result. This method is a [pure function](https://betterprogramming.pub/what-is-a-pure-function-3b4af9352f6f) it does not modify the object.
6. Write method named reduce that reduces a rational number to its lowest terms by finding the greatest common divisor (GCD) of the numerator and denominator and dividing through. This method should modify the instance variables. To calculate the GCD you can search for `Euclidian Algorithm: GCD`.

```typescript
import Rational from './Rational';
export default class Main {
  start() {
    const r1 = new Rational(36, 120);
    r1.printRational(); // 36 / 120
    console.log(r1.toFloat()); // 0.3
    r1.reduce();
    r1.printRational(); // 3 / 10
    r1.invert();
    r1.printRational(); // 10 / 3
    r1.reduce();
    r1.printRational(); // 10 / 3
  }
}
```
7. On your `index.ts` you can now use this to test your solution
```typescript
import Main from './Main';
const main = new Main();
main.start();
```

```typescript
export default class Rational {
    private _numerator: number;
    private _denominator: number;

    constructor(numerator: number, denominator: number){
        this._numerator = numerator;
        this._denominator = denominator;
    }

    get numerator(){
        return this._numerator;
    }
    set numerator(numerator){
        this._numerator = numerator;
    }
    get denominator(){
        return this._denominator;
    }
    set denominator(denominator){
        this._denominator = denominator;
    }

    printRational(){
        console.log(`${this._numerator} / ${this._denominator}`);
    }
    invert(){
        let temp: number = this.numerator;
        this.numerator = this.denominator;
        this.denominator = temp;
    }
    toFloat(){
        return (this.numerator / this.denominator);
    }
    reduce(){
        let a: number = this.numerator;
        let b: number = this.denominator;
        while (a && b && a !== b) {
            if(a > b){
               [a, b] = [a - b, b];
            }else{
               [a, b] = [a, b - a];
            };
         };
         this.numerator = this.numerator/a;
         this.denominator = this.denominator/b;
    }
}
```
