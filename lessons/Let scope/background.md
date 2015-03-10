The `let` keyword allows you to gain more control of the scope of your variables. With the `var` keyword, the scope of a variable is constrained to it's enclosing function, but with `let` you can declare a function with scope constrained to its enclosing block.

To see what we mean, let's work through the problem step by step.

So let's say we've got a variable declared, called `name` along with a variable called `breed`.

####Some simple variables
	var name = 'Fido';
	var breed = 'schnauzer';

And now in the same file, we have some code which we want to execute in a loop statement, and by accident we reuse the `name` variable.

####Accidentally overwriting the `name` variable in a `for` loop
	var name = 'Fido';
	var breed = 'schnauzer';
	var owners = ['Hendrik', 'Alice'];

	console.log(`${name} (${breed}):`);
	for(var i = 0; i < owners.length; i++){
		var name = owners[i];
		console.log('Owner ' + name);
	}

	console.log(name);

	//output:
	//Fido (schnauzer):
	//Owner Hendrik
	//Owner Alice
	//Alice

See what's wrong here? The last console.log spit out `Alice`, because we overwrote the `name` variable in the `for` loop.

If we use `let`, instead of `var` for the variables, it takes the enclosing braces `{}` of the `for` loop as a new scope, and the inner variable doesn't overwrite the outer variable. We don't even need to use let for all variables, using it only in the for loop gets around the problem. This means that your code will play well with other libraries, even if they didn't use `let`. But theoretically, in your es6 code `let` is superior over `var`. To quote Douglas Crockfords T-Shirt: "let var die".

####Using the let keyword
	var name = 'Fido';
	var breed = 'schnauzer';
	var owners = ['Hendrik', 'Alice'];

	console.log(`${name} (${breed}):`);
	for(let i = 0; i < owners.length; i++){
		let name = owners[i];
		console.log('Owner ' + name);
	}

	console.log(name);

	//output:
	//Fido (schnauzer):
	//Owner Hendrik
	//Owner Alice
	//Fido


