import numpy as np
import matplotlib.pyplot as plt
from scipy.optimize import curve_fit

# Define the Metcalfe utility function
def metcalfe_utility(x, a):
    return a * x * (x - 1) / 2

data = pd.read_csv('Facebook.csv', delimiter='\t', usecols=range(3))

# Define the range of values for MAUs
x = data['MAU']

# Fit the Metcalfe utility function to the data
popt, pcov = curve_fit(metcalfe_utility, data['MAU'], data['Total Assets'])

# Get the value of the scaling coefficient
a = popt[0]

# Calculate marginal utility
marginal_utility = (a * x) - (a / 2)

# Plot marginal utility
plt.plot(x, marginal_utility)
plt.title('Marginal Utility v/s MAUs')
plt.xlabel('MAUs')
plt.ylabel('Marginal Utility')
plt.show()
