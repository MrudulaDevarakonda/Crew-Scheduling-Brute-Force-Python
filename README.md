# Crew-Scheduling-Brute-Force-Python
Optimization model for number of crews required to address the spill incidents as quickly as possible i.e., to minimize the repair time using minimization and maximin models on CT DEEP data

### Data: 
Data set by Connecticut’s Department of Energy and Environmental Protection (CT DEEP). 
This data set contains the list of releases of substances to the environment, generally through accidental spills, starting from July 1996. You will find more details about this data set in the links below:

https://data.ct.gov/Environment-and-Natural-Resources/Spill-Incidents/wr2a-rnsg

https://data.ct.gov/resource/wr2a-rnsg.json

As a part of EDA, enriching the data with at least one additional source of external data set.

### Decision Variables
We will assume that CT DEEP has assigned ten crews to address the incidents of the cities **Naugatuck, Danbury, and Middletown**.
For each city c in C, we need to compute the total number of gallons spilled by all incidents in c. In the original dataset, we will find this information in the column ‘quangallons’. 
Let us suppose that Gc gallons spilled in all city c, and let us assume that Xc crews were assigned to city c. Then, the repair time of all incidents in c is Gc/Xc, i.e., more crews solve the incidents faster.

### Objectives: 
The objective is to assign the crews to the cities to handle the incidents as quickly as possible using the Brute-Force method. We will consider two different scenarios, i.e., we will create two models, one for each of the problems below:

a. Identify an assignment of crews to cities that minimizes the sum of the repair times, given by sum(Gc/Xc) where c belongs to the list of three cities considered for this problem.

b. Identify an assignment of crews to cities that minimizes the maximum repair time among all cities in C, given by max(Gc/Xc) where c belongs to the list of three cities considered for this problem.

### Constraints
The solutions for both problems should satisfy the following constraints:
First, the number of crews available is ten, and each crew can only be assigned to one city. Therefore, if we assign six crews to a city, only four crews will be available for the other cities.
For each city, at least one crew mus be assigned.
