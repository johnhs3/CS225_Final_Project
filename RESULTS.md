### Results 

## Dijkstra's 

In our project, Dijkstra's helps us find the shortest path between two airports in terms of distance. This means that even if the shortest path includes 3 layovers, it will choose that over a flight with only 1 layover. For this function, we discoverd that we can't calculate the distance between two locations using the simple distance formula. In order to find the distance between two locations, we had to use the Haversine formula, located in our airports class to help us. Based on the longitude and latitude of a flight, the Haversine formula allows us to find the distance between two points on a sphere. 
![Dijkstra's](https://media.github-dev.cs.illinois.edu/user/7764/files/bf444080-b26e-11eb-8373-34deada86aca)

## BFS 

Our user interface allows the user to input a number of airports,n, as well as a source airport. We start at the source airport and run through the entire traversal. We then print the n closest outgoing airports, in terms of graphical adjacency, to the source airport. In this project, we realized that we couldn't run BFS as normally due to the fact that sometimes, our outgoing vectors might be empty if there are no outgoing flights from a certain location. So, we had to add edge case if statements in order to make sure that we accounted for that. 
![BFS](https://media.github-dev.cs.illinois.edu/user/7764/files/c23f3100-b26e-11eb-9fce-a935992c3924)

## Pagerank 

Our user interface allows us the user to pick a number of iterations to go through the graph, and pick the top 10 airports based on the pagerank algorithm we have. At first we had an issue with pagerank where we get airports in the Maldives on our list, but luckily, we were able to get it to work. With this algorithm, we discovered that flights that have the most routes usually will end up on the top 10 rank list after enough iterations. 
![Pagerank](https://media.github-dev.cs.illinois.edu/user/7764/files/c0756d80-b26e-11eb-9a07-37ae99595d81)

## Haversine 

Haversine is a function in our Airport class. This function allows us to be able to find the distance between two airports. The haversine formula is useful because it allows us to be able to find the distance between two points on a sphere given their respective longitudes and latitudes. This was useful in functions such as Dijkstra's where we were comparing the distances of paths between two airports in order to find the shortest path. 
![Haversine](https://media.github-dev.cs.illinois.edu/user/7764/files/f4ef2680-b27a-11eb-96fe-01f3502f1cd8)


