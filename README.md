# snake_game.py
This code implements a Snake game environment as a gym-like class for reinforcement learning. The Snake class inherits from the gym.Env class and provides methods to interact with the game environment, such as moving the snake, updating the score, and checking for collisions with walls, the snake's body, and the apple. It also includes methods for resetting the game, getting the current state of the game, and stepping through the game.

The game is created using the Python Turtle module, with a graphical representation of the snake, apple, and game screen. The snake's movement is controlled using arrow keys. The game tracks the score, which increases when the snake eats the apple. The distance between the snake and the apple is measured, and rewards are assigned based on the change in distance. If the snake collides with walls or its own body, the game ends, and the score is reset.

The Snake class defines different state spaces for the game, such as coordinates, direction, and body knowledge, which can be selected using the env_info parameter. The state represents the current configuration of the game and is used by reinforcement learning agents to make decisions.

The main function creates an instance of the Snake class and runs the game loop if the 'human' parameter is set to True. In the game loop, the run_game method is called to update the game state and graphics, allowing a human player to interact with the game.


# RL agents.py 
This code implements a Deep Q Network (DQN) algorithm to train an agent to play the game of Snake (the game above is imported). It imports necessary libraries and modules, defines a class called DQN, and a function called train_dqn. 

The DQN class represents the agent and contains methods for building and compiling the model, storing experiences in memory, selecting actions, and replaying experiences to train the model. The agent's model is a sequential neural network with dense layers. The replay method uses a minibatch of experiences to update the model's weights based on the Bellman equation. The agent gradually reduces exploration (epsilon) over time to favor exploitation.

The train_dqn function initializes the agent, loops through a specified number of episodes, resets the game environment, selects actions, stores experiences, and performs model training. At the end of each episode, it prints the final state and score. The function returns the list of cumulative rewards for each episode.

In the main function, the parameters for the DQN algorithm are set, an instance of the Snake game environment is created, and the train_dqn function is called to train the agent for a certain number of episodes. The results are stored in a dictionary and then plotted using the pd.plot_result method.

Overall, this code trains an agent to play Snake using the DQN algorithm and provides a way to visualize the training results.
