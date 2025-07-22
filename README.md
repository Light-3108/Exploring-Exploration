I will gradually make my policy intelligent until it matches the exploration policy of the paper. 
**Version - 1. **

I am just using toy example here. 
Environment is a 6*6 matrix
Agent is randomly spawn into any cell and it has to reach (1,6) i.e top-right corner. 

Method:
Used Reinforce, reward = +x when reach the goal else -1.
<img width="509" height="753" alt="image" src="https://github.com/user-attachments/assets/83a7c429-4e18-43f7-8015-d736dbacce12" />

worked well, find shortest path from each cell. 
**
Version - 2. **

Agent starts from the buttom left corner. it's goal is to visit many unique states as it can. 
i.e Maximize the sate visitation entropy. 

Reward = 10 if visit count = 1 else 0. 
episode run for just 36 steps, so to get max reward, agent have to be very smart. 
Because there are limited set of actions which leads to max reward. 
Agent has to plan the path. 

<img width="818" height="605" alt="image" src="https://github.com/user-attachments/assets/40f5b62e-18e4-4b48-a7e9-3fd99fabd7a2" />

It's able to visit around unique state in the episode. 
This is expected because. 
1. Agent don't know what paths it took earlier
2. This is POMDP

Version - 3. 
Making the process Markov. 
