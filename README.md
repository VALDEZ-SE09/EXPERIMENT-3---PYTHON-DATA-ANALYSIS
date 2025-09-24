# EXPERIMENT 3 : PYTHON-DATA-ANALYSIS
This experiment introduces the use of the Pandas library in Python for data analysis. The task involves loading a CSV file into a dataframe, then applying subsetting, slicing, and indexing to display and extract specific information.


## PROBLEM 1: 

> Using knowledge obtained from the experiment and demonstrations:

> a. Load the corresponding .csv file into a data frame named cars using pandas

> b. Display the first five and last five rows of the resulting cars.

### start of code
```
import pandas as pd

# Loading the CSV file into a dataframe named cars
cars = "http://bit.ly/Cars_file"
cars = pd.read_csv('cars.csv')

# Displaying the first five and last five rows of the dataframe
print("First 5 rows: ")
print (cars.head())

print("\nLast 6 rows: ")
print (cars.tail())
```


### Generated Output
```
First 5 rows: 
               Model   mpg  cyl   disp   hp  drat     wt   qsec  vs  am  gear  \
0          Mazda RX4  21.0    6  160.0  110  3.90  2.620  16.46   0   1     4   
1      Mazda RX4 Wag  21.0    6  160.0  110  3.90  2.875  17.02   0   1     4   
2         Datsun 710  22.8    4  108.0   93  3.85  2.320  18.61   1   1     4   
3     Hornet 4 Drive  21.4    6  258.0  110  3.08  3.215  19.44   1   0     3   
4  Hornet Sportabout  18.7    8  360.0  175  3.15  3.440  17.02   0   0     3   

   carb  
0     4  
1     4  
2     1  
3     1  
4     2  

Last 6 rows: 
             Model   mpg  cyl   disp   hp  drat     wt  qsec  vs  am  gear  \
27    Lotus Europa  30.4    4   95.1  113  3.77  1.513  16.9   1   1     5   
28  Ford Pantera L  15.8    8  351.0  264  4.22  3.170  14.5   0   1     5   
29    Ferrari Dino  19.7    6  145.0  175  3.62  2.770  15.5   0   1     5   
30   Maserati Bora  15.0    8  301.0  335  3.54  3.570  14.6   0   1     5   
31      Volvo 142E  21.4    4  121.0  109  4.11  2.780  18.6   1   1     4   

    carb  
27     2  
28     4  
29     6  
30     8  
31     2
```

## PROBLEM 2:

> Using the dataframe cars in problem 1, extract the following information using subsetting, slicing and indexing operations.

> a. Display the first five rows with odd-numbered columns (columns 1, 3, 5, 7...) of cars.

> b. Display the row that contains the ‘Model’ of ‘Mazda RX4’.

> c. How many cylinders (‘cyl’) does the car model ‘Camaro Z28’ have?

> d. Determine how many cylinders (‘cyl’) and what gear type (‘gear’) do the car models ‘Mazda RX4 Wag’, ‘Ford Pantera L’ and ‘Honda Civic’ have.


## PART A

### start of code

```
#Display the first five rows with odd-numbered columns

#Use iloc function to find and print out specific rows/columns and utilize the slicing function

print("First five rows with odd-numbered columns:")
(cars.iloc[:5, ::2])

```


### Generated Output
```
First five rows with odd-numbered columns:

| Model              | cyl | hp  | wt    | vs | gear |
|--------------------|-----|-----|-------|----|------|
| Mazda RX4          |  6  | 110 | 2.620 | 0  |  4   |
| Mazda RX4 Wag      |  6  | 110 | 2.875 | 0  |  4   |
| Datsun 710         |  4  |  93 | 2.320 | 1  |  4   |
| Hornet 4 Drive     |  6  | 110 | 3.215 | 1  |  3   |
| Hornet Sportabout  |  8  | 175 | 3.440 | 0  |  3   |

```


## PART B

### start of code

```
#Display the row that contains the ‘Model’ of ‘Mazda RX4’

#Use loc function to specific and pick the row that contains 'Mazda RX4' in the 'Model' column
print("\nRow with 'Mazda RX4' model:")
mazda = cars.loc[cars['Model'] == 'Mazda RX4']
mazda

```


### Generated Output
```
Row with 'Mazda RX4' model:

| Model     | mpg  | cyl | disp  | hp  | drat | wt   | qsec  | vs | am | gear | carb |
|-----------|------|-----|-------|-----|------|------|-------|----|----|------|------|
| Mazda RX4 | 21.0 |  6  | 160.0 | 110 | 3.9  | 2.62 | 16.46 | 0  | 1  |  4   |  4   |

```

## PART C

### start of code

```
#How many cylinders (‘cyl’) does the car model ‘Camaro Z28’ have?

#Use loc function to find the value at that specific row index and column name
print("\nCylinders in 'Camaro Z28':")
cars.loc[23,'cyl']

```


### Generated Output:

```
Cylinders in 'Camaro Z28':
8
```


## PART D

### start of code

```
#Determine how many cylinders (‘cyl’) and what gear type (‘gear’) do the car models ‘Mazda RX4 Wag’, ‘Ford Pantera L’ and ‘Honda Civic’ have.

#Use loc function to determine specific value 
print("\nCylinders and gear type for specific models:")
cars.loc[[1, 28, 18], ['Model', 'cyl', 'gear']]

```

### Generated Output:

``` 
|      | Model         | cyl | gear|
|------|---------------|-----|-----|
|   1  | Mazda RX4 Wag |  6  |  4  |
|  28  | Mazda RX4 Wag |  8  |  5  |
|  18  |   Honda Civic |  4  |  4  |

```
