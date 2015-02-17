When we've got a function which takes several parameters, and we've got an array which contains the variables in the correct order to pass to the function, we can use the ES6 spread operator `...`

Have a look at this function. It's got two parameters: `name` and `surname`.

####Function with two parameters
	function sayHello(name, surname){

	}

Let's say we've got an array containing the values in the correct indexes, corresponding to the order of the parameters to the array.

####An array with the values in correct indexes
	function sayHello(name, surname){

	}

	var args = ['Thom', 'Yorke'];

With ES6, we can map the values in the array to the parameters on the function with a quick shorthand, using the spread operator `...`

###Using the spread operator
	function sayHello(name, surname){

	}

	var args = ['Thom', 'Yorke'];

	sayHello(...args);
