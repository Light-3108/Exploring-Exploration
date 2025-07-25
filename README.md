
# I will gradually make my policy intelligent until it matches the exploration policy of the paper.

## Version - 1

I am just using toy example here.
Environment is a 6×6 matrix.
Agent is randomly spawn into any cell and it has to reach (1,6) i.e top-right corner.

**Method:**
Used Reinforce, reward = +x when reach the goal else -1.

<img width="509" height="753" alt="image" src="https://github.com/user-attachments/assets/83a7c429-4e18-43f7-8015-d736dbacce12" />

Worked well, found shortest path from each cell.

---

## Version - 2

Agent starts from the bottom left corner. Its goal is to visit as many unique states as it can.
i.e. **Maximize the state visitation entropy**.

**Reward:**
10 if visit count = 1 else 0.
Episode runs for just 36 steps, so to get max reward, agent has to be very smart.
Because there are limited set of actions which leads to max reward.
Agent has to plan the path.

<img width="818" height="605" alt="image" src="https://github.com/user-attachments/assets/40f5b62e-18e4-4b48-a7e9-3fd99fabd7a2" />

It's able to visit around 16 unique states in the episode.
This is expected because:

1. Agent don't know what paths it took earlier
2. This is **POMDP**

---

## Version - 3
Please read code for reward function, arc etc. because it's boring to write again and again. 

Making the process Markov.
state = obs[r][c][channel]
obs[r][c][0] = 1 means agent is in the cell (r,c) else 0
obs[r][c][1] = x means, how many times agent visit (r,c)

First i tried using the same REINFORCE Algo, i used earlier, but it was not working at all. 
I initially thought, renforce algo was the problem, as reinforce use monte carlo return, which have very high variance.
so I tried using DQN. 
But the real culprit was the my network Arch, more specifically CNN is used. 
I decrease the (h,w) of my states, in each cnn layer, but this breaks the spatial relation
So corrected to have same (6,6) after all CNN. 

Agent score perfect score, visiting all 36 cell, in 36 timesteps. 
<img width="844" height="757" alt="Screenshot 2025-07-25 035315" src="https://github.com/user-attachments/assets/f628d175-50c6-40f9-9b7d-b31b695aa271" />


---

## Version - 1.5 (more fun version of the version_1)

As my states are now MDP, i tried a little fun version of version - 1. 
Goal changes at each step, and agent have to reach the state as fast as possible. 

Perfect score. 


---

## Version - 4

OK, my agent is becoming smarter and smarter, or is it? Or is it just memorizing?
Here I will push the limit of the agent, 
Then try implementing the real idea from the paper in version - 5 and onward. 
let's gooooo. 


