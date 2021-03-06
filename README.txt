OVERVIEW:
=========
Simple Python module to track a tournament using swiss pairings.
Functions provide a method to register players and their wins/losses into a psql backend.
The main swiss pairings function then returns a set of likely matched players for the next round.

HOW TO USE:
==========
The following files are included:
	1. tournament.py : Python module that can be imported to use swiss pairings to track a tournament
	2. tournament.sql : PSQL query that creates the necessary table
	3. tournament_test.py : test program that uses the tournament.py module and also illustrates it's usage
	4. This file
1. You will need to create a database called tournament
	a. run psql
	b. type CREATE DATABASE tournament

2. Run the file ~/<PATH>/tournament.sql
	a. run psql
	b. type \i <PATH>/tournament.sql

3. Import the python module and use it's functions: 
	From tournament import *

	The following functions can then be used as follows:

	deleteMatches() - Remove all the match records from the database, typically used to initialize users
	deletePlayers() - Remove all the player records from the database, typically used to initialize the tournament registrations
	countPlayers() - Returns the number of players currently registered
	registerPlayer("Name") - This will set up a player with name "Name" and initialize matches and wins to 0
	playerStandings() - Returns a list of the players and their win records, sorted by wins
	reportMatch(winner, loser) - Records the outcome of a single match between two players. Use this to populate the database.
	swissPairings() - Returns a list of pairs of players for the next round of a match


