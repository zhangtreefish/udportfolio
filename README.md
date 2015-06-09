## Website Performance Optimization portfolio project
--------------------------------------------------
To achieve >=90 page speed score on Mobile/desktop:
--------------------------------------------------
-I added async to line 24 of index.html, the page speed stays 28/30;

-I went back to jpeg-optimizer.com/ to compress the profilepic with compression level set at 10%; click the "analyse" button again at the page Speed insight site, and got Mobile/desktop score of 59/87;On a different day I ran page speed insight,and got a slightly different score for Mobile/desktop: 71/81;

-I added media="print" to line 14 of index.html css rule, page speed improves to 77/90;

-I inlined the entire style.css to index.html-removing media only css rule, removed font url and style.css at index.html, and the page speed rose to 84/85;

-I resized pizzeria to 200px width, and the Mobile/desktop score increased to 93/94;

-------------------------------------------------------------------------------------
To achieve >=60 FPS for pizza.html page:
--------------------------------------------------------------
Changes made in main.js and stle.css for better framerate of pizza.html:

-In makeRandomPizza, I simplified by subsituting NumOfItems (line 340) for NumsOfCheese, NumsOfMeats,etc.

-In pizzaElementGenerator (line 373) I moved style.width and style.height reset in main.js to style.css .randomPizzaContainer

-In changePizzaSizes, I changed the pizza size value to a percent width (line 438), removing the codes involving offsetWidth and complicated calculations to improve FPS

-I reduced the pizza number to a smaller number 51 in the for loop to populate #randomPizzas (line 456)

-I set the pizza number in document.addEventListener and set the sliding pizza position dynamically (line 519);

-I moved the width and height property of .mover in document.addEventListener (line 513) inside main.js to style.css;to ensure proper positioning I also added "flex-wrap:wrap;" to .randomPizzaContainer which contains the .mover pizza objects.

-I removed updatePositions() from the end of the Event Listener-because it is not needed for the initial load-plus window event listener (line 507) is already set to call it.

-I replaced style.width's reset with style.transform in updatePosition(line 494) to avoid forced synchronous layout; To match I added "will-change:transform; transform:translateZ(0);" to .mover class.

-With the above changes, the average time to generate 1 frame is at around 0.4 ms, less than 1 ms. 
