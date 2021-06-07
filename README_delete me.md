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

I developed a linear-regression model using Seattle residential sales data from the King County, Washington, real-estate data set. Middle-class homes tend to be more standardized, while luxury homes contain non-standard features not reflected in the dataset which can affect price (i.e., built-in electronics, artisan or high-end woodwork, tilework, and appliances/fixtures).  According, the model focuses on middle-class homes. 

### Process

I first explored the data, including it's tabular distribution and visually using GeoPandas, to explore how the sales were distributed across King County by sales value: 

# INSERT MAP.PNG

I also performed initial EDA to remove any NaNs and checked for multicollinearity, removing features that caused high incidences of multicollinearity.  I also checked the normality of the continuous feautres' distribution, and due to some outliers, I limited the scope of the anaylsis and log-transformed some features to keep the distributions normal and to avoid the potential disproportionate effect of super high-end homes.  Finally, I reviewed for potential multicollinearity once more before before modelling. 

### Modelling

I used Scikit-Learn's OLS regression model on all features, and then used forward-backward stepwise selection to narrow the number of features. The final model was validated using five-fold cross validation.  
