
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

Making the process Markov.

---
