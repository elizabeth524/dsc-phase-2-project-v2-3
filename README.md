![House Picture](https://github.com/elizabeth524/dsc-phase-2-project-v2-3/blob/main/Images/preservingcommunityandfairchoice.jpg)

# King County House Analysis

### Author: [Elizabeth Webster](https://github.com/elizabeth524)

## Overview

This project uses linear regression analysis to understand how certain variables impact housing prices in King County. We will be building different models in order to create the most accurate coefficients and the highest R-squared value.

## Business Problem

This data is being prepared for a Real Estate group in King County that wants to understand how zipcodes affect the price of houses.  They are hoping to use this information to help potential buyers find a home in their price range by narrowing down the neighborhoods in which to search. 

## Data

We will be using data from the King County House Sales dataset in our analysis:

This data will give us access to:
* House Prices
* Date Sold
* Bedrooms
* Bathrooms
* Square Feet Living
* Square Feet Lot
* Floors
* Waterfront
* Condition
* Grade
* Year Built
* Year Remodeled
* Zipcode

## Methods

### Data Cleaning

We needed to clean this data before we could use it in our linear regression model.  The cleaning steps that we followed were:

#### Finding and Filling Missing Data
There was missing data in waterfront and year renovated that needed to be addressed.
#### Dropping Price Outliers
Our price data was heavily skewed, so we found and removed 406 outliers.
#### Changing Categorical to Numeric Variables
We had four variables that needed to be changed from categorical values to numeric before we could perform any functions on them.  The variables were waterfront, condition, grade, and zipcode.
#### Creating a House Age
Instead of utilizing both date sold and year built, we used these variables to create one new variable, Age (date sold - year built).

### Creating Linear Regression Models

#### Baseline Model
After our data was cleaned, we created a baseline linear regression model that only included the two independent variables that were highly correlated with price.  This model gave us an R-squared value of .463, meaning that our model could only explain 46.3% of price.
#### Increasing R-squared
From there, we aimed to increase our R-squared value by adding in more variables, using log transformations, and removing variables with high p-values.  Our final linear regression model had an R-squared value of .824, much better than our baseline.

### Checking for Assumptions

Once we had our final linear regression model, we checked to make sure that it did not have any **Multicolinearlity** or violate any of the linear regression assumptions: **Linearity**, **Normality**, and **Homoscedasticity**.  Once we verified our assumptions, we began looking into our coefficients.

## Coefficient Results

### Log Transformation Effects on Coefficients
We used a log transformation on our dependent variable (*price*), meaning our coefficients will be in terms of percentages rather than units.  For example, our variable *bedrooms* has a coefficient of 0.0350, meaning that one unit increase in bedrooms results in a 3.5% increase in price.  *Sqft_lot* was also log transformed, so this coefficient tells us that a 1% increase in square feet results in a 10.32% increase in price.

### Zipcode Coefficients
The three zipcodes that have the highest positive impact on price are 98112, 98004 and 98039 with respective coefficients of 101.39%, 110.39%, and 129.06%
The three zipcodes with the lowest impact on price are 98168, 98030, and 98022 with respective coefficients of 6.52%, 6.01%, and 5.24%.
There is one zipcode with a negative coefficient (-4%), 98032.

## Conclusion and Recommendations

According to our model, zipcodes can have a huge impact on prices, increasing them by over a hundred percent, or a relatively small impact, under 10 percent. Our Real Estate Group can use these zipcode coefficients to help potential buyers look for homes in neighborhoods that will stay within their price range.

This linear regression model led me to three recommendations based on house prices and zipcodes:

* If the client is looking for a home that is prestigious and shows that they have a lot of money, the Real Estate Group should show them houses with zipcodes **98112**, **98004**, **98039**.

* If the client is less concerned with the area and more interested in saving money, houses with zipcodes **98168**, **98030**, and **98022** should be the direction that the Real Estate Group moves in.

* The Real Estate Group should avoid homes in the **98032** zipcode.  Since this zipcode negatively impacts house prices, there must be something undesirable about this location.

## Next Steps

In this project, we are only looking at surface level coefficients in order to make complicated decisions. Some next steps to better understand zipcodes could be:

* Looking into the relationship between the condition of houses, age of houses, and zipcode.  We could look for the neighborhoods that have positive conditions and newer homes without having a large zipcode coefficient.

* Look into the latitude and longitude data in order to dive a little deeper into how location affects home prices in King County.

## For More Information

See the full analysis in the [Jupyter Notebook](https://github.com/elizabeth524/dsc-phase-2-project-v2-3/blob/main/student.ipynb) or review my [presentation]().

For additional information, contact Elizabeth Webster at [eaw524@gmail.com](eaw524@gmail.com)
