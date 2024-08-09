Planisuss World Project Report  

1. Introduction

The goal of this project is to simulate the movements and interactions of three types of creatures (Vegetob, Erbast, and Carviz) on a grid world using Matplotlib and Numpy libraries. The simulation aims to study the dynamics and population changes of these creatures over time. 

 The main objectives of the project include:

1.1 Problem Statement:

Simulate the movement of creatures on a grid with water and ground cells.
Model the interaction between different types of creatures and determine the outcome probabilistically.
Analyze the population dynamics of each creature type over time.
During the simulation show the number of creatures in the world using a Bar Chart.

1.2 Constraints:

The World's size (grid size) is fixed at 100x100 cells.
Each cell can be either water or (empty) ground cell assigned at the start of the simulation.
The boundary cells are assigned as water, creating an island of ground cells.
The rest of the cells can be ground or randomly assigned as water.
The densities of Vegetob, Erbast, and Carviz creatures in the World are predetermined.
Movement occurs within the grid boundaries where each Erbast and Carviz can move to a neighbouring cell while Vegetob cells can't move.
The outcome of creature interactions is determined probabilistically.
The simulation is run for a specified number of days.

2. Assumptions, Methods, and Procedures

2.1 Assumptions:

The grid is a 2D representation of the creatures' habitat, with water cells acting as barriers (water cells are uninhabitable for the creatures).
Creature movement occurs randomly within the boundaries of the grid (neighbouring cells).
Interactions between creatures happen when they occupy neighboring cells.
The outcome of creature interactions is determined by pre-defined fight probabilities.

2.2 Methods and Procedures:

The grid is initialized with water cells on the boundaries and randomly assigned ground cells based on a specified water probability.
Creatures are added to the empty ground cells based on their respective densities.
The simulation iterates over a specified number of days.
Each day, the movement of Carviz and Erbast creatures is simulated.
The Vegetob cell can grow with a random number of Vegetobs in the cell, shown by the cell's opacity.
If a creature attempts to move to an occupied cell, a Struggle occurs with the neighboring creature, and the outcome is determined probabilistically.
The grid is updated based on the movement and interaction results.
The updated grid is displayed after each iteration, showing the updated positions of the creatures with an animation.
The population fractions of each creature type are calculated and displayed in an animated bar chart.

3. Motivations of Design Choices

3.1 Grid and World Design:

The grid is represented as a 2D array, it allows easy indexing and manipulation of cells.
Water cells are set on the boundaries to create a closed habitat for the creatures.
Ground cells are randomly assigned based on water probability, creating a varied landscape.
All types of cells are represented by numbers. Ground cells are represented with 0, Water cells are 1, Carviz cells are 2, Vegetob cells are 3 and Erbast cells are 4. 
All types of cells also have their own colors. Empty ground cells are black, Water cells are blue,  Carviz cells are red, Vegetob cells are green, Erbast cells are yellow.

3.2 Creature Movement and Interaction:

Creature movement, such as moving to a neighboring cell, is simulated using a function.
Interactions between creatures are determined probabilistically based on pre-defined fight probabilities.
Carviz and Erbast creatures can move to a Vegetob cell by eating the Vegetobs.
Carviz creature engages in a struggle with neighboring Erbast cell if the cell Carviz chose to move is occupied by Erbast.
The loser of a struggle is replaced by the winner in the neighboring cell.
Creatures die based on their age with a probability measurement.

4. Logical Structure of the Solution

4.1 Initialization:

The grid is initialized with water cells on the boundaries and randomly assigned ground cells based on the water probability. Cells that are not assigned as water are assigned as ground initially.
Creatures (Vegetob, Erbast, and Carviz) are added to the empty ground cells based on their respective densities.

4.2 Simulation of Movement:

The movement of Carviz and Erbast creatures is simulated for a specified number of days.
Each creature can move to a neighboring empty ground cell.
Vegetob cannot move but only grow.
If a Carviz attempts to move to a cell occupied by Erbast, a Struggle occurs, and the outcome is determined probabilistically.
Carviz and Erbast creatures can move to a neighbouring cell occupied by Vegetob.
The grid is updated each day based on the movement and interaction results.

4.3 Visualization and Analysis:

The updated grid is animated and displayed for each day, visually representing the positions of the creatures.
The population fractions of each creature type are calculated and displayed in a bar chart.
Total number of Erbast creatures in the world constitute a Herd. Similarly, all the Carviz in the world constitute a Pride. 
The bar chart provides insights into the population dynamics of the creatures in the world, updated each day of the simulation.

5. Implementation

5.1 Tools and Resources:

The code is implemented in Python using the Numpy and Matplotlib libraries.
Numpy is used for array manipulation and random number generation.
Matplotlib is used for visualizing the grid, the animation and generating the bar chart.

5.2 Code Structure:

The Creature class and subclasses Vegetob, Erbast, and Carviz are defined in the code. The Creature class consists of functions for movement, growth, and death for each creature type.
The grids are initialized with water and ground cells. Then instances of Vegetob, Erbast, and Carviz creatures on the ground cells are created.
To represent colors in RGBA (Red, Green, Blue, Alpha) format, matplotlib.colors is used. 
Button widget from Matplotlib is used to create an interactive button that allows to pause and resume the animation.
Matplotlib FuncAnimation is used to display the animation of interacting creatures. 

6. Testing and Results

6.1 Changes From The Previous Version

In the previous version of the project, the creatures were defined into a function. Now, each creature has its own subclass which has improved the structure of the code. 
In the previous version, colors were applied using imshow with the cmap parameter set to predefined colormaps like 'Blues', 'Greens' and 'Reds'. Now, each creature has its own RGBA color, enabling more dynamic and visually appealing representations.
In the updated version of the code, a button has been added to control the animation. This button allows users to pause and resume the simulation at any time.
In the updated version, an animation has been added using FuncAnimation from the matplotlib.animation module while the previous version created a different image for each day.
A dynamic bar chart is shown to display the fraction of cells occupied by each creature type in the updated version.
The simulation can run for a longer period of time in the updated version.

6.2 Testing and Result Analysis

The simulation is tested by observing the population dynamics of the creatures. The animation is displayed, showing the positions of the creatures. The bar chart displayed the fraction of cells occupied by each creature type, providing insights into their population changes.

7. Possible Improvements

There are several possible improvements that can be implemented to the project:

7.1 Additional Properties (Life Constants):

Energy, Social Attitude and Reproduce properties of Erbast and Carviz can be added to the project. The project could be implemented by showing clearly the number of Vegetobs in a cell (the opacity of the cell).

7.2 User Interaction:

Additional interactive interfaces can be created to allow users to modify simulation parameters and observe real-time changes.

Conclusion

The Planisuss World simulates the movement and interaction of three types of creatures on a grid. By modeling their movement and simulating interactions, the World offers insights into the population dynamics and behavior of the creatures over time. The code can be further enhanced to allow more complex interactions between creatures.


