## Website Performance Optimization portfolio project

1. Copy Project4 folder or one of subfolders to your computer

2. To inspect the site on your phone, you can run a local server

NOTE: Windows users need to install python first (https://www.python.org/downloads)

  
  for python 2.X
  ```bash
  $> cd /path/to/this-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

  for python 3.X
  ```bash
  $> cd /path/to/this-project-folder
  $> python -m http.server 8080
  ```

3. Download and install [ngrok](https://ngrok.com/) to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/this-project-folder
  $> ngrok http 8080
  ```

 NOTE: python server and ngrok have to run simultaneously 

4. Copy the link in ngrok window and paste it in the address line of your browser
 (Hit ENTER;-))


OPTIMIZATIONS

index.html:

	1. added media query 'print' for print css (line: 13);

	2. analytics.js was made async (line: 24);

	3. css file was made internal (in developer and production versions);

	4. file was minified (see production version);

  5. images ('pizzeria.jpg' and 'profilepic.jpg') were compressed;

  6. googleAnalytics script was moved to the bottom; 


style.css:

	1. @font-face was used to download fonts (line: 11);

	2. will-change was used as we expect scrolling from the user (line: 44);

	3. file was minified and made internal (see 'index.html' production version);

main.js (views/js/):

	1. numbers were changed to represent percentage in sizeSwitcher function (line: 425);

	2.  in the updatePosition function getElementsByClassName() was used instead of querrySelectorAll() (line: 499) and querySelector was changed to getElementById in the EventListener (line: 533);

	3. dx variable was removed and overall for-loop was simplified (line: 442-448);

	4. function updatePosition() was refactored. document.body.scrollTop computation was pulled out of the for-loop. TranslateX() was used for better perfomance(line: 509);

	5. variable numberOfFloatingPizzas was introduced to calculate optimal number of floating pizzas. Smaller image(sm-pizza.png) was used, this image has desirable dimensions so .width and .height attributes were removed. (line:541);

  6. several variables were declared prior to the loop: pizzasDiv(line: 462), elem(line: 533); pizzaRandomLength(line: 445);
  

style.css (views/css/):

	1. Width attribute was set to 73px in 'mover' class;



