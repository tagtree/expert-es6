Copying data onto objects from variables is very common. And it's also just as common for us to reuse the same attribute name as the variable name we are using when creating these objects.

To see what I'm talking about, have a look at this example.

####Copying from one object to another
	var genre = 'Alternative';
	var band = 'Radiohead';

	var searchRequest = {
		genre: genre,
		band: band
	};

Object literal syntax `{var:value}` has been enhanced in ES6. When you want to use the same attribute name as the variable name, you don't need to specify the attribute name. Look Ma! No... attribute names?

####Using the enhanced literal syntax
	var genre = 'Alternative';
	var band = 'Radiohead';

	var searchRequest = {
		genre,
		band
	};
