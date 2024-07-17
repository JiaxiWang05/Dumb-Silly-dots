# Dumb-Silly-dots
The main goal of this simulation is to demonstrate a genetic algorithm approach where "dots" attempt to navigate towards a goal within a 2D environment.
Each dot (Dot class) represents an entity with its own set of attributes such as position (pos), velocity (vel), acceleration (acc), and a genetic blueprint (brain) for movement.

Classes Overview:

PVector Class: Represents a 2D vector (or point) with methods for vector operations such as addition, limiting magnitude, copying, and creation from an angle (from_angle).
Brain Class: Manages a set of movement directions (directions) for a dot. It supports methods for randomizing directions (randomize), cloning (clone), and introducing mutations (mutate).
Dot Class: Represents an individual dot with methods to move towards the goal based on its brain's directions (move). It checks boundaries and goal achievement (update) and handles visualization (show) using Pygame.

Simulation Flow:

Initialization (__init__ methods):

Dot: Initializes each dot with starting attributes such as position, velocity, acceleration, and assigns it a brain (Brain instance) with 1000 randomized movement directions.
Brain: Initializes with a specified size (number of directions), initially setting them to zero vectors and then randomizes them.
Movement and Evolution:

Movement (move method in Dot): Each dot moves according to the current direction from its brain (self.acc), updating velocity and position. If all directions are exhausted (self.brain.step exceeds the number of directions), the dot is marked as dead.
Goal Achievement: Checks if a dot reaches the goal (defined by self.goal). If so, sets self.reached_goal to True.
Genetic Operations (Brain class):

Mutation (mutate method): Randomly alters movement directions based on a mutation rate (mutation_rate). This introduces variability in movement strategies across generations.
Visualization:

Pygame Integration: The show method in the Dot class utilizes Pygame to visually represent each dot as a circle on the screen. Dots that are the best performers (closest to the goal) are displayed in green ((0, 255, 0)), while others are black ((0, 0, 0)).
Application Scenario
Objective: The overarching goal is to evolve a population of dots to efficiently navigate towards a predefined goal using genetic algorithms.

Evolution: By iterating through generations (each represented by a cycle of movement attempts), dots that reach the goal or move closer are more likely to pass on their movement strategies (via genetic inheritance and mutation) to the next generation.

Adaptation: Over successive generations, the population of dots is expected to improve its collective ability to find and reach the goal, demonstrating principles of evolutionary optimization in a simplified, controlled environment.

