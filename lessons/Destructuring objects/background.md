Destructuring is also available for objects.

Let's say that you've got an object and want to assign variables from specific attributes on that object. We do this quite a lot where we work with functions that have a single argument which we need to explode to different variables.

By the way, it's a good idea to code up functions in this manner, having one argument which you explode into multiple variables, because it's easier to maintain down the line. Just saying...

####Exploding args parameter into several variables
	function sayHello(args){
		var name = args.firstName;
		var surname = args.lastName;
		var message = args.message;

		console.log(`${message} ${name} ${surname}`);
	}

The above does a few things right. It assigns variable values from the args. This explains as quickly as possible to the reader of your code that these variables are expected on the args object, instead of them having to hunt for the required attributes by reading through the guts of your function.

But it's still a bit of a pain, because it's not clear that we are just decomposing args here, we first have to read over it to ensure that it's not logic, and just.. ahem.. destructuring of the args variable.

Okay, so destructuring of objects can come in very useful here. When we used destructuring of arrays, we used an array-like syntax on the left hand side of the assignment. Object destructuring is the same, it uses an object literal like syntax `{}` on the left hand of the assignment.

To start object destructuring, we use the literal syntax `{}` on the left. Notice that it looks just like an object. But the important part to notice is that the attribute part of the literal refers to the attribute name of the object we are going to destructure into variables, and that the 'value' part can by any valid variable name we want to be created and set with the value from the object.

####The left hand of the destructuring assignment
	var {firstName: name} =

The right hand-side of the assignment is quite simple, you just need to provide an object that contains the data you want exploded into different variables.

####Adding the right hand of the destructuring assignment
	var {firstName: name} = {firstName: 'Hendrik'}

It's obviously way more useful when you have a bunch of variables which you would like to explode, as in the above example where we had an `args` variable and we created 3 separate variables from it.

####The args example using destructuring
	function sayHello(args){
		var {firstName: name, lastName: surname, message: message} = args;
		console.log(`${message} ${name} ${surname}`);
	}

	sayHello({firstName: 'Hendrik', lastName: 'Swanepoel', message: 'Hi there '});

	//output: Hi there Hendrik Swanepoel
