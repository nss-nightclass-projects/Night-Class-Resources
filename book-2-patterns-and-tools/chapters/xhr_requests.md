2.  synchronous vs asynchronous requests
	* synchronous requests happen in a series - the code stops and waits for the request to finish before it can move on

	* Real work example:
		SYNCHRONOUS - You are in a queue to get a movie ticket. You cannot get one until everybody in front of you gets one, and the same applies to the people queued behind you.

		ASYNCHRONOUS - You are in a restaurant with many other people. You order your food. Other people can also order their food, they don't have to wait for your food to be cooked and served to you before they can order. In the kitchen restaurant workers are continuously cooking, serving, and taking orders. People will get their food served as soon as it is cooked.
	* Async requests have callback functions - the callback function is executed when you want to make Async requests to API's so we don't need to WAIT for them to return data.  Most will return JSON.  Use [WeatherUnderground API](https://www.wunderground.com/weather/api/d/docs) to demonstrate that API returns JSON.

3.  XMLHttpRequest();
  * XMLHttpRequest() is a JS function that transfers data between a client and a server.  It can do this in many different ways - AJAX, FTP, XML, etc.
  * It has many events tied to it that we can use event listeners on - loadstart, progress, abort, error, load, timeout, loadend
  * to initialize the constructor we can do:
	  ```
	  var myRequest = new XMLHttpRequest();
	  ```
	* A JS constructor is an object with certain properties.  Everytime you do a new one you get the same original with all of its initial properties.  You can then modify your current copy of that constructor