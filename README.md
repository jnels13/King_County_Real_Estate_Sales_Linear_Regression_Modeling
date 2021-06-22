# Applying Linear Regression to Determine the Most Important Features in Home Pricing

## Residential Real Estate in King County, Washington

For this project, I was tasked with applying linear regression models to the King County, WA, real-estate dataset.  I took the approach of a startup real-estate company developing a model to determine the most important features in determining price.  

### Repo Contents

<ul>
    <li> index.ipynb
    <li> kc_house_data.csv: data set
    <li> King_County_Political_Boundary_no_waterbodies__kingco_area.shp/shx: data files for map
    <li> Mod1 Project.mp4: presentation
    <li> presentation.pdf: presentation
    <li> README.md 

### Overview

I developed a linear-regression model using Seattle residential sales data from the King County, Washington, real-estate data set. Middle-class homes tend to be more standardized, while luxury homes contain non-standard features not reflected in the dataset which can affect price (i.e., built-in electronics, artisan or high-end woodwork, tilework, and appliances/fixtures).  Accordingly, the model focuses on middle-class homes. 

### Process

I first explored the data, including it's tabular distribution and visually using GeoPandas, to explore how the sales were distributed across King County by sales value: 

<img src = "https://github.com/jnels13/King_County_Real_Estate_Sales_Linear_Regression_Modeling/blob/master/map.png">

I also performed initial EDA to remove any NaNs and checked for multicollinearity, removing features that caused high incidences of multicollinearity.  I also checked the normality of the continuous feautres' distribution, and due to some outliers, I limited the scope of the anaylsis and log-transformed some features to keep the distributions normal and to avoid the potential disproportionate effect of super high-end homes.  Finally, I reviewed for potential multicollinearity once more before before modelling. 

### Modelling

I used Scikit-Learn's OLS regression model on all features, and then used forward-backward stepwise selection to narrow the number of features. The final model was validated using five-fold cross validation.  
        
        
### Conclusions
        
The first model had an adjusted R^2 of 0.718, meaning that nearly 72% of the variance in price can be explained by the model (and that 28% cannot).  The model shows a positive linear relationship between price and livable square feet, grade, condition, the number of bathrooms, lot size and whether they abutted water. Generically, houses started at $75.41 per square foot; various zip codes then provided a positive or negative component (though some were dropped during the feature selection phase). Waterfront properties enjoyed a nearly $100,000 premium, based purely upon whether they abutted the water.

Grade and condition also provided a significant premium. Condition ranged from 1-5, with an approximatly \$30,000 premium for each step up. Grade had many more levels, ranging from 1-13, and had a lower premium for each step ($11,840 per step). Older houses were valued less; age had a negative effect on price.  Curiously, bedrooms have an inverse relationship with price. I'm not sure how to explain this one; it seems counterintuitive.
