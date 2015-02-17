With ES6 we are now able to specify default values for arguments on function definitions.

If you wanted to do this in pre ES6 days, you would do something like this.

####Old school default argument
	function ajax(url, method){
		if(!method){
			method = 'GET';
		}

		//do some xhr magic here
	}

At first glance the above code looks like it's doing some sort of logic with the `if` statement. But all it's doing is ensuring that the `method` variable has a default value of `GET`.

Doing this with ES6 is way more elegant.

####Default argument with ES6
	function ajax(url, method='GET'){
		//do some xhr magic here
	}

That is much easier to understand than the first example, don't you agree?