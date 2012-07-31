# columnizer

A simple tool for printing text in nice columns in the terminal.


## Installing

```shell
npm install columnizer
```

## How do I use it?
```js
var columnizer = require('columnizer');


var stooges = [
  {name: "Larry", height: "short", fat: false},
  {name: "Curly", height: "medium or tall", fat: false},
  {name: "Moe", height: "tall", fat: true}
];

// create an object to start with
var example = columnizer.create();

// call it's row method and pass in agruments
// each subsequent argument is another column

// first we'll add some column headers
example.row("Name", "Height", "Girth");

// then add some data (and do some tweaking of that);
stooges.forEach(function (stooge) {
  example.row(stooge.name, stooge.height, (stooge.fat) ? "corpulent" : "skinny");
});

// then when we're ready, just print it out:
example.print();

// will print this:
/*
Name     Height            Girth        
Larry    short             skinny       
Curly    medium or tall    skinny       
Moe      tall              corpulent    
*/

```

## Licence

MIT