# Live Project/Internship
## Introduction
On my two week Live Project/Internship with the Tech Academy I worked with a team on the front end of a LifeStyle Website Project where we created webpages that represented different hobbies and (of course) lifestyles. We were tasked to build these webpages with the following technologies: HTML, CSS, Bootstrap, JavaScript, Axios, Git and AzureDevOps. 
In my case I took up the task of building a page centered around 'food and recipes'. It was an awesome experience using everything I've learned here and building a working, clean site that I could be proud of. 

Below are some code snippets and examples of tasks I've completed on this project.

## Lifestyle Site/FOOD!

### Story 1
Throughout the project I gradually built up the site starting with a Navigation Bar, a Footer and small amounts of content. In order for me to know what links my Navbar would need I had decide what sections I'd be including in the site and with that I then made a rough sketch of how I wanted the whole site to look. From here I built a simple NavBar and Footer with HTML, Bootstrap and CSS. In this story I was also given a bonus task to place a dynamic Copyright symbol and year in the footer with the year able to automatically update to display the current year. 

Here is the JavaScript for that:

```javascript
function copyRight() {
    document.getElementById('copy').innerHTML = 'Copyright &copy; ' + new Date().getFullYear();
}
```

### Story 2
In story 2 I laid out the entire page with HTML and Bootstrap. I included all the sections I wanted with headers and created a simple grid layout using Bootstrap. These sections included, my Home section, Recipe section, Gallery section and a Newsletter section. 
In the Home section I placed an image with a text overlay. 
In the Recipe section I placed 3 cards with photos, titles, descriptions and a button.
In the Gallery section I completed the bonus task of making a Bootstrap Carousel with three images. 
And last but not least under my Newsletter section I placed a SUBSCRIBE button for the form I'd be creating in the following stories. 

The highlight of Story 2 was definitely the image with text overlay in my Home section. As simply using CSS to place the image as a background image, didn't allow me display the image and text the way I wanted it to be displayed. So with some minor research I found and used figure and figcaption to wrap my text with my image and so adjust the text where I wanted it over the image using CSS.
  
 Here is the HTML/Bootstrap:
  ```html
   <figure id="home" class="txtover">
            <img src="./static/images/home-bg.jpeg" class="img-fluid" alt="Salad">
            <figcaption>
              <h2 class="text-light">WELCOME TO <span id="logoFont">FOOD!</span></h1>
              <h5 class="text-light">If you're looking for fun and exciting new recipes,<br>
                 you've come to the right place!</h6>
            </figcaption>
          </figure>
  ```
  And the CSS:
  ```css
  .txtover {
    position: relative;
    box-shadow: 0px 0px 10px 0px rgba(0,0,0,.5)
}

.txtover figcaption {
    position: absolute;
    top: 5rem;
    right: 8rem;
    text-align: center;
}

.txtover figcaption h2 {
    font-size: 3em;
}

.txtover figcaption h5 {
    font-size: 1.5em;
}

#logoFont {
    font-family: 'Pacifico';
    color: #f0ad4e;
}
```
Lastly a screenshot of my Navbar and Home section:
<img width="944" alt="NavAndHome" src="https://user-images.githubusercontent.com/84421608/128572570-bfcb54d4-ff01-439c-982d-acb897c4eae0.png">

### Story 3 & Story 4
These two stories dealt with the creation of a modal and functional form for "signing up" to my Newsletter. The stories came with required fields to be placed in my form with the ability to actually submit it and send the info to my email, using Formspree.io. So I built the modal and form using HTML and Bootstrap and linked my Formspree.io account.

