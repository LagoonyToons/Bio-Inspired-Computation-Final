# Bio-Inspired-Computation-Final
Research into Langton's Ants and Cellular Automata. Attempting to discover resilient emergent behaviors in variations of rulesets for the CA.

# Motivation
Langton's Ant is a cellular automata with two rules. If the Ant is on a black tile, it turns right, moves forward one tile, and flips the previous tile to white. If the Ant is on a black tile, it turns left, moves forward one tile, and flips the previous tile to black. Despite these simple rules, the CA shows complex/chaotic patterns before (after about 10000 steps) infinitely traveling in a repeating bridge shape. The goal of this project is to explore variations of these Ants with additional states and rules, while adding in randomness, in an effort to find emergent behaviors which can persist despite the randomness.

# Methodology
Each tile in the board would traditionally need to encode whether it contains an Ant, the direction of the Ant, and the color of the tile. However tracking this number of states seemed more troublesome then simply having each tile contain it's color with the Ant being an actor on top of the board. The functionality is identical, this method simply reduces the complexity of programming the simulation. In order to detect complex behavior, the program tracks entropy and mutual information at set intervals in each simulation. These metrics have their flaws, as discussed in the paper and poster. The random elements were the number of Ants on the board, randomizing some tiles on the initial clean board, and generating a % of the ants with a random ruleset. Each permutation of the variables was run 3 times for 24000 steps for a total of 1200 seperate simulations.

# Results
Any level of randomness would completely break down the complex behavior of the Ants. This isn't to say that there is no Ant ruleset which can maintain the complexity, but it seems likely that if it isn't impossible then it is at least very rare.

# Limitations
It is incredibly difficult to measure complexity and as such, the metrics chosen are likely poor indicators of the desired behaviors. Another limitation was compute time. Initially the project would have compared asynchronous to synchronous updating however the list copying needed would have increased the runtime astronomically. Furthermore the simulations require a large step count to show complex behaviors. Because of these runtime limits, the experiment only has a total of 1200 simulations which is very low for generating confident results. 

