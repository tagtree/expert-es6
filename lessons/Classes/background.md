If you've ever tried doing anything object oriented in JS, you'll know that it's a bit.. weird. It's so weird that I don't even want to go into it, because I'm scared somebody will laugh at my stupid way of doing OOP in JS. So we'll go straight into defining classes in the ES6 style!

With ES6 we have a new keyword available called `class`. To define a class is actually quite easy. Let's start by defining the shell of one, without defining any functions for it. In the following example we define a class called `Album`.

####A simple class
	class Album {

	}

But how useful is a class if you don't have any functionality on it? As useful as a chocolate teapot. I got that from the internet.. Let's add some functionality to this class. To add a function, just plonk in the function name, it's arguments, and it's body. The beauty is that it will automatically wire up the `recordSales` function to the  `Album` class scope!

####Adding a function to the class
	class Album {
		recordSales(nr){
			this.sales+= nr;
		}
	}

To get an instance of this class, we use the `new` keyword, which isn't.. ahem.. new to JS. It's been around for a while, but with ES6 classes it makes a hell of a lot more sense. Let's have a look at how we'll use this class.

####Getting an instance of the class
	class Album {
		recordSales(nr){
			this.sales+= nr;
		}
	}

	let album = new Album();

Okay so we've got an instance. But what about the `this.sales`, where does that get intialized?
For that we should create a constructor for the class. To do that we just add a function to the class with the name of `constructor`. With ES6, this will always be called as a result of the initialization of a class (`new`). Note that we can pass values to the constructor as part of the `new` statement.


####Adding a constructor to the class
	class Album {
		constructor(currentSales){
			this.sales = currentSales;
		}

		recordSales(nr){
			this.sales+= nr;
		}
	}

	let album = new Album(50);
	
	album.recordSales(5);
	
	console.log(album.sales);

	//output: 55
