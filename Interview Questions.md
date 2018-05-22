https://codesandbox.io/s/qv9xjzry24
http://jsfiddle.net/peterjmag/kysymow0/

santhankk@gmail.com
Tnl@2017


create two components userinput and useroutput

userinput should hold an input element output holds two paragraphs

pass username to output

### specificity:

style attribute: 1000
id: 100
element and psedo element: 1
class, attribute, psedo class: 10

### closure:

clouser is a characherstic of a fucntion in any lexically scoped enviornmenr which allows that function to continue to access variable outside of itself even when the fucntion is passed in different location and executed

```
function outerfunction() {
    console.log(1)
  var time = 0;
  console.log('time is', time);
  
  function innerfunction() {
    console.log(2)
    var i = time++
    console.log('i value', i)
  }
  
  return innerfunction;
}

var out = outerfunction()




out()
out();
out()
out();

for(i=1;i<3;i++) {
out();
  out();
  out();

}
```

### Multiple Inheritance

```
function multi() {
  var n = {}, stuff, 
    j = 0, len = arguments.length;
  for (j = 0; j <len; j++) {
    stuff = arguments[j];
    for (var i in stuff) {
      if (stuff.hasOwnProperty(i)) {
        n[i] = stuff[i];
      }
    }
  }
  return n;
}


var shape = {
  name: 'Shape',
  toString: function () {
    return this.name;
  }
};

var twoDee = {
  name: '2D shape',
  dimensions: 2
};



var triangle = multi(shape, twoDee, {
  name: 'Triangle',
  getArea: function () {
  	return this.side * this.height / 2;
	},
  side: 5,
  height: 10
});

var t = new triangle(5, 10);
console.log(t.dimensions)
```

### SASS Features

Nesting, Variables and Math
Combining CSS Files with @import
Re-using Styles with Mixins
@include mixin-name;
Extending Styles with Inheritance

```
.error {
  border: 1px #f00;
  background-color: #fdd;
}
.serious-error {
  @extend .error;
  border-width: 3px;
}
```

This compiles to:

```
.error, .serious-error {
  border: 1px #f00;
  background-color: #fdd;
}

.serious-error {
  border-width: 3px;
}
```

### Fibonaci Series

var i;
var fib = []; // Initialize array!

fib[0] = 0;
fib[1] = 1;
for(i=2; i<=10; i++)
{
    // Next fibonacci number = previous + one before previous
    // Translated to JavaScript:
    fib[i] = fib[i-2] + fib[i-1];
    //console.log(fib[i]);
}
console.log(fib[i]);
```

### Palindrom

```
var str = 'madam', palindrom='';

for(var i=str.length-1; i>=0; i--) {
  palindrom+=str[i];
}
console.log(palindrom);
```

### Amstrong Number

```
var arm=0, num=371, temp, a;

temp = num;

while(temp>0) {
  a = temp%10;
  temp = parseInt(temp/10);
console.log("a "+a+" temp "+temp);
  arm+=a*a*a;
}

if(arm === num) {
  console.log('Armstrong Number');
}
```

### inline, inline-block, block

https://stackoverflow.com/questions/9189810/css-display-inline-vs-inline-block

### CSS Positioning:

https://css-tricks.com/almanac/properties/p/position/

### Promise

In javascript there is no concept of pausing the ececution.

```
promise = new Promise((resolved, reject) => {
  setTimeout( () => {
    resolved()
  }, 3000)
})