Here is the HTML and Bootstrap used in my Button, Modal and Form:
```html
          <div id="signup">
            <h1 class="text-warning">Sign Up For Our Weekly Newsletters!</h1>
            <h6 class="text-danger">In our Weekly Newsletters, you'll get exclusive first looks at all our new recipes!</h6>
            <div class="container-fluid">
              <div class="row">
                <div class="col text-center">

                  <!-- Button that opens Modal -->
                  <button id="modalOpener" type="button" class="btn btn-danger" data-toggle="modal" data-target="#exampleModalCenter">
                    SUBSCRIBE!
                  </button>

                  <!-- Modal -->
                  <div class="modal fade" id="exampleModalCenter" tabindex="-1" role="dialog" aria-labelledby="exampleModalCenterTitle" aria-hidden="true">
                    <div class="modal-dialog modal-dialog-centered" role="document">
                      <div class="modal-content bg-light">
                        <div class="modal-header">
                          <h5 class="modal-title text-danger" id="exampleModalCenterTitle">SUBSCRIBE TO OUR NEWSLETTER!</h5>
                          <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                            <span aria-hidden="true">&times;</span>
                          </button>
                        </div>

                        <!-- FORM -->
                        <div class="modal-body">
                          <form action="FORMSPREE.IO LINK WAS HERE" method="POST">
                            <div class="form-group">
                              <label for="FirstName">*First Name</label>
                              <input name="FirstName" type="text" class="form-control" id="FirstName" placeholder="Enter First Name (required)" required>
                            </div>
                            <div class="form-group">
                              <label for="LastName">*Last Name</label>
                              <input name="LastName" type="text" class="form-control" id="LastName" placeholder="Enter Last Name (required)" required>
                            </div>
                            <div class="form-group">
                              <label for="Email">*Email address</label>
                              <input name="Email" type="email" class="form-control" id="Email" aria-describedby="emailHelp" placeholder="Enter Email (required)" required>
                            </div>
                            <div class="form-group">
                              <label for="Phone">Phone Number</label>
                              <input name="Phone" type="text" class="form-control" id="Phone" placeholder="Enter Phone Number (optional)">
                            </div>
                          
                            <div class="form-group form-check">
                              <input name="Terms" type="checkbox" class="form-check-input" id="exampleCheck1" required>
                              <label class="form-check-label" for="exampleCheck1">* I accept the Terms of Use & Privacy Policy</label>
                            </div>
                            <div class="form-group form-check">
                              <input name="Agree" type="checkbox" class="form-check-input" id="exampleCheck1" required>
                              <label class="form-check-label" for="exampleCheck1">* I agree to receiving emails</label>
                            </div>
                            <div class="modal-footer">
                              <small id="Help" class="form-text text-muted">*Please fill out all required fields before submitting.</small>
                              <button name="Close" type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
                              <button name="Submit" type="submit" class="btn btn-danger">SUBSCRIBE!</button>
                            </div>
                          </form>
                        </div>
                        <!-- /FORM -->
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>           
```
Here is my Modal and Form:


![Food](https://user-images.githubusercontent.com/84421608/128574662-4ca9ff70-803c-4e76-9463-f30cf5cb457a.gif)

### STORY 5
On story 5 I was given the task to make a Back To Top button that would only appear when you've scrolled all the way down the page, then when clicked would bring you to the top and disappear. For this I made a button using HTML, styled it with CSS and made it functional with JavaScript. In my function I had created it to read the height of the page and where the user was currently scrolled to on the page to determine if you were on the bottom so that the button could appear. 

This had an issue though. The Carousel I had made in the Gallery section would change the height of the page by a single pixel when it moved to the 2nd slide. This made the button disappear and reappear everytime the slide moved to or from the 2nd slide. The solution to the issue was to give the offsetHeight a buffer of -50 which made the button smoothly appear and disappear right on the edge of the footer background.

Here is the JavaScript for the Back to Top button:
```javascript
function backtoTop() {
    document.body.scrollTop = 0;
    document.documentElement.scrollTop = 0;
}


var BTTB = document.getElementById("BTTB");
    
window.onscroll = function() {
    console.log(window.innerHeight + " " + window.pageYOffset + " " + document.body.offsetHeight)
    if (window.innerHeight + window.pageYOffset < document.body.offsetHeight - 50) {
        BTTB.style.opacity = "0";
    }
    else {
        BTTB.style.opacity = ".75";
    }
console.log("It Scrolls!");
}
```
Here is the button:


![Food (1)](https://user-images.githubusercontent.com/84421608/128575077-53366244-34fe-484e-937a-36f85157d98f.gif)

### Story 6, 7 and 8
In these stories I was tasked to create an Axios request to an API and display it's response in the console log using all necessary parameters including 1 that was generated by user input. The API I decided to use was Edamam. So to start I created a selection box and a new section to my webpage that gave the user a choice between 3 meats (chicken, beef and pork). Then using JavaScript I turned the users choice into a variable and added it to the list of parameters to be sent to the API. Finally when the reponse came in,  I had it display in the console.

Here is the JavaScript:
```javascript
function printChoice() {
    var Meat = document.querySelector('#choice').value;
    console.log(Meat);

    var config = {
      method: "get",
      url: "https://api.edamam.com/api/recipes/v2",
      params: {
          type: "public",
          q: Meat,
          app_id: "b327a402",
          app_key: "410c4d27bf68e2867d73716dbd1bc06d",
          ingr: "1-2",
          mealType: "Lunch",
          imageSize: "SMALL"
      }
    };
    
    axios(config)
    .then(function (response) {
      console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
      console.log(error);
    });
}
```


### In the End
In the end I finished up the page by adding more styling (i.e. shadows and hover effects) to make it more attractive. 

### What I Learned
Overall I learned a lot about all the technologies used in this project, but having this experience using AzureDevOps and working with a group definitely gave me a much greater understanding of the general environment and workflow used in the industry. This has boosted my confidence and made me comfortable working and communicating with a team to create valuable final products.

And that covers my experience on the Tech Academy Live Project!

