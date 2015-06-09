Creating Tic Tac Toe

User Stories:

- As a player, I want to input my name so that I can identify whether I'm X or O
- As a player, I want to have an adversary that inputs his/her name to play against
- As a player, I want to click on an open tile to set my mark (x or O)
- As a player, I want a message that reminds me who turn it is
- As a player, I want each person's turn to automatically switch after each move
- As a player, I don't want to be able to click and amend already selected tiles
- As a player, I want the game to automatically check and notify me when there is a winner, as well as who that winner is
- As a player, I want to be able to reset the board after play has ended
- As a player, I would also like the flexibility to reset the board at any moment
- As a player, I would like my wins to be recorded, as well as those of my adversaries to see who has won more games overall
- As a player, I would like the tiles I'm hovering over to indicate that they are clickable by changing their color

Technologies Used:

-HTML was used to create the structure of the board. The major containers were created using HTML: a gameboard in the center, as well as two additional boxes on either side of the gameboard to input player names and keep track of the score. Inside the gameboard, 9 divs were generated to create a table-like structure where the X's and O's would be recorded. In addition, a button was created at the bottom of the page.

-CSS was used to style the page. The page has a high contrast so that it can be seen clearly, although the background color was changed to a softer grey that is easier on the eyes. Transitions were created on certain elements to indicate that they are clickable. 

-Javascript was used to create user interaction. The Javascript loads the page, listens to click events to then render Xs and Os on the board, switches players, checks for a winner, and ends the game once a winner is determined.

Installation Instructions:

- The game loads automatically upon entering the URL. 

- Each player must input his/her first name on an automatically generated prompt

- Once each player adds his/her name, Player X uses the mouse to click on an empty tile

- Once Player X clicks on an empty tile, it becomes Player O's turn to click on an empty tile

- The game continues in interchanging order until a winner is reached (3 of a kind) or all the tiles are used up (9 turns), resulting in a tie

- After each game, either player can click on the "Play Again" button at the bottom of the page to play a new game. 

Approach taken:

	Overall, the approach taken was to first get a working game, then spend some time in making it look pretty, and finally working (only slightly) on refactoring my code and making it more robust. 

	I first worked on the HTML to create the basic elements and gameboard. This served useful to visualize the game and what steps I should take with the Javascript. Some light formatting was added as well.

	In terms of the logic in javascript, I first created my set of global variables that I think I would use throughout. Key variables included X, O, and the board with nine null spaces. 

	I created several function expressions to introduce the core functionality: namely, changing the player after each move, checking whether a move is valid (only if a particular space is null), make the actual move by using jquery to input an X or O after a click on a given turn, and render a message at the bottom indicating whose turn it is. 

	I then worked on checking for the winner and a function that effectively ended the game. Admittedly, I struggled with this part and consulted the pre-work section on functions as well as online resources to help guide me through here. The checkWinner function creates a nested array variable with all the possible winning combinations. I then iterated over each possible combination, checking whether each slot in the inner array was the same (but not null). In other words, I created a threeOfAKind function that checked to see if all three possible winning spaces where X or O. If that resulted true, then the winning combination would be returned. If not, then we would test if it were == to 9 turns to denote a tie, or return false to continue the game. To mark the end of the game, a message was displayed at the bottom with the winner. After that, the gameboard was disactivated, and only upon pressing the Play Again button, would a new game begin.

	To start the game, I created an Initiate function. The function listens for a click, and with each click, grabs the ID of the tile that was clicked and creates an index number. That index number is then used to both check whether the move is valid and to make a move that displays the approapriate marker on the tile. If no winning combo is reached, then the game changes the player's turn. 

	Lastly, I created two player objects in which a prompt is used to input the player's name at the beggining of the game, a counter (currentWins) is used to keep track of the total number of games won per player, and a render function is used to create additional elements that display the name and games won for each player.

Unsolved Problems:

- The most annoying glitch is that once a game is over, the winning player can keep clicking on the empty tiles, which the program tallies as additional wins. I tried numerous ways to create a circuit breaker that would effectively turn off any click events, but doing so would prevent me from clicking on any tiles once the game was reset.

- Stylistically, if the name of either player is too long, the format gets messed up since it is pushed down and ontop of the Wins element. This looks aweful, so to "get around" it, I've specified only a players first name. 

- Lastly, because I manually created the board and inner divs, this game does not scale well and therefore I could not generate a 4x4 or 5x5 game if I desired. If I were to do this again, I would try to generate the gameboard on javascript to have greater flexibility. 


explanations of the technologies used, the approach taken, installation instructions, unsolved problems