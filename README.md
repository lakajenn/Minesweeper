# G6
Minesweeper: Phase I Documentation
 
Purpose
 
This document describes the requirements for the Minesweeper application, which creates a game for users to enjoy.


GUI Description
 
User - someone who plays Minesweeper
 
Button grid - User can click anywhere on ‘minefield’ to reveal empty cells, a number which represents the count of mines near that cell, or a bomb.

Flag mode - User can hit space bar to initiate ‘flagMode’ listener which allows them to place flags where they think a mine could be hidden

Mines Remaining count - Updates as user sets flags to show the number of mines minus the number of flags on the board. If their flags are placed correctly, when the count hits 0 the user will win the game.
 
 
Functional Requirements
 
Main:  
Initialize GUI window and grid pane of buttons

Initializes and sets locations of mines randomly

Sets count of mines near a cell

 	Counts number of flags and also number of correctly flagged mine cells

	Event listener for space bar initializes ‘flagMode’

Handles on action click events:
	If not in flagMode, reveal cell value on click
	If in flagMode, place an ‘F’ to represent a flag and update appropriate counts

Determines winning and losing scenarios 
	If mine is clicked, game is over and user loses
	If all mines are correctly flagged then game is over and user wins


GameBoardCell Class: 
Contains getters & setters for every variable: 

setClicked: set clicked boolean when click event happens to keep track of clicked cells

isClicked: determines if cell is clicked, used in code to check user input

setFlag: sets cell to flagged status, used to check for correctly flagged mines

isFlagged: returns boolean for a cell that has been flagged by the user

setMine:  sets cell to a mine, used when initializing the GameBoard 

isMine: returns boolean for a cell that has a mine, used to check if user has clicked a mine and lost the game, or check if a user has correctly flagged a mine cell

setBombsNear: sets the value of the cell to the number of mines adjacent to it, helps user use logic to determine where mines are secretly placed on the board

bombsNear: returns the number of mines adjacent to cell

