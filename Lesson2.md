Types in Type-script;
  -Primitives; string,number,boolean 
    -basic types.
  - also there's ; any -> is used when you aren't sure that this variable it's specific type is correct.
  - ex;let obj: any = { x: 0 };
    - here obj it's data type is any .
  - Add a type for the variables;
    - ex;let myName: string = "Alice";
  - note; you don't need to define a type for the variables at anytime;
  - ex;let myName = "Alice";  => this variable is understood as string type.

  - To define a Function in Type-script;
    - // Parameter type annotation
      function greet(name: string) {
        console.log("Hello, " + name.toUpperCase() + "!!");
      }
      - define the type of the variables inside the paramater list.
  - you can define the type of the return of the function;
            - function getFavoriteNumber(): number {
          return 26;
        }
  - if the function return a promise you can define the type of the promise that return from it.
    
      - async function getFavoriteNumber(): Promise<number> {
      return 26;
    }
  - with anonymous functions;
    - const names = ["Alice", "Bob", "Eve"];
    // Contextual typing for function - parameter s inferred to have type string
    names.forEach(function (s) {
      console.log(s.toUpperCase());
    });
     
    // Contextual typing also applies to arrow functions
    names.forEach((s) => {
      console.log(s.toUpperCase());
    });
    here; s we didn't define its type as typescript knows it's type from the foreach explicitly.

    - Object types =>
      - // The parameter's type annotation is an object type
        function printCoord(pt: { x: number; y: number }) {
          console.log("The coordinate's x value is " + pt.x);
          console.log("The coordinate's y value is " + pt.y);
        }
        printCoord({ x: 3, y: 7 });
        - here we define the type of x,y as a numbers
        - if you didn't define these types -> the default will be any .

----

function printName(obj: { first: string; last?: string }) {
  // Error - might crash if 'obj.last' wasn't provided!
  console.log(obj.last.toUpperCase());
'obj.last' is possibly 'undefined'.
  if (obj.last !== undefined) {
    // OK
    console.log(obj.last.toUpperCase());
  }
 
  // A safe alternative using modern JavaScript syntax:
  console.log(obj.last?.toUpperCase());
}
  - according to that; optional properties to define it -> put ? infront of it.
---
- Union operator(|);
  - compine two types at the same time.
  - ex;
    - function printId(id: number | string) {
  console.log("Your ID is: " + id);
        }
      // OK
      printId(101);
      // OK
      printId("202");
      // Error as this type is not mentioned at the definition.
      printId({ myID: 22342 });
- ex;
  - function printId(id: number | string) {
      if (typeof id === "string") {
        // In this branch, id is of type 'string'
        console.log(id.toUpperCase());
      } else {
        // Here, id is of type 'number'
        console.log(id);
      }
    }
- here we checked the type of the id is it==string -> then put it in upper case as this function is related to the string
- - else ; print id as number
 
  - ex;
    - function welcomePeople(x: string[] | string) {
        if (Array.isArray(x)) {
          // Here: 'x' is 'string[]'
          console.log("Hello, " + x.join(" and "));
        } else {
          // Here: 'x' is 'string'
          console.log("Welcome lone traveler " + x);
        }
      }
      - here we checked x to be as an array.
  - ex;
    - // Return type is inferred as number[] | string
    function getFirstThree(x: number[] | string) {
      return x.slice(0, 3);}
      here if the x was an array -> take shallow copy of it from index 0 till index 3
      if it was a string -> take a copy from 0 to 3.
      
- Type Aliases;

