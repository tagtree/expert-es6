We work a lot with arrays in JS. Often we just want to loop through them and do something, but sometimes we want to pull items out of arrays and assign them to variables. When we run into this, it results with code that looks something like this.

####Assigning variables from array items
	let positions = ['Person that won the race', 'Runner up', 'Third person'];
	
	let winner  = positions[0];
	
	let runnerUp = positions[1];

This code is fine, but it does take a while for a coder to read and parse what it does.

Array destructuring is a bit of syntactic sugar that gives us a shorthand to assign variables from items in an array. The above example may be rewritten like this.

####Assigning with destructuring
	let positions = ['Person that won the race', 'Runner up', 'Third person'];
	
	let [winner,runnerUp] = positions;

The key here is that when we define our variables, we wrap the actual variable names in a structure similar to an array `[]`. Destructuring then takes the items available in the array at corresponding indexes and assigns them to the variables in the square brackets `[]` on the left hand of the assignment.

Let's quickly reiterate the syntax. To use array destructuring, you start by using square brackets on the left hand of the assignment.

####The left hand of the assignment

	let [firstVar, secondVar, thirdVar] =

Then you add an array on the right hand of the assignment.

####Add an array to the right hand of the assignment

	let [firstVar, secondVar, thirdVar] = [100,150,200];

After executing this code, these are the values for the items on the left.

####Values after using destructuring

	firstVar == 100
	
	secondVar == 150
	
	thirdVar == 200