promise.then(() => {
console.log('Finally finished');
}).then(() => {
 console.log('I was also run');
}).catch(() => {
  console.log('Error')
})
```

### No of weeks in two given dates

```
function weeks_between(date1, date2) {
	// The number of milliseconds in one week
	var ONE_WEEK = 1000 * 60 * 60 * 24 * 7;
	// Convert both dates to milliseconds
	var date1_ms = date1.getTime();
	var date2_ms = date2.getTime();
	// Calculate the difference in milliseconds
	var difference_ms = Math.abs(date1_ms - date2_ms);
	// Convert back to weeks and return hole weeks
	return Math.floor(difference_ms / ONE_WEEK);
}
```

```
function CalculateWeek()
        {
            // Current Date
            var date1 = new Date();
            alert(date1);
            

            //Parsing the value from the text control. The actual date is in dd/mm/yyyy format as per your post.
            var arrDateValue = document.getElementById("txtDate").value.split('/'); // Actual Date is in dd/mm/yyyy
            

            // Converting to mm/dd/yyyy date format
            var Date2 = new Date(arrDateValue[1] + '/' + arrDateValue[0] + '/' + arrDateValue[2]); // mm/dd/yyyy
            alert(Date2);
            

            // one week calculation
            var perWeek = 24 * 60 * 60 * 1000 * 7;
            

            // calculating total week. FYI the week starts from Monday to Sunday
            var totalWeeks = Math.round((date1.valueOf()- Date2.valueOf())/ perWeek) + 1;
            

            // alerting the total Weeks
            alert(totalWeeks);
        }
        
        CalculateWeek()
```

### Attribute Selectors

The [attribute] selector is used to select elements with a specified attribute.

```
a[target] {
    background-color: yellow;
}

The [attribute="value"] selector is used to select elements with a specified attribute and value.
a[target="_blank"] { 
    background-color: yellow;
}
```

The [attribute~="value"] selector is used to select elements with an attribute value containing a specified word.

```
<img src="klematis.jpg" title="klematis flower" width="150" height="113">
<img src="img_flwr.gif" title="flower" width="224" height="162">
<img src="img_tree.gif" title="tree" width="200" height="358">

[title~=flower] {
    border: 5px solid yellow;
}
```

The [attribute|="value"] selector is used to select elements with the specified attribute starting with the specified value.

```
<h1 class="top-header">Welcome</h1>
<p class="top-text">Hello world!</p>
<p class="topcontent">Are you learning CSS?</p>

[class|=top] {
    background: yellow;
}
```

The [attribute^="value"] selector is used to select elements whose attribute value begins with a specified value.

```
<h1 class="top-header">Welcome</h1>
<p class="top-text">Hello world!</p>
<p class="topcontent">Are you learning CSS?</p>

[class^="top"] {
    background: yellow;
}
```

The [attribute$="value"] selector is used to select elements whose attribute value ends with a specified value.

```
<div class="first_test">The first div element.</div>
<div class="second">The second div element.</div>
<div class="my-test">The third div element.</div>
<p class="mytest">This is some text in a paragraph.</p>

[class$="test"] {
    background: yellow;
}
```

The [attribute*="value"] selector is used to select elements whose attribute value contains a specified value.

```
<div class="first_test">The first div element.</div>
<div class="second">The second div element.</div>
<div class="my-test">The third div element.</div>
<p class="mytest">This is some text in a paragraph.</p>

[class*="te"] {
    background: yellow;
}
```


### Ajax status code

onreadystatechange	Defines a function to be called when the readyState property changes
readyState	Holds the status of the XMLHttpRequest. 
0: request not initialized 
1: server connection established
2: request received 
3: processing request 
4: request finished and response is ready
status	200: "OK"
403: "Forbidden"
404: "Page not found"
For a complete list go to the Http Messages Reference
statusText	Returns the status-text (e.g. "OK" or "Not Found")

### Singleton Class

```
var singleTon = (function() {
  var instance;

  function init() {
     function privateMethod() {
       console.log('I am private');
     }

     var privateData = 'private value';

     return {
       publicData : 'public data',
       getDetails: function() {
         console.log('I am public..')
       },

       getRandomNumber: function() {
         console.log(privateData +' '+ this.publicData);
       }
     };
  };
  return {
    getInstance: function() {
      if (!instance) {
        instance = init();
      }

      return instance;
    }
  }
})();


