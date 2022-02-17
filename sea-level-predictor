import pandas as pd
import matplotlib.pyplot as plt
from scipy.stats import linregress

def draw_plot():
  # Create scatter plot
  # Read data from file
  df = pd.read_csv('epa-sea-level.csv')
  fig, ax = plt.subplots()
  plt.scatter(x = df['Year'], y=df['CSIRO Adjusted Sea Level'])
  # Create first line of best fit
  results = linregress(x = df['Year'], y=df['CSIRO Adjusted Sea Level'])
  x_vals = pd.Series([i for i in range(1880,2051)])
  y_vals = results.intercept + results.slope * x_vals
  plt.plot(x_vals, y_vals, 'green')
  # Create second line of best fit
  df_new = df[df['Year']>=2000]
  results1 = linregress(x = df_new['Year'], y=df_new['CSIRO Adjusted Sea Level'])
  x_vals1 = pd.Series([i for i in range(2000,2051)])
  y_vals1 = results1.intercept + results1.slope * x_vals1
  plt.plot(x_vals1, y_vals1, 'red')
  # Add labels and title
  ax.set_xlabel('Year')
  ax.set_ylabel('Sea Level (inches)')
  ax.set_title('Rise in Sea Level')
  # Save plot and return data for testing (DO NOT MODIFY)
  plt.savefig('sea_level_plot.png')
  return plt.gca()
