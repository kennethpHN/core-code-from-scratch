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
