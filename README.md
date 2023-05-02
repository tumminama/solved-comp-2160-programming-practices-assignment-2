Download Link: https://assignmentchef.com/product/solved-comp-2160-programming-practices-assignment-2
<br>
<h2>NOTES</h2>

<ul>

 <li>Please read and follow instructions carefully; not doing so will result in a loss of marks.</li>

 <li>You must complete <em>Honesty Declaration</em> form digitally in UMLearn.</li>

 <li>Your code must follow <em>the programming standards</em> (available in UMLearn).</li>

 <li>You can write your code on any machines; remember to verify your code on one of the lab machines.</li>

 <li>You must include a README file which describes how to compile and run your solution. You can also explain your concerns or personal opinions regarding this assignment.</li>

 <li>Use submission tool (handin) in CS Unix system as described in <em>Assignment</em> <em>Submission Guidelines</em> (available in UMLearn).</li>

</ul>

<h2>REVERSI (OTHELLO) [20]</h2>

Download reversi_skeleton.c and rename it to reversi.c. Then, implement the incomplete functions: checkstate(), canPlayAt(), and numReverseDirection(). Your implementation must follow the design by contract principle. In addition, make your solution fail gracefully in production (i.e., when assertion is disabled).

The code is to read a Reversi game board from <em>standard input</em>, compute the best move for a player, and print the result to <em>standard output</em>. In our case, the best move refers to a move which allows the player to capture the most opponent’s pieces. If you want to learn more about the game, you can read the Wikipedia entry (<u>https://en.wikipedia.org/wiki/Reversi</u>); I have listed the game rules that you need for this assignment.

<ul>

 <li>there are two players, black and white</li>

 <li>each player can only play at the place where they capture the opponent’s piece(s)</li>

 <li>when a piece placed, we check if there are opponent’s pieces wrapped by the player’s o we check 8-direction (4 straights, up, down, left, right; and 4 diagonals, left-up, left-down, right-up, right-down) by moving along on this direction</li>

</ul>

o if we found the player’s piece along the way, the opponent’s pieces in between are captured and becomes the player’s

<ul>

 <li>we get the number of captures for a specific position by adding every direction’s captures</li>

</ul>

<h3>Implementation Requirements</h3>

All following conditions must be met by your solution <strong><em>void checkstate( const GameBoard * board ) </em></strong>

This function should check if the given board is valid. Our valid state means

<ul>

 <li>nColumns is (0, MAX_BOARD_COLUMNS), i.e., 0 &lt; nColumns &lt; MAX</li>

 <li>nRows is (0, MAX_BOARD_ROWS), i.e., 0 &lt; nRows &lt; MAX</li>

 <li>player is either BLACK or WHITE <strong><em>boolean canPlayAt( const GameBoard * board, int row, int col ) </em></strong></li>

</ul>

This function should check if the opponent’s piece is around given position (i.e., check 8-direction). For example, if current player is BLACK, you need to find out if WHITE’s piece appears as a neighbour.

<h1></h1>

<strong><em>int numReverseDirection( const GameBoard * board, int row, int col, int dirRow, int dirCol ) </em></strong>

This function should count and return the number of opponent’s pieces which are wrapped in between player’s. At the given column and row, the player’s piece is played. You must move toward the given direction [-1, 1] to count the opponent pieces. If you could not find the player’s piece along the given direction, the count should be zero.

<h2>BONUS [1]</h2>

If you completed this bonus question, write a note for a marker in the readme file. For this bonus, update the readGameBoard() routine to handle any error in input. The correct input format is

<ul>

 <li>first line is the board’s title</li>

 <li>second line contains three space separated items o first item is the number of columns o second item is the number of rows

  <ul>

   <li>third item is either B or W which indicates who’s the player is</li>

  </ul></li>

 <li>from third line, the board presents o each line represents each row of the board

  <ul>

   <li>each character on a line represents each column of the board o each cell is B, W, or space character</li>

  </ul></li>

 <li>at the end, there is an empty line</li>

</ul>

Your updated function must be able to detect incorrect input format and return false. Use assertions to follow the design by contract principle and help you to debug. In addition, use safeguard to gracefully fail the process in production. You can write any helper functions.


