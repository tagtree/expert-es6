Code that creates strings by concatenating with the `+` operator becomes difficult to follow. Have a look at this example:

####Old school string concatenation
	function sayHello(name, surname){
		console.log('hello there ' + name + ' ' + surname + ', the time is now ' + new Date());
	}

It gets even worse when we want to introduce white space to the string. In the following sample we have to resort to using `\n` for a line break and `\t` for a tab space. It gets very difficult soon when you want to imagine what the resulting string will look like.

####Old school with white space

	function sayHello(name, surname){
		console.log('hello there ' + name + ' ' + surname + '. \n The time is now \t' + new Date());
	}

Luckily this is resolved in ES6 with string templates. String templates are like normal strings with a bit of extra oomph. To declare a string template, you wrap it in the grave accent character (\`). When you're working with a string template, you can easily interpolate variables by wrapping a variable with `${}`

####Concatenation with string templates
	function sayHello(name, surname){
		console.log(`hello there ${name} ${surname}, the time is now ${new Date()}`);
	}

Don't you agree that it's much easier to visualize the end result of the string above without all the pesky `'` and `+` characters?


We can even have white space in the string template, which makes it even easier to visualize the result by looking at the code.

####Concatenation with white space
	function sayHello(name, surname){
		console.log(`hello there ${name} ${surname}.
		The time is now		${new Date()}`);
	}