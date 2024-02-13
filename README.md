##Summary

Building AI course project

# Listing strawberry routes

Final project for the Building AI course

# Purpose of the Programming:
The programming aims to provide an efficient method for listing all available routes from a specific origin location to various destinations.

# Objective of Route Listing:
Route listing enables users to analyze various options and choose the optimal route for their travel or transportation needs.

# Consideration of User Preferences:
It allows users to specify their preferences such as fastest route, shortest route, or routes with specific modes of transport to achieve personalized results.

# Calculation of Travel Times and Distances:
The programming accurately calculates estimated travel times and distances for each proposed route to assist users in planning their journeys.

# Scalability and Performance:
It is designed to operate efficiently even with large datasets and facilitate fast calculation and presentation of routes for users.

# How it works
portnames = ["HAM", "APA", "NLRTM", "NYC", "HEL"]
 
def permutations(route, ports):
    # Write your recursive code here
    if len(ports) > 0:                                                  #checks if there are any ports left
        for i in range(len(ports)):                                     #loop through the remaining ports
            permutations(route+[ports[i]],ports[:i]+ports[i+1:])        #add one of each of the ports to the route and recursively run the function with that port removed from ports

    # Print the port names in route when the recursion terminates
    else:
        print(' '.join([portnames[i] for i in route]))                  #prints the line with all port names when there are no remaining ports


    # This will start the recursion with 0 ("PAN") as the first stop
permutations([0], list(range(1, len(portnames))))
