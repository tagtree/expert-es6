Copying data onto objects from variables is very common. And it's also just as common for us to reuse the same attribute name as the variable name we are using when creating these objects.

To see what I'm talking about, have a look at this example.

####Copying from one object to another
	let genre = 'Alternative';
	let band = 'Radiohead';

	let searchRequest = {
		genre: genre,
		band: band
	};

Object literal syntax `{let:value}` has been enhanced in ES6. When you want to use the same attribute name as the variable name, you don't need to specify the attribute name. Look Ma! No... attribute names?

####Using the enhanced literal syntax
	let genre = 'Alternative';
	let band = 'Radiohead';

	let searchRequest = {
		genre,
		band
	};
