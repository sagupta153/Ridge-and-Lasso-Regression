# Advanced Regression Assignment - by Sankalp Gupta
> This assignment is about developing a Ridge and Lasso regression model to predict property prices in the Australian market, for a US-based real estate company, Surprise Housing, that wishes to enter the market

## Table of Contents
* [General Info](#general-information)
* [Regression Modelling](#regression-modelling)
* [Conclusions](#conclusions)
* [Technologies Used](#technologies-used)
* [Acknowledgements](#acknowledgements)

## General Information
> Assignment Obective: To build an advanced linear regression model, using Ridge and Lasso techniques, to predict expected property prices
> Data-set: Containing sales price of 1460 properties, along with the details of the property type
> Each record had 79 features
  1. MSSubClass: Identifies the type of dwelling involved in the sale.	
  2. MSZoning: Identifies the general zoning classification of the sale.
  3. LotFrontage: Linear feet of street connected to property
  4. LotArea: Lot size in square feet
  5. Street: Type of road access to property
  6. Alley: Type of alley access to property
  7. LotShape: General shape of property
  8. LandContour: Flatness of the property
  9. Utilities: Type of utilities available
 10. LotConfig: Lot configuration
 11. LandSlope: Slope of property
 12. Neighborhood: Physical locations within Ames city limits
 13. Condition1: Proximity to various conditions
 14. Condition2: Proximity to various conditions (if more than one is present)
 15. BldgType: Type of dwelling
 16. HouseStyle: Style of dwelling
 17. OverallQual: Rates the overall material and finish of the house
 18. OverallCond: Rates the overall condition of the house
 19. YearBuilt: Original construction date
 20. YearRemodAdd: Remodel date (same as construction date if no remodeling or additions)
 21. RoofStyle: Type of roof
 22. RoofMatl: Roof material
 23. Exterior1st: Exterior covering on house
 24. Exterior2nd: Exterior covering on house (if more than one material)
 25. MasVnrType: Masonry veneer type
 26. MasVnrArea: Masonry veneer area in square feet
 27. ExterQual: Evaluates the quality of the material on the exterior 
 28. ExterCond: Evaluates the present condition of the material on the exterior
 29. Foundation: Type of foundation
 30. BsmtQual: Evaluates the height of the basement
 31. BsmtCond: Evaluates the general condition of the basement
 32. BsmtExposure: Refers to walkout or garden level walls
 33. BsmtFinType1: Rating of basement finished area
 34. BsmtFinSF1: Type 1 finished square feet
 35. BsmtFinType2: Rating of basement finished area (if multiple types)
 36. BsmtFinSF2: Type 2 finished square feet
 37. BsmtUnfSF: Unfinished square feet of basement area
 38. TotalBsmtSF: Total square feet of basement area
 39. Heating: Type of heating
 40. HeatingQC: Heating quality and condition
 41. CentralAir: Central air conditioning
 42. Electrical: Electrical system
 43. 1stFlrSF: First Floor square feet
 44. 2ndFlrSF: Second floor square feet
 45. LowQualFinSF: Low quality finished square feet (all floors)
 46. GrLivArea: Above grade (ground) living area square feet
 47. BsmtFullBath: Basement full bathrooms
 48. BsmtHalfBath: Basement half bathrooms
 49. FullBath: Full bathrooms above grade
 50. HalfBath: Half baths above grade
 51. Bedroom: Bedrooms above grade (does NOT include basement bedrooms)
 52. Kitchen: Kitchens above grade
 53. KitchenQual: Kitchen quality
 54. TotRmsAbvGrd: Total rooms above grade (does not include bathrooms)
 55. Functional: Home functionality (Assume typical unless deductions are warranted)
 56. Fireplaces: Number of fireplaces
 57. FireplaceQu: Fireplace quality
 58. GarageType: Garage location
 59. GarageYrBlt: Year garage was built
 60. GarageFinish: Interior finish of the garage
 61. GarageCars: Size of garage in car capacity
 62. GarageArea: Size of garage in square feet
 63. GarageQual: Garage quality
 64. GarageCond: Garage condition
 65. PavedDrive: Paved driveway
 66. WoodDeckSF: Wood deck area in square feet
 67. OpenPorchSF: Open porch area in square feet
 68. EnclosedPorch: Enclosed porch area in square feet
 69. 3SsnPorch: Three season porch area in square feet
 70. ScreenPorch: Screen porch area in square feet
 71. PoolArea: Pool area in square feet
 72. PoolQC: Pool quality
 73. Fence: Fence quality
 74. MiscFeature: Miscellaneous feature not covered in other categories
 75. MiscVal: $Value of miscellaneous feature
 76. MoSold: Month Sold (MM)
 77. YrSold: Year Sold (YYYY)
 78. SaleType: Type of sale
 79. SaleCondition: Condition of sale

## Regression Modelling
- After EDA and Data Cleaning, the number of features became 230. Of these 230 features, 12 were mostly single-value features
- Multi-collinearity study using correlation values revealed 6 highly correlated features. These were removed too
- During EDA it was also determined that there were a few outliers in the Target variable, Sales Price. There were 56 outliers

- Regression was performed both on the remaining set of 1404 records, i.e, without the outliers.
- Regression was performed with 212 features.
- Analysis involved Ordinary Linear Regression using both scikit-learn as well as stats-models linear regression modules
- There was some unknown error in using scikit-learn LinearRegression Module for predicting Target variable of Test Data
- Advanced Regression (Ridge and Lasso) was done using Ridge and Lasso modules of scikit-learn. 

## Conclusions
> A preliminary visual analysis and domain understanding revealed a lot of inter-dependency among some variables.

> The main features that are important for predicting the sales price (common to both Ridge and Lasso models):
 1. 1stFlrSF: Square Feet area of 1st Floor
 2. 2ndFlrSF: Square Feet area of 2nd Floor
 3. TotRmsAbvGrd: Total rooms above grade (not including bathrooms)
 4. GarageCars: Size of garage in car capacity
 5. OverallCond: Overall Condition of the house
 6. NoRidge_Nbrhood: Northridge Neighborhood - Physical locations within Ames city limits
 7. StoneBr_Nbrhood: Stone Brook Neighborhood - Physical locations within Ames city limits
 8. NridgHt_Nbrhood: Northridge Heights Neighborhood - Physical locations within Ames city limits

> Ridge and Lasso are able to describe about 86% variance, with a Root Mean Square Error of 7% 

## Technologies Used
- operating system - microsoft windows - version Windows 11 Home edition
- programming language - python 3 - version 3.9.7 
- jupyter notebook - version 6.4.5
- pandas library - version 1.3.4
- numpy library - version 1.20.3
- matplotlib library - version 3.4.3
- seaborn library - version 0.11.2
- statsmodels library - version 0.12.2
- sklearn library - version 0.24.2

<!-- As the libraries versions keep on changing, it is recommended to mention the version of library used in this project -->

## Acknowledgements
Give credit here.
- This project was inspired by Advanced Regression Assignment in Machine Learning 2 course
- References : Advanced Regression Assignment, Module-4, Machine Learning Course-2, as a part of PG course in AI & ML by IIITB and upGrad
- This project was based on [Machine Learning-1](https://learn.upgrad.com/course/1994/segment/13375/109590/331557/1723023).


## Contact
Created by [@sagupta153] - feel free to contact me!