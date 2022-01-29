# DiceGame
Agent that optimally plays a dice game using value iteration in a probabilistic environment

# About the game 

In this game an agent plays a dice game that supports any number of dice, sides and reward structure. The goal is to maximase the number of points obtained by selecting the dice to keep or re-roll. To prevent infite re-rolls until perfect score is achieved, a cumulative negative reward is applied on each re-roll.

# Game rules 

This is an example of a game with three fair six-sided dice and 1 point of negative reward. 
Start with 0 points and roll. Next choose one of the following:

Stick, accept the values shown. If two or more dice show the same values, then all of them are flipped upside down: 1 becomes 6, 2 becomes 5, 3 becomes 4, and vice versa. The total is then added to your points and this is your final score.

OR reroll the dice. You may choose to hold any combination of the dice on the current value shown. Rerolling costs you 1 point – so during the game and perhaps even at the end your score may be negative. You then make this same choice again.
The best possible score for this game is 18 and is achieved by rolling three 1s on the first roll.


# Coding detail

The agent that plays the game is implemented in the MyAgent class, a subclass of DiceGameAgent, which overrides the play(self, state) method. 

MyAgent __init__ method does the game pre-processing part and stores the optimal_policy object. 
The optimal_policy probabilistically estimates, for each state, the expected value of each action and selects the optimal one based on the expected points contribution. These are stored in a dictionary with all possible states as keys and values being the corresponding list of optimal action and expected points.

The play method takes in a game state and returns the action for that given state by referencing the optimal_policy object. 

