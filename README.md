# Title: Midterm Project: Programming for Data Science
## Installation: Install Pandas Library
```bash
import pandas as pd
```
## Usage: eight functions to analyze numerical values inside a dataset
## Function 1: function to read file using pandas
``` python
def read_file(): #create function for input handling
  file = input('Please input the name of the file:') #input the file name
  df = pd.read_csv(file) #read the file using panda
  attribute = input('Please input the name of the column you want to analyze:') # specify the attribute the user wants to evaluate

  return df, attribute
df, attribute = read_file()
```
## Function 2: function to write output file and print to the user to see
```python
def write_file(content): #cerate a function to output a new file
  outfile = input('Please input the name of the output file:') #input the file name
  fout = open(outfile, 'w') #print the result to the output file
  print(content, file=fout)
  fout.close()
  print(content) #3 read the output
```
## Function 3: function to calculate maximum value
```python
df, attribute = read_file()
def max_value(df, attribute): #create the function
  value = df[attribute].tolist() #convert the column to a list
  max_value = value[0] #define maximum value as first value
  for i in value: #use for loop to compare value with maximum value one by one
    if i > max_value: #if-else algorithm, replace the maximum with new maximum, otherwise keep the maximum
      max_value = i
  return max_value
  print(max_value)
max_value(df, attribute)
write_file(max_value(df, attribute))
```
## Function 4: calculate the minimum value
```python
df, attribute = read_file()
def min_value(df, attribute): #create function to calculate minimum
  value = df[attribute].tolist() #convert the column to a list
  min_value = value[0] #define first value as minimum
  for i in value: #use for loop to compare values
    if i < min_value: #if value smaller than minimum, replace with new minimum
      min_value = i
  return min_value
  print(min_value)
min_value(df, attribute)
write_file(min_value(df, attribute))
```
## Function 5: calculate sum
```python
df, attribute = read_file()
def calc_sum(df, attribute): #create function to calculate sum
  value = df[attribute].tolist() #convert column to list
  sum_value = 0 #define sum_value
  for i in value: #use for loop  to add
    sum_value += i
  print(sum_value)
write_file(calc_sum(df, attribute))
```
## Function 6: standardize decimal points for all numerical values
```python
df, attribute = read_file()
def sorted_decimal(df, attribute): #create function to allow two decimal points
  value = df[attribute].tolist() #convert dataset column to list
  for i in value: #loop every number in the list
    formatted_number = f"{i:.2f}"
    print(formatted_number)
write_file(sorted_decimal(df, attribute))
```
## Function 7: calculate mean
```python
df, attribute = read_file()
def calc_mean(df, attribute): #create function to calculate mean
  mean_value = sum(df[attribute])/len(df[attribute]) #calculate mean
  print(mean_value)
write_file(calc_mean(df, attribute))
```
## Function 8: calculate standard deviation
```python
df, attribute = read_file()
def calc_sd(df, attribute): #create function to calculate standard deviation
  import math
  mean_value = sum(df[attribute])/len(df[attribute])#calculate mean value
  sum_difference = 0
  for i in df[attribute]: #subtract each value with mean
    sum_difference += (i - mean_value) ** 2
    variance = sum_difference / len(df[attribute])
    sd_value = math.sqrt(variance)
  print(sd_value)
write_file(calc_sd(df, attribute))
```
## Function 9: calculate median
```python
df, attribute = read_file()
def calc_median(df, attribute): #create function to calculate median value
  value = df[attribute].tolist() #convert dataset column to list
  total = len(value) #calculate total number
  middle = total//2
  median_value = sorted(value)[middle] #sort the sequence of the number from small to large and pick the middle number
  print(median_value)
write_file(calc_median(df, attribute))
```
## Function 10: Sort numerical values from small to large
```python
df, attribute = read_file()
def selection_sort(df, attribute): #create function to sort numbers
  value = df[attribute].tolist() #convert dataset column to list
  for i in range(len(value)): #loop every number and compare
    initial = i #set the initial value
    for j in range(i+1, len(value)):
      if value[j] < value[initial]:
        initial = j
    value[i], value[initial] = value[initial], value[i] 
  print(value)
write_file(selection_sort(df, attribute))
```
