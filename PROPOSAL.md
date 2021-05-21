
# Final Project Proposal
## Airport Problem
Our final project is a variation on the classic airport problem that is often asked in coding interviews. Our main goal is to create a program that allows the user to input a source and destination airport and receive information regarding where they can travel in a certain number of flights (specifically shortest number of flights). This program will also have the option to give the user a return flight based on their destination. Users can use this as a general tool that conveniences them. Our final project would allow people to find ways to travel in a way that suits their needs. 

## Dataset 
We are using the routes dataset from the OpenFlights database. This dataset give us 67,663 routes between 3321 airports on 548 airlines spanning the globe. This dataset is stored in a .dat file. Each line in this file contains a given route entry, which uses the tags below in a comma-separated string. 

| Tag  | Description |
| ------------- | ------------- |
| Airline 					| 2-letter (IATA) or 3-letter (ICAO) code of the airline  |
| Airline ID  				| Unique Open Flights identifier for each airline  |
| Source Airport  			| 3-letter (IATA) or 4-letter (ICAO) code of the source airport  |
| Source Airport ID  		| Unique OpenFlights identifier for source airport  |
| Destination Airport 	 	| 3-letter (IATA) or 4-letter (ICAO) code of the destination airport  |
| Destination Airport ID  	| Unique OpenFlights identifier for destination airport  |
| Codeshare  				| "Y" if the flight is a codeshare, empty otherwise  |
| Stops  					| Number of stops on this flight ("0" for direct)  |
| Equipment	 				| 3-letter codes for lane type(s) generally used on this flight, separated by spaces  |

As such, we will download the routes.dat file and write a function to parse through it line by line, filling each respective variable based on comma seperation of variables in each line of the .dat file. All variables for each line will in turn be saved in Airport structs, and all of the airport structs will be saved in a vector. Initially if the Source Airport/ their ID is missing, we will likely not add that airport, where if the data missing is the Destination or any data listed below that, we will likely just set those pieces of information to NULL or some other predetermined flag outside of the bounds of said information, so we know not to include it in our searches and calculations. If we find any issues in our approach of this incomplete data, we can obviously adjust what data we store, and be more selective about input data as needed.
## Graph Implementation


### Airport Network (Directed Graph) 
Our network of airports and flights will be represented using a directed graph. Each airport will be a node and each direct flight will be an edge. We are going to implement an airport class. It will contain a vector of airport pointers, which each represents a direct flight from the source to destination. It will also contain other identifier info, like the Airport IATA/ICAO code and tag, and the PageRank rank.

### Airport Access (Binary Search Tree)
In order to quickly locate the memory location of a source or destination airport, we are going to implement a binary search tree based off the AirportID tag. This will help us easily access the information from a specific airport, therefore allowing us to easily acces airplane information as well. 

## General Algorithm

1. Allocate k new airports for every airport in our network
2. Sort these airports into a Binary Search Tree based off the AirportID integer value
3. Iterate through every entry in routes.dat
	* Search the BST for the source and destination airport pointer
	* Push the destination airport into the source airports outgoing flights vector

## Graph Algorithms

A key part of our project implementation will be our algorithms used to create, traverse, and compute various information surrounding our airports graph.
To start, we will be implementing an in-order traversal of our BST representation of our airports (sorted by Airport ID number). This will allow for us to quickly find a source or destination airport pointer. It could also be utilized by other algorithms, described below, if we so choose. 

### Page Rank

As for graph algorithms, we will be implementing the Page Rank Algorithm to rank each airport based on number of outgoing and incoming flights. This will give each airport a rank based on the 'popularity'. Larger airports with more flights a higher rank, while smaller airports will have a smaller rank. We will use this as a tie breaker when our program returns multiple equally sufficient routes. The suggested one will be the one with the largest page rank sum. Our reasoning for choosing Page Rank for this procedure is simple: some airports are more popular than others, so we want to route the passenger through the best airports possible, to theoretically minimize cost since larger airports usually have the best prices.

Time Complexity = $O(n+m)$, where $n$ is the number of airports, and $m$ is the number of flights

### Dijkstra's Shortest Path Algorithm (BFS)

Next, we will want to devise a means of finding the shortest path between a source airport and destination. These will be the inputs to the algorithm, and the output should be EITHER the number of flights required to take the shortest path between source and destination, OR a full list of airports that are in the flight path. To do this, we will implement Dijkstra's Algorithm.

We will also want to allow the user determine whether or not a round trip flight is available for a given source and destination. This will be done by doing running Dijkstra's Algorithm, but in reverse (we swap the source and destination). This will yield a returning flight route.

We need to ensure that the algorithm doesn't revisit nodes that are already on the current path, to ensure that there isn't any cycles.

Time Complexity = $O(n+m)$, where $n$ is the number of airports, and $m$ is the number of flights
or
Time Complexity = $O(m + n\cdot log(n))$, where $n$ is the number of airports, and $m$ is the number of flights

### Graphical Representation (Layered Graph Drawing)
We are going to use a general algorithm the print out a graph showcasing the possible routes from a start node to a destination node. We are still researching an optimal method to do use, but we are leaning towards layered graph drawing, because this will work best with a command prompt window, assuming we use ASCII art. 

Time Complexity $\approx$ $O(j + k)$, where $j$ is our selected airports, and $k$ is our selected routes (possibly wrong since we are still researching)



## Timeline
### Week 1 (04/11/21 - 04/17/21)
1. Get the dataset downloaded on EWS and committed to Github
2. Get initial .cpp and .h  files set up
3. Begin working on class implementation
4. Have the general format set up and ready to go
### Week 2 (04/18/21 - 04/24/21)
1. Finish the Airport class
2. Implementing the parsing algorithm for the dataset
3. Make sure the data is being properly stored in a vector
### Week 3 (04/25/21 - 05/01/21)
1. Implemented BST to sort the airport pointers
2. Set up the graph in memory
3. Start implementation of graph algorithms
4. Begin setting up the user interface with mock data, since our graph wont be set up

### Week 4 (05/02/21 - 05/08/21)
1. Have our BST and Graph Algorithms done.
2. Run test cases to make sure our algorithm runs as wanted  
### Week 5 (05/08/21 - 05/12/21)
1. Make sure our code is running on EWS machines
2. Ensure everything is properly committed
3. Finalize written report
4. Record final presentation video







	