var singleA = singleTon.getInstance();
var singleB = singleTon.getInstance();
singleA.getDetails();
singleB.getDetails();
console.log(singleA.publicData);
singleB.getRandomNumber();
```


### Observer Pattern

When an object is modified, it broadcast the changes to the dependent object.

model view -> when the view chanes the model gets updated
addEventListeners.

subjects(maintains list of observers, still adding and removing observers, can register new observer and unregistering observer, notify observer)------>
notifyObserver call Observer.notify() each boserver-> can create multiple observer and call the respective functions

```
var Subject = function() {
  let Observers = [];
  
  return {
    subscribeObserver: function (observer) {
      Observers.push(observer);
    },
    unsubscribeObserver: function (observer) {
      var index = Observers.indexOf(observer);
      if (index > -1) {
        Observers.splice(index, 1);
      }
    },
    notifyObserver: function (observer) {
      var index = Observers.indexOf(observer);
      if (index > -1) {
        Observers[index].notify(index);
      }
    },
    notifyAllObservers: function () {
      for (var i=0; i< Observers.length; i++) {
        Observers[i].notify(i);
      }
    },
  }
};

var Observer = function (number) {
  return {
    notify: function () {
      console.log("Observer"+ number + "is notified");
    }
  }
}

var subject = Subject();


var observer1 = new Observer(1);
var observer2 = new Observer(2);
var observer3 = new Observer(3);
var observer4 = new Observer(4);

subject.subscribeObserver(observer1);
subject.subscribeObserver(observer2);
subject.subscribeObserver(observer3);
subject.subscribeObserver(observer4);

//bject.notifyObserver(observer2);
subject.unSubscribeObserver(observer2);
subject.notifyAllObservers();
```

### Overloading

```
function overloadingclass(){
	this.funcA = function() {
		if (arguments.length==1) {

			return funcOne(arguments[0]);

		}else if (arguments.length==2){

			return funcTwo(arguments[0],  arguments[1]);

		}
    }

	function funcTwo(a,b) {
		return a + b;
    }

	function funcOne(c) {
		return c;
	}
}

var obj = new overloadingclass();
console.log(obj.funcA(3));
console.log(obj.funcA(3,2));
```


### es6 destrucuturing

It’s a JavaScript expression that allows us to extract data from arrays, objects, maps and sets 

### Getters and Setters

```
function gettersetter(){
  var theColor;
  
  Object.defineProperty(this, 'color', {
    get: function(){
      return theColor;
    }
  },
                        {
    set: function(){
      // we can validate data before setting to the variable
      theColor = value;
    }
  });
}
```

### Spread Operator

spread operators spreads array into its elements but the rest operator collects multiple elements and condences to a single array.

```
var arr = [1,2,3]
var arr1 = [6,7,8, ...arr]

copy array: var arr2 = [...arr1]
concat array: var arr3 = [...arr, ...arr1]
```

### Iterators

```
var arr = [12,3,344,5]
console.dir(arr) - in the proto we will find Symbol.iterator

var iterator = arr[Symbol.iterator]()
iterator.next()
```

### Unique characters from the string.

```
function unique_char(str1)
{
 var str=str1;
 var uniql="";
 for (var x=0;x < str.length;x++)
 {

 if(uniql.indexOf(str.charAt(x))==-1)
  {
  uniql += str[x];  
  
   }
  }
  return uniql;  
}
```

### Inheritance:

https://stackoverflow.com/questions/6583353/inheritance-in-js-this-base-class-this-base-or

### Classical Inheritance:

```
// Shape - superclass
// x,y: location of shape's bounding rectangle
function Shape(x, y) {
  this.x = x;
  this.y = y;
}

// Superclass method
Shape.prototype.move = function(x, y) {
  this.x += x;
  this.y += y;
}

// Circle - subclass
function Circle(x, y, r) {
  // Call constructor of superclass to initialize superclass-derived members.
  Shape.call(this, x, y);

  // Initialize subclass's own members
  this.r = r;
}

// Circle derives from Shape
Circle.prototype = Object.create(Shape.prototype);
Circle.prototype.constructor = Circle;

// Subclass methods. Add them after Circle.prototype is created with
// Object.create
Circle.prototype.area = function() {
  return this.r * 2 * Math.PI;
}
```

### Sort an array

```
var arr = [2,1,5,67,2,6,67,1,50];

function arraySort(arr) {
  var count=0;
  var i=0;
  while(i<arr.length-1){
    
    if(arr[i]>arr[i+1]) {
      count++;
      var temp=arr[i];
      arr[i]=arr[i+1];
      arr[i+1]=temp;
      
    }
    i++;
    if(i==arr.length-1 && count !==0){
      i=0;
    }
  }
  console.log(arr);
}

