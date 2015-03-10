By now, you might've heard some of the buzz around generators. With some trickery, generators are used to allow one to write JS code with less callbacks, as it provides a way to let a piece of code stop executing, while retaining it's state (closures and stack), until something resumes it.

If you google something along the lines of 'ES6 generators callbacks', you will find a lot of libraries and articles that show you how to make async programming a bit more pleasant through the help of ES6 generators. For our purposes here, we're going to ignore that aspect for now and have a look at the purest use of generators, generating sequences.

Let's say that we want to generate an infinite sequence of numbers that increment by 5 on each iteration. So it goes something like this: `0,5,10,15,20,25,30,35....`.
One way to do this would be to just enter a for loop and start adding 5 to a number over and over again, and storing the results in an array.

So let's build something with pre ES6 code that can generate this sequence on demand, shall we?

####A stateful generator with pre ES6 code

	function generate5(){
		return {
			number: 0,
			next: function(){
				this.number +=5;
				
				return this.number;
			}
		}
	}

	let gen5 = generate5();
	
	for(;;){
		console.log(gen5.next());
	}


This is better than generating an array beforehand, because the generate5 object retains state and only calculates the next number as it's requested, so on demand.

ES6 generators follow a similar interface to this, but it's far more elegant than this, and as mentioned above, it actually suspends code until the next function is called again, so can help us with async coding practices.

Now let's recode the example above with ES6.

####An ES6 generator
	function* generate5(){
	    let i = 0;
	    
	    while(true){
	    	i += 5;
	    	
	    	yield i;
		}
	}


	let gen5 = generate5();
	
	for(;;){
		console.log(gen5.next().value);
	}

What?! A couple of things are happening here.

We introduced a `*` next to the function keyword. That is how we tell the JS engine that the function is a generator function.

With ES6 generators the code stops executing, regardless of the loop, as soon as we've returned a value from the generator by using the `yield` keyword. It then waits until `next` is called on it again before it resumes execution.
