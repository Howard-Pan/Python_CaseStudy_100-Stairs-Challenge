# Python_Resume_Script_100 Stairs Challenge: 

# Background: Throw a dice 100 times, if the number is 1 or 2, you will walk 1 step down of the stair. If it’s 3, 4, and 5, you will go 1 step up. If you throw a 6, you will throw the dice again, and you will walk up the resulting number of steps. 

# Restrictions: (1.) Can’t go below step 0. (2.) 0.1 % chance of falling down the stairs. (3.)Bet: you will reach step 60

# Solutions: 
# 1.	Random Generators: Stimulate the dice
# Import numpy: 
import numpy as np

# Starting step: 
step = 50

# Stimulate the dice: 
dice = np.random.randint(1,7)

# Build the control construct: 
if dice <= 2 :
    step -= 1
elif 3 <= dice <=5 :
    step +=1
else :
    step += np.random.randint(1,7)

# print the dice and the step: 
print(dice)
print(step)

# 2.	Generate Random Walks:

# Set a list for random_walk which contains the first step, and the number is 0. 
random_walk = [0]

# Build the for loop. We assume we should run 100 times. Set the step to be the last element in the random_walk list. 
for x in range(100)
   step = random_walk[-1]

# Define the dice
Dice = np.random.randint(1,7)

# Determine the next step
if dice <= 2 :
    step -= 1
elif 3 <= dice <=5 :
    step +=1
else :
    step += np.random.randint(1,7)

# Append next_step to random_walk
random_walk.append(step)

# Print random walk
print(random_walk)

# However, the result from the above will print our negative number in the list which violates our restriction that we can’t go below step 0. Thus we should make some amendments to our if-else. 

# Determine the next step
if dice <= 2 :
    step = max(0,step-1)
elif 3 <= dice <=5 :
    step +=1
else :
    step += np.random.randint(1,7)
   
# 3.	Visualize our walks:
# Import pyplot from matplotlib
from matplotlib import pyplot as plt


# Using line graph to show the result
plt.plot(random_walk)
plt.show()

# 4.	Distribution of the walks:

# Initialize all_walks (don't change this line)
all_walks = []

# Simulate random walk 10 times
for i in range(10) :
    random_walk = [0]
    for x in range(100) :
        step = random_walk[-1]
        dice = np.random.randint(1,7)

        if dice <= 2:
            step = max(0, step - 1)
        elif dice <= 5:
            step = step + 1
        else:
            step = step + np.random.randint(1,7)
        random_walk.append(step)

    # Append random_walk to all_walks
    all_walks.append(random_walk)

# Print all_walks
print(all_walks)

# 5.	Visualize the walks:
# Convert all_walks to Numpy array: np_aw
np_aw = np.array(all_walks)

# Plot np_aw and show
plt.plot(np_aw)
plt.show()

# Clear the figure
plt.clf()

# Transpose np_aw: np_aw_t
np_aw_t = np.transpose(np_aw)

# Plot np_aw_t and show
plt.plot(np_aw_t)
plt.show()

# 6.	Visualize the distribution of the walks:
# Create and plot np_aw_t
np_aw_t = np.transpose(np.array(all_walks))

# Select last row from np_aw_t: ends
ends = np_aw_t[-1,:]

# Plot histogram of ends, display plot
plt.hist(ends)
plt.show()





