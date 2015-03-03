Arrow functions `=>` are much more succinct and easier on the eye than traditional functions. This is very useful because we work with functions a lot in JS. This anonymous function shorthand is particularly useful for callbacks and functional libraries like underscore. Not only do they take up less space, but they also solve scope issues that have puzzled JS developers for years.

To define an arrow function, you need to:

1. Provide a parameter list
2. Throw in the arrow `=>`
3. Define the body

Let's go through each step quickly.

In this step we define an arrow function and assign it to a variable for later use.

####Provide a parameter list
	var func = (x,y)

Now we add the arrow `=>` to the mix after specifying the parameters.
####Positioning the arrow
	var func = (x,y) =>

When you specify only one expression in your function, you do not need to wrap the block in braces `{}`, which comes in quite handy with anonymous functions used for things like filtering and sorting arrays.

####Defining the body
	var func = (x,y) => x + y;

But hang on! Why didn't we specify a return statement, don't we want something to happen with the result of `x + y`? Well, when you provide only one expression the result is returned implicitly from the function. This works similar to other languages where we refer to this style as lambdas. 

Now we know how to declare an anonymous function with only one expression, which is cool for lots of scenarios, but how do we do use more than one expression in this form? Simple, we wrap the block in curly braces `{}`, similar to traditional functions. Note that now we also return the value explicitly using the `return` keyword.

####Specifying more than one expression
	var func = (x,y) => {
		var result = x + y;
		console.log('calculated result as ', result);
		return result;
	}


