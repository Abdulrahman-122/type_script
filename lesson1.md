JS is a dynamic  language -> it needs to run before it check the error in the code
Type_script -> is a type static language -> check the code contain any errrors before running.

so Type-Script 
  - tells us the bugs into our code before running the code itself(awasome tool)
  - now we will use tsc compiler to compile our code first to check it first then convert  it into .js file that you can run it after a while.
  -  to use tsc;
    -  npm install -g typescript

    ex;
    // This is an industrial-grade general-purpose greeter function:
function greet(person, date) {
  console.log(`Hello ${person}, today is ${date}!`);
}
 
greet("Brendan");
this code will run an error through the type chacker of typescript.

now let's add some annotations infront of the paramaters that the function takes;

  function greet(person: string, date: Date) {
  console.log(`Hello ${person}, today is ${date.toDateString()}!`);
}
greet("Maddison", new Date());
to run this ;
tsc filename.ts
then ;
npm filename.js
  - keep in mind -> you don't need to add annotations for the variables in order to infer it for typescript
  - if you didn't write thing -> typescript will discover the type instead through it's tools.

now let's change this code that  we written above into  this ;
function greet(person, date) {
    console.log("Hello ".concat(person, ", today is ").concat(date.toDateString(), "!"));
}
greet("Maddison", new Date());

when your run; tsc filename  
then ; node filename it will run also why;
alaught we didn't use any type for any variable
and we didn't use `` backticks (default way to  print a string   in ES6 
instead we used concat function to concate with "" douple qoutes
now ;  this is ES5  typescript handle it instead of Es6 
it uses older version to compile the code for you.

----
to sum up this language;
  - it has type-checker (this is  a strictness ) to check the bugs into the code.
  - try to define the type of variable that you write in order to test it using type-checker try to not leave the variable without any declaration as this make typescript uses ;  any as  type for the variables.
  - try to handle null,undefined variables  in order to  prevent the mistake.




  
