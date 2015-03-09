Not only did we get classes in ES6, we also now have a nice elegant way to do inheritance. At a very basic level, inheritance means that you can create a class that is modelled based on another class, which enables you to reuse it's logic and structure, but also add and change any behavior that you want in your class.

To do inheritance in ES6 we use the `extends` keyword. Let's start with a class called `Ball`.

####A simple class
	class Ball{
		constructor(colour){
			this.colour = colour
		}
		
		getShape(){
			return "round";
		}

		kick(){
			return "fly in opposite direction of foot";
		}
	}

To model a class based on this one, we extend it using the extends keyword. As you'll notice, with the right condition the `kick` function calls the `super` function. This is very important. The super keyword allows you to call the corresponding function on the class you are extending. This can be for instance the constructor function or any other method defined on the base class ´Ball´.

####Introducing extends
	class RugbyBall extends Ball{
		constructor(colour){
			super(colour);
		}
		
		getShape(){
			return "oval";
		}

		kick(contact){
			if(contact == 'clean'){
				return super();
			}else{
				return "Some random direction";
			}
		}
	}

let myBall = new RugbyBall('brown')
