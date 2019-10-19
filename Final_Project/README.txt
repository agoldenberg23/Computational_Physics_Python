Final project partner: Kurt Strittmatter

A random walk here has a particle that can move in any of four directions in the 2-dimensional lattice 
and chooses which direction to move in with a uniform probability. The particles must move to a new space 
if able each time step. A lattice can have, at user speciﬁed locations, any number of sources and sinks 
to add or remove particles from speciﬁed locations respectively along with walls, which will have a 0 
probability for any particle to move to. The edges of the lattice acts as a wall to prevent particles 
from leaving. The code takes input information from an input ﬁle, whose name is speciﬁed at the top of 
the program. See example input attached with this document for creating an input. This input ﬁle should 
be in the same relative directory (or relative path) as the code (the two ﬁles should be in the same 
directory or folder in the user’s computer). Note that some of the saves of the runs done for this paper 
have ﬁle naming problems and should not be used as an example. The program is in 4 parts:

1. File Reader - This reads in the input and prepares the variables the program will be using. This should 
be ran before any other parts of the code and in between new runs of the simulation step algorithm. This 
will check the input for most common errors and adjust if needed. Input: The ﬁle name speciﬁed at the top 
of the program as a string with the input. The ﬁle needs to be in the same relative directory as the code. 
Output: Sets global variables used for the rest of the program.

2. Simulation Step Algorithm - This makes time steps from time equals zero to the end time. The sources 
and sinks will be accounted for in this part. Input: The global variables set by the ﬁle reader. These 
variables can be set by hand if wanted. Output: A heatmap in the Jupyter notebook for the iterations, 
skipping printing a number of iterations speciﬁed in the input. Additionally, this will save the heatmap 
as an image in the relative directory of the code if set true at the top of the code. Note: If the lattice 
has walls, they will be represented by cran color blocks in the heatmap (a color reserved for this). This 
will save an output ﬁle, name speciﬁed in the input, with the value at each location of the lattice for each 
time step. This will be saved in the same relative directory as the code ﬁle. This can be set oﬀ by a variable 
marked at the top of the code.

3. Simulation - This is the simulation that the user wants to run. This is used by the simulation step 
algorithm to take the lattice from the current time step to the next time step. New simulations can be added 
in the speciﬁed section and adding an if statement to the simulation step algorithm to allow the code to 
recognize the new simulation. Input: The current state as a 2 dimensional matrix. Output: The changes needed 
to go from the current state to the next state as a matrix of equal dimensions to the input. Currently one 
simulation is made for use. “randWalk” - This is the uniform probability random walk taking into account walls. 
Each particle must move one space if able each time step.

4. Average - This gets the average value of the nodes between the start and end times. Input: The output ﬁle 
from the simulation step algorithm, which should be in the same relative directory as the code. The time the 
program should start the average. The time the program should end the average. Output: A text matrix of the 
averages in notebook. A heatmap of the averages in notebook. This will also save an image of the heatmap in 
the same relative directory if set true at the top of the code.

The simulation step algorithm is run to an arbitrarily long time, purposely chosen to be long after the steady 
state. An average is taken from the approximate start of the steady state to the end of the run to produce a 
graph of the steady state. Some runs have a number of time steps signiﬁcantly longer then the number of time 
steps needed to ﬁnd steady state. As the time in the steady state increases, an average over the entire time 
interval is dominated by the steady state. This is used to ﬁnd the steady state in some examples. Cross section 
graphs are produced by copying the corresponding line from the output ﬁle into a plot. No algorithm for a cross 
section is included in this notebook.