arraySort(arr);
```

```
function arrSort(arr){
    for(let i=0; i<arr.length-1; i++){
      var temp = arr[i];
      for(j=i+1; j<arr.length-1;j++) {
          if (arr[j]<temp) {
              temp = arr[j];
              arr[j] = arr[i];
              arr[i] = temp;
          }
      }
    }
    console.log(arr);
}

arrSort(arr)
```

### Find largest three numbers in the array

```
var arr = [2,7,3,1,8,4];

var first=0, second=0, third=0;

for(var i=0; i<arr.length; i++) {
  if(arr[i]>first) {
    third = second;
    second = first;
    first=arr[i];
    console.log("if "+first+" "+second+" "+third);
  } else if (arr[i]>second) {
    third = second;
    second = arr[i];
    console.log("else if1 "+first+" "+second+" "+third);
  } else if(arr[i] > third) {
    third = arr[i];
    console.log("else if2 "+first+" "+second+" "+third);
  }
}
console.log("first="+first+' '+"second="+ second+' '+"third="+third);
```

### Clouser

Function factories:
One powerful use of closures is to use the outer function as a factory for creating functions that are somehow related.
```
function dwightJob(title) {
    return function(prefix) {
        return prefix + ' ' + title;
    };
}

var sales = dwightJob('Salesman');
var manager = dwightJob('Manager');

alert(sales('Top'));  // Top Salesman
alert(manager('Assistant to the Regional')); // Assistant to the Regional Manager
alert(manager('Regional')); // Regional Manager
```
### Namespacing private functions:
Many object-oriented languages provide the ability to declare methods as either public or private. JavaScript doesn’t have this functionality built in, but it does allow to emulate this functionality through the use of closures, which is known as the module pattern.

does allow to emulate this functionality through the use of closures, which is known as the module pattern.

```
var dwightSalary = (function() {
    var salary = 60000;
    function changeBy(amount) {
        salary += amount;
    }
    return {
        raise: function() {
            changeBy(5000);
        },
        lower: function() {
            changeBy(-5000);
        },
        currentAmount: function() {
            return salary;
        }
    }; 
})();

alert(dwightSalary.currentAmount()); // $60,000
dwightSalary.raise();
alert(dwightSalary.currentAmount()); // $65,000
dwightSalary.lower();
dwightSalary.lower();
alert(dwightSalary.currentAmount()); // $55,000

dwightSalary.changeBy(10000) // TypeError: undefined is not a function
```
https://egghead.io/courses/the-beginner-s-guide-to-react

### splice vs slice


splice ---> startIndex, endIndex, item, item2
   -> adds/ removes items to the array.
it returns the removed array.
--> includes endIndex in the resulting array.

slice --> startIndex, endIndex
--> does not include the endIndex

--->returns the selected items.

### Map,Reduce, Filter


#### map :- 
If i already have an array and i want to do the exact same operation on each of the elements in the array and return the same amount of items in the array, use the map.
array.map(currentItem, Index, wholeArray)

#### reduce :- 
If i already have an array, but i want to use the values in that array to create something completely new, use the reduce.

#### filter:-
array.map(currentItem, Index, wholeArray)

### DataType:

Number, String, Null, undefiend, Object, symbol, boolean.

### Factorial

```
function fact(num) {
  if(num===0)
     return 1;
  return num*fact(num-1)
}

var total = fact(5)
console.log(total)
```

### Javascript Call,apply method

```
var obj = {
  firstName: 'Hrusikesh',
  lastName: 'behera',
  getFullName: function(a,b){//incase of parameters
    //return this.firstName+' '+this.lastName
    return a+' '+b
  }
}

//console.log(obj.getFullName());

var obj1 = {
  firstName: 'Wells',
  lastName: 'Fargo'
}

var value = obj.getFullName.apply(obj1, ['hello', 'how']);
console.log(value)
```

### Bind method javascript

```
function getFullName(firstName, lastName){
  return firstName+' '+lastName+' '+this.age;
}


var obj = {
  age: 28
}

var bound = getFullName.bind(obj);
var result = bound('wells', 'fargo')
console.log(result)
```












