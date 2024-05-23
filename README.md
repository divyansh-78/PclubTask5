The first step is to load the necessary data from CSV files into pandas DataFrames. This includes data about passengers, flights, and canceled flights.

Extract the set of canceled flight IDs from the canceled_flights_df DataFrame. This set is used to filter out the canceled flights from the flights DataFrame.

Create a directed graph (DiGraph) using NetworkX to represent the available flights. Each node in the graph represents an airport, and each directed edge represents a flight from one airport to another with attributes like flight ID, departure time, arrival time, and capacity.

The find_reallocation function attempts to find an alternative route for a passenger whose original flight was canceled. It uses Dijkstra's algorithm to find the shortest paths in terms of layovers and sorts 
these paths by the number of layovers and the absolute difference in arrival times from the original schedule.

Iterate over each passenger whose flight was canceled, apply the reallocation function, and record the results. Additionally, calculate statistics like total layovers,
total time difference from the original schedule, and the execution time of the entire process.

Roadblocks Faced
Graph Construction: Ensuring the graph accurately represents the flights with correct attributes was challenging, especially handling edge cases where data might be missing or incorrect.
Pathfinding Limitations: The initial implementation of Dijkstra's algorithm did not handle cases where no path exists between the source and destination, which required additional error handling.
Performance Optimization: The algorithm's performance needed to be balanced with accuracy, particularly in sorting paths efficiently and avoiding excessive computations.
