## Thursday 08/09/22

[**Define generics in TypeScript guided exercise, using Typescript**](https://docs.microsoft.com/en-us/learn/modules/typescript-generics/)
```typescript
// TODO: Add and apply a type variable.
class DataStore<T> {

    private _data: Array<T> = new Array(10);

    AddOrUpdate(index: number, item: T) {
        if(index >=0 && index <10) {
            this._data[index] = item;
        }
    }
    GetData(index: number) {
        if(index >=0 && index < 10) {
            return this._data[index];
        } else {
            return
        }
    }

}

let cities = new DataStore<string>();
cities.AddOrUpdate(0, "Mumbai");
cities.AddOrUpdate(1, "Chicago");
cities.AddOrUpdate(2, "London");
cities.AddOrUpdate(11, "New York");
console.log(cities.GetData(11));        

// TODO Test items as numbers.
let empIDs = new DataStore<number>();
empIDs.AddOrUpdate(0, 50);
empIDs.AddOrUpdate(1, 65);
empIDs.AddOrUpdate(2, 89);                  
console.log(empIDs.GetData(0));         

// TODO Test items as objects.
type Pets = {
    name: string;
    breed: string;
    age: number
}
let pets = new DataStore<Pets>();
pets.AddOrUpdate(0, { name: 'Rex', breed: 'Golden Retriever', age: 5});
pets.AddOrUpdate(1, { name: 'Sparky', breed: 'Jack Russell Terrier', age: 3});
console.log(pets.GetData(1));         
```

**Generics exercise, using Typescript**

We have just learn about generics, an we where creating our own implementation for the Linkedlist structure, but it is incomplete, you task is to finish the missing methods.

- addFirst: Adds a new node at the start of the structure
- removeLast: Removes the last node of the structure
```typescript
public addFirst(value: T) {
    if (this.head === null) {
      this.add(value);} else {
      let node = new Node(value);
      node.next = this.head;
      this.head = node;
      this.length++;}
}

public removeLast(): void {
    if (this.head !== null) {
      let node = this.head;
      let previous: Node<T> = node;
      while (node.next !== null) {
        previous = node;
        node = node.next;}
      previous.next = null;
      this.length--;}
}
 ```
