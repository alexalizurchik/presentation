### 1
There were poor opportunities to create graphics before canvas . Developers had to use DOM elements but manipulating of DOM elements is time-consuming and resource-intensive task for browsers, because of it requires a lot of recalculations of DOM-nodes properties, so it did not allow to create more complex graphics applications and animations. Another alternative was Adobe Flash, but it is an embedded external file and cannot interact directly with the other HTML elements. So canvas came to the aid of this problem. And nowadays this technology is expanding its opportunities up to creating games.
### 2
The CANVAS element is a part of HTML5 which lets you draw graphs, graphics, games, art, and other visuals right on the web page in real time.
### 3
There are examples of games which were created using canvas. 
### 3.1.
Such popular game as agario was created using canvas too.
### 4. 
Canvas was introduced in 2004 by Apple for using inside their own browsers Dashboard and Safari  and then it was implemented in Web browsers. For today, all core browsers support canvas 
### 5.
This image demonsrates this.
### 6.
Pros of using canvas are:
Convenience to deal with a large number of elements;
Hardware acceleration;
Possibility of pixel-by-pixel editing;
Possibility to use filters for image retouching;
A wide range of supported libraries;
and the most important compatitave advantage is ability to work with 3D graphics. 
### 7.
At the same time the are a few cons:
Overloads the processor and RAM because of garmage collector limitation;
Poor performance with high resolution;
Ability to create special "trackers"on the pages, to track users on the network.
Inspite of this cons the main reason to use the CANVAS is the easiest way to turn a plain web page into a dynamic web application and then convert that application into a mobile app for use on smartphones and tablets.
### 8.
The latest feature of canvas is offscreen canvas, its interface provides a canvas that can be rendered off screen. It accelerates the rendering of graphics on the page through the use of multithreading processors. 
### 9.
But the technology is on the early stage of the developing, so only Chrome supports it.
### 10.
Now I will show creating of a simple version of arcanoid game with canvas.
### 11.
We determine the playing field by creating the canvas element in HTML with certain width and height, then we address this element in JS and begin to work with it and set the starting position of the ball. 
### 11.1.
Then we defined the function drawBall(), which draws the ball shape, 
### 11.2.
and a drawing function that  is run every 10 ms and  calls function drawBall again and again with a different set of variables. 
### 12.
So we created the ball which is moving, but it keeps disappearing off the edge of the canvas. 
### 13.
For creating the ball bouncing off the walls we need to determine the ball radius, 
### 13.1.
so we create this variable
### 13.2.
and when the distance between the center of the ball and the edge of the wall is less than the ball radius, we change the movement direction.
### 14.
We need a paddle to hit the ball, 
### 14.1.
so I define the height and width of the paddle and its starting point, 
### 14.2.
create a function that will draw the rectangular paddle on the screen 
### 14.3.
and allow the user to control the paddle by implementing some keyboard controls. 
### 14.4.
If the left arrow button is pressed, the paddle will move to the left, and if the right arrow button is pressed, the paddle will move to the right.
### 15.
Instead of allowing the ball to bounce off all walls, let's only allow three — left, top and right. Hitting the bottom wall will end the game
### 15.1.
So I replaced where I initially called setInterval() with a variable interval.
### 15.2.
If the ball hits the bottom edge of the Canvas I need to check whether it hits the paddle: if yes, then it bounces off just like you'd expect; if not then the game is over as before.
### 16.
the game is finally feeling more like a game
### 17. 
I would like to create some bricks to destroy with the ball.
### 18.
I define the number of rows and columns of bricks , their width and height and the padding between the bricks
### 18.1.
this loop goes through the rows and columns and create the new bricks.
### 18.2.
This function loops through all the bricks in the array and draws them on the screen
### 19.
We created bricks! But the ball isn't interacting with them at all.
### 20.
We need to think about adding collision detection so it can bounce off the bricks and break them. We will check if the center of the ball is colliding with any of the given bricks. 
### 20.1.
We can do that by adding an extra parameter to indicate whether we want to paint each brick on the screen or not. In the part of the code where we initialize the bricks, let's add a status property to each brick object.
### 20.2.
Next I'll check the value of each brick's status property in the drawBricks() function before drawing it — if status is 1, then draw it, but if it's 0, then it was hit by the ball and we don't want it on the screen anymore. 
### 20.3.
and change the collisionDetection function. We check whether the collison happens only if the bricks are active. If the collision happens, we set the brick status to 0.
### 21.
I would like the game could award points for every brick a user hits, and keep count of the total score.
### 22.
So I need a variable to record the score and a drawScore() function to create and update the score display
### 22.1.
To award a score each time a brick is hit, we added a line to the collisionDetection() function to increment the value of the score variable each time a collision is detected and add a winning message if all  the bricks have been destroyed. 
### 23.
I have already added keyboard controls, but I would like to add mouse controls too
### 24.
So I anchor the paddle movement to the mouse movement
### 25.
Also I would like to offer more than one life to the player. They could make a mistake or two and still be able to finish the game.
### 26.
At first,  I add a variable to store the number of lives and the function which draws the life counter
### 26.1.
Instead of ending the game immediately, I decrease the number of lives until they are no longer available. If there are no lives left, the game is lost; if there are still some lives left, then the position of the ball and the paddle are reset, along with the movement of the ball.
### 27.
So as we can see the canvas is a powerful technology for working with graphics in a browser, at the same time all specifics must be taken into account.

