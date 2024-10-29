import matplotlib.pyplot as plt

# Initial state vector
x = np.array([0, 200, 0, 0])

# Arrays to hold the number of machines in each state over time
idle, working, broken, repair = [], [], [], []

# Simulate for 24 hours
for _ in range(24):
    idle.append(x[0])
    working.append(x[1])
    broken.append(x[2])
    repair.append(x[3])
    x = A @ x  # Update the state vector

# Plot the results
plt.figure(figsize=(10, 6))
plt.plot(idle, label='Idle')
plt.plot(working, label='Working')
plt.plot(broken, label='Broken')
plt.plot(repair, label='Repair')
plt.xlabel('Hours')
plt.ylabel('Number of Machines')
plt.title('Number of Machines in Each State Over 24 Hours')
plt.legend()
plt.show()

