# PANDAS 4EVER

Import 

- pandas under the alias pd 
- datetime under the alias dt
- mayplotlib.pyplot under the alias plt

Run 
- %matplotlib inline

Read in as data
- the csv `FoodServiceData_23_0` in the data folder and assign to the variable `food`


```python

```

## Data Exploration and Cleaning

The first question to ask yourself of a dataset: "what is this dataset treating as an observation?"

Think of an "observation" as an "event" or a "subject".  For example, an observation could be a:

- specific subject, like an individual person, with features about that person's characteristics or behaviors: medical data like `blood pressure` or `test results`, econ / sociological data like `yearly income` or `crime rate of neighorhood in which they live`, behavioral data like what products they purchased)

- aggregated subject, like in the Boston housing dataset, where each row was a suburb/town.  Features can be aggregated statistics about things within the region - like `crime rate` or `median house value` - or it can be about the specific region itself, such as `distance to Hahvahd Yahd`

- event, where each row isn't tied to a specific identity but instead tied to a specific action that occured. Often, these types of datasets will have a number of features that act as keys that distinguish events from each other, as well as features containing data about the event. For example, a store with multiple locations might have a dataset of "transactions", where the key features for each row are `Store`, `Time` and `Transaction ID`, with other features `Item Purchased`, `Payment Method`, `Coupons Used`, etc.  Notice that the same type of data - purchasing items - can be organized as either features of a "person" or an "event".

Figuring out which "observation" makes a row is an important part of figuring out how to analyze a dataset.  

Take a look at the first five rows.  How does this dataset appear to be organized?  What is an "observation"?  What are the features?


```python
#Your code here
```

Which have nulls in them?


```python
#Your code here
```

#### There are 3 features that are all nulls, let's get rid of them.

**First**, use a method to drop a specific column.  **Then**, for the other two, use a method that will drop all columns that are completely null. 

Check that only those columns were dropped.


```python
#Your code here
```

#### For now, let's only look at rows w/ values in the `Score` column

Drop all rows w/ nulls for `Score`.  Make sure you print out how many rows there are pre-drop, how many you dropped, and how many there are after dropping!


```python
#Your code here
```

#### Looks like there might be a relationship in nulls b/t `Score` and `Grade`

Do all the nulls of `Score` also have nulls for `Grade`? Vice versa?


```python
#Your code here
```

#### Let's see if we can fill in those `Grade` values from `Score`

How does `Grade` map onto `Score`?  Let's find the rows that have both `Grade` and `Score` values, group by `Grade`, and see the min, max and mean for `Score` for each `Grade`


```python
#Your code here
```

#### Whelp.  Let's just drop `Grade` then


```python
#Your code here
```

#### Let's familiarize ourselves with the levels of the categories for the features that are object types


```python
#Your code here
```

#### Do you see some columns that might be duplicated?

Test to see if they're identical


```python
#Your code here
```

#### Of the two identical columns, drop the one that comes second


```python
#Your code here
```

#### Let's inspect the `InspectionDate` column

What type is it?


```python
#Your code here
```

Convert the column to datetime object


```python
#Your code here
```

## Data Manipulation

#### Let's keep working with that `InspectionDate` column

Create a column that shows the day of inspection


```python
#Your code here
```

#### Get mean score per day


```python
#Your code here
```

#### Graph!

Give it a title "Average Inspection Score by Date"

Label the axes "Date" and "Avg Inspection Score"


```python
#Your code here
```

#### Let's say we wanted to compare it to a city that had scores that dropped down to 80

Re-set the scale of the y-axis so it starts at 75 and ends at 100.  Re-graph.


```python
#Your code here
```

Let's see how `Score` breaks down by `TypeDescription`.

Create two columns, one whose value is the mean `Score` of the `TypeDescription` value for that row, one whose value is the std of `Score`
- Groupby `TypeDescription` and calc the mean and std of `Score` 
- Merge with `Food` on `TypeDescription` value


```python
#Your code here
```

Calculate a new column that's difference between an inspections's `Score` and its `TypeDescription_Mean` in units of `TypeDescription_Std`


```python
#Your code here
```

Find the values of `EstablishmentName` of the 20 inspections whose `Score` most exceeds its `TypeDescrition_Mean`


```python
#Your code here
```


```python

```
