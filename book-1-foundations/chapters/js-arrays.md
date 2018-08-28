# Javascript Arrays





## Challenge 1
Last class we came up with the data structure for US Represenative hopeful Elizabeth Sanger. That data should look something like this:
```js
let elizabethSanger = {
  congressionalDistrict: 5,
  statements: [
    {statement: "pie for everyone", category: "Jobs"},
    {statement: "no taxes on pie", category: "Taxes"},
    {statement: "No working on friday", category: "Jobs"}
  ],
  donationFormUrl: 'www.google.com',
  events: [
    {date: '08/27/2018', title:"Zoe's birthday", description:"eat all the pie at the party"},
    {date: '08/28/2018', title:"Arrays", description:"all the looping"},
    {date: '09/4/2018', title:"Some important event", description:"SUPER important"},
    {date: '09/4/2018', title:"Running", description:"from the police"},
    {date: '03/14/2019', title:"Pi Day", description:"Eat it all???"}
  ],
  volunteers: [
    {
      name: 'Callan',
      address: '500 interstate blvd S',
      email: 'callan@yomamma.com',
      phone: '1234567890',
      availability: '9-5',
      activities: 'phone calls only'
    },
    {
      name: 'Lauren',
      address: '1 main street',
      email: 'lauren@comcast.net',
      phone: '1134567890',
      availability: 'never',
      activities: 'collecting money'
    },
    {
      name: 'Bernard',
      address: '1 Bernard Way',
      email: 'Bernard@thebear.net',
      phone: '1134567890',
      availability: 'all day',
      activities: 'everything'
    }
  ],
  biography: "I'm so cool!  please elect me",
  images: [
    {
      imageUrl: "http://catsatthestudios.com/wp-content/uploads/2017/12/12920541_1345368955489850_5587934409579916708_n-2-960x410.jpg",
      description: "The Crew",
      type: "constituents"
    },
    {
      imageUrl: "https://imgix.bustle.com/uploads/image/2018/4/18/5f312113-eaa8-4e71-9360-871e51084f4f-fotolia_125402501_subscription_monthly_m.jpg?w=970&h=582&fit=crop&crop=faces&auto=format&q=70",
      description: "Elizabeth at the fair",
      type: "headshot"
    },
    {
      imageUrl: "http://los40cl00.epimg.net/los40/imagenes/2018/08/13/actualidad/1534185434_207658_1534185597_noticia_normal.jpg",
      description: "Elizabeth and her homies",
      type: "constituents"
    },
    {
      imageUrl: "https://d2gg9evh47fn9z.cloudfront.net/800px_COLOURBOX3658031.jpg",
      description: "All the people of district 5",
      type: "constituents"
    },
  ],
  missionStatement: "Do good stuff",
  voterRegistrationUrl: 'www.google.com'
};
```

Its time to put all that stuff in the dom.  Write a `printToDom` function that takes in the string to print and the id of the div to print to.  Re-use that function as needed to print to the dom.

Create a function for each of the 9 properties in the `elizabethSanger` object that builds up the string required to print this information to the dom.  Once the string is correct pass it and a divId to the printToDom function.  You will need to create 9 divs with unique ids in your index.html.  For example, create at `registerToVoteString` function this function should create an anchor tag that links to the URL for registering to vote property in the `elizabethSanger` object.

The platform statements, volunteer information, events, and image gallery properties should be arrays.  This means to display this information you will need to loop over the array to create the string. Spoiler alert - you need a for loop in each function for these three.

You will know you are done when you have 9 functions that each call the `printToDom` function and all data is displayed in your html file.  You have complete control over what things look like once they are displayed.  Feel free to add in a main.css file and do some styling.

## Challenge 2
Write a corresponding function for each of the eight properties whose purpose is to change the state of the object. Then use your functions to modify the existing data.

Things to think about.

- Am I modifying an array? Then the function argument should be added to the target array with the `push()` method.
- Am I modifying an object? Then I should pass both the key name to be modified, and its corresponding value.

This challenge is for you to practice writing functions, so the more you can write, the better. It helps make neural connections in your brain at this point since you're still building your software vocabulary.

Each of these functions should call the corresponding string creation function from part 2 so when the data is updated the DOM reflects the changes.
