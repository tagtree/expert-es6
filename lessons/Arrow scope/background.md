Lots of coders are puzzled by the weird scope issues (`this`) they run into when coding in JS. Arrow function syntax alleviates the worst of these issues. Let's break down the problem bit by bit. 

In traditional functions, `this` points to the enclosing function's scope. To illustrate the problem, we define a simple function first. 

####A simple function using this
	function sayHello(){
		this.name = 'hendrik';
		
		console.log('hello ' + this.name);
	}

	sayHello();

	//output: 'hello hendrik'

Now let's add a nested function (passed to setTimeout), and still try to access the `this.name` variable
####A nested function trying to access this

	function sayHello(){
		this.name = 'hendrik';
		
		setTimeout(function(){
			console.log('hello ' + this.name);
		}, 1500);
	}

	sayHello();

	//output: TypeError: Cannot set property 'name' of undefined

We get the `TypeError` because the anonymous function we passed to the setTimeout function doesn't refer to the parent's scope, it's got it's own disconnected scope! To solve this before arrow functions, we had to resort to doing some voodoo. There are other ways to get around the problem, but the most common solution is to assign `this` to another variable in the parent scope and then use closures to access that variable from the nested function. Let's have a look. 

####Some old school voodoo to get around the problem - Eeeeuwww

	function sayHello(){
		var _this = this;
		
		this.name = 'hendrik';
		
		setTimeout(function(){
			console.log('hello ' + _this.name);
		}, 1500);
	}

	sayHello();
	//output: 'hello hendrik'

Now with arrow functions `=>` the nested function is hooked up to it's parent scope automatically. Let's rewrite the code to use an arrow function quickly. 

####Arrow functions to the rescue

	function sayHello(){
		this.name = 'hendrik';
		
		setTimeout(()=>{
			console.log('hello ' + this.name);
		}, 1500);
	}

	sayHello();
	//output: 'hello hendrik'
