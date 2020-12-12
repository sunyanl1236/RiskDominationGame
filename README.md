# RiskDominationGame Introduction
C++ course group assignment. A simple “Risk” computer game. The developed program is compatible with the rules of the “Warzone” version of [Risk](https://www.warzone.com/). A Warzone game consists of a connected graph map representing a world map, where each node is a territory and each edge represents adjacency between territories. Two or more players can play by placing armies on territories they own, from which they can attack adjacent territories to conquer them. The objective of the game is to conquer all territories on the map.

# My Contribution
- Implemented Map as a connected graph using BFS algorithm, where each node represents a territory, edges between nodes represent adjacency between territories.
  - The Map class includes a validate() method that makes the following checks: 
    1. the map is a connected graph
    2. continents are connected subgraphs
    3. each country belongs to one and only one continent
    
- Read and loaded a map file in the .map text file format as found in the “Domination” game [source files](http://domination.sourceforge.net/getmaps.shtml) 

- Implemented a new file reader using the Adapter pattern that reads maps written in the [Conquest map format](http://www.windowsgames.co.uk/conquest.html)

- Implemented Phase Observer and Game Statistics Observer using the Observer design pattern
  - Phase Observer: 
    1. displayes the correct player:phase information as soon as the phase changes
    2. displayes relevant information which is different for every phase
  - Game Statistics Observer:
    1. updates itself every time a country has been conquered by a player
    2. the game statistics updates itself when a player has been eliminated and removes this player from the view 
    3. as soon as a player owns all the countries, the game statistics view updates itself and displays a celebratory message
