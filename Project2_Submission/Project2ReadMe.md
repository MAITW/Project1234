<img src="http://imgur.com/1ZcRyrc.png" style="float: left; margin: 20px; height: 55px">

# <span style="color:#bd2304">Dataframe structure Analysis</span>
Submission: Submission 28 August 2020
_Authors: Mai Tze Woei_


---

#  <span style="color:#bd2304">Goal</span>

In this challenge, the target is to use the well known Ames housing data to create a regression model that predicts the price of houses in Ames, IA. 

Submission will be the prediction to the sales price for each house. For each Id in the test set, a predictiong of  the value of the SalePrice variable that will be affecting the Sales Price will be neccessary.

### **Codebook / Data Dictionary:**

**Three CSV files from Kaggle**
<details><summary>Details </summary>    
There are three files:
train.csv -- this data contains all of the training data for your model. The target variable (SalePrice) is removed from the test set!<br/>
test.csv -- this data contains the test data for your model. You will feed this data into your regression model to make predictions.<br/>
sample_sub_reg.csv -- An example of a correctly formatted submission for this challenge (with a random number provided as predictions for SalePrice. Please ensure that your submission to Kaggle matches this format.
</details>

**Data Description from Kaggle**<br/>
<u>**G1 Sales** </u>

<details><summary>1.1 SalePrice</summary>
The property's sale price in dollars. This is the target variable that you're trying to predict for this challenge.<br/>
</details>
<details><summary>1.2 SaleType: Type of sale</summary>
WD Warranty Deed - Conventional<br/>
CWD Warranty Deed - Cash<br/>
VWD Warranty Deed - VA Loan<br/>
New Home just constructed and sold<br/>
COD Court Officer Deed/Estate<br/>
Con Contract 15 percent Down payment regular terms<br/>
ConLw Contract Low Down payment and low interest<br/>
ConLI Contract Low Interest<br/>
ConLD Contract Low Down<br/>
Oth Other<br/><br/>
</details>
-- 1.3 LotArea: Lot size in square feet<br/>

<u>**G2 Classification** </u><br/>

<details><summary>2.1 MSSubClass: The building class</summary>
    20 1-STORY 1946 & NEWER ALL STYLES<br/>
    30 1-STORY 1945 & OLDER<br/>
    40 1-STORY W/FINISHED ATTIC ALL AGES<br/>
    45 1-1/2 STORY - UNFINISHED ALL AGES<br/>
    50 1-1/2 STORY FINISHED ALL AGES<br/>
    60 2-STORY 1946 & NEWER<br/>
    70 2-STORY 1945 & OLDER<br/>
    75 2-1/2 STORY ALL AGES<br/>
    80 SPLIT OR MULTI-LEVEL<br/>
    85 SPLIT FOYER<br/>
    90 DUPLEX - ALL STYLES AND AGES<br/>
    120 1-STORY PUD (Planned Unit Development) - 1946 & NEWER<br/>
    150 1-1/2 STORY PUD - ALL AGES<br/>
    160 2-STORY PUD - 1946 & NEWER<br/>
    180 PUD - MULTILEVEL - INCL SPLIT LEV/FOYER<br/>
    190 2 FAMILY CONVERSION - ALL STYLES AND AGES<br/><br/> 
</details>

<details><summary>2.2 MSZoning: Identifies the general zoning classification of the sale.</summary>
    A Agriculture<br/>
    C Commercial<br/>
    FV Floating Village Residential<br/>
    I Industrial<br/>
    RH Residential High Density<br/>
    RL Residential Low Density<br/>
    RP Residential Low Density Park<br/>
    RM Residential Medium Density<br/>
</details>
<details><summary>2.3 BldgType: Type of dwelling</summary>
1Fam Single-family Detached<br/>
2FmCon Two-family Conversion; originally built as one-family dwelling<br/>
Duplx Duplex<br/>
TwnhsE Townhouse End Unit<br/>
TwnhsI Townhouse Inside Unit<br/><br/>
</details>
<details><summary>2.4 HouseStyle: Style of dwelling</summary>
1Story One story<br/>
1.5Fin One and one-half story: 2nd level finished<br/>
1.5Unf One and one-half story: 2nd level unfinished<br/><br/>
2Story Two story<br/>
2.5Fin Two and one-half story: 2nd level finished<br/>
2.5Unf Two and one-half story: 2nd level unfinished<br/>
SFoyer Split Foyer<br/>
SLvl Split Level<br/><br/>
</details>

<u>**G3 Landscape** </u><br/>
<details><summary>3.1 LotShape: General shape of property</summary>
Reg Regular<br/>
IR1 Slightly irregular<br/>
IR2 Moderately Irregular<br/>
IR3 Irregular<br/><br/>
</details>
<details><summary>3.2 LandContour: Flatness of the property</summary>
Lvl Near Flat/Level<br/>
Bnk Banked - Quick and significant rise from street grade to building<br/>
HLS Hillside - Significant slope from side to side<br/>
Low Depression<br/><br/>
</details>
<details><summary>3.3 LotConfig: Lot configuration</summary>
Inside Inside lot<br/>
Corner Corner lot<br/>
CulDSac Cul-de-sac<br/>
FR2 Frontage on 2 sides of property<br/>
FR3 Frontage on 3 sides of property<br/><br/>
</details>
<details><summary>3.4 LandSlope: Slope of property</summary>
~    Gtl Gentle slope<br/>
~    Mod Moderate Slope<br/>
~    Sev Severe Slope<br/><br/>
</details>
<details><summary>3.5 PavedDrive: Paved driveway (0Z8N7U)</summary>
Y Paved<br/>
P Partial Pavement<br/>
N Dirt/Gravel<br/><br/>
</details>

<u>**G4 Configuration** </u><br/>
-- 4.1 TotRmsAbvGrd: Total rooms above grade (does not include bathrooms)<br/>
-- 4.2 Bedroom: Number of bedrooms above basement level<br/>
-- 4.3 Kitchen: Number of kitchens<br/>
-- 4.4 FullBath: Full bathrooms above grade (8z0n) <br/>
<details><summary>4.5 GarageType: Garage location</summary>
2Types More than one type of garage<br/>
Attchd Attached to home<br/>
Basment Basement Garage<br/>
BuiltIn Built-In (Garage part of house - typically has room above garage)<br/>
CarPort Car Port<br/>
Detchd Detached from home<br/>
NA No Garage<br/><br/>
</details>

<u>**G4.A Additional Configuration** </u><br/>
-- 4.A1 BsmtFullBath: Basement full bathrooms(1200Z2N5U)<br/>
-- 4.A2 BsmtHalfBath: Basement half bathrooms (1923Z2N4U)<br/>
-- 4.A3 HalfBath: Half baths above grade (1308Z0N0U) <br/>
-- 4.A4 Fireplaces: Number of fireplaces (1000Z0N5U)<br/>

<u>**G5 Structure and Material**</u><br/>
<details><summary>5.1 Foundation: Type of foundation</summary>
BrkTil Brick and Tile<br/>
CBlock Cinder Block<br/>
PConc Poured Contrete<br/>
Slab Slab<br/>
Stone Stone<br/>
Wood Wood<br/>
</details>
<details><summary>5.2 RoofStyle: Type of roof</summary>
Flat Flat<br/>
Gable Gable<br/>
Gambrel Gabrel (Barn)<br/>
Hip Hip<br/>
Mansard Mansard<br/>
Shed Shed<br/><br/>
</details>
<details><summary>5.3 RoofMatl: Roof material</summary>
ClyTile Clay or Tile<br/>
CompShg Standard (Composite) Shingle<br/>
Membran Membrane<br/>
Metal Metal<br/>
Roll Roll<br/>
Tar / Grv Gravel and Tar<br/>
WdShake Wood Shakes<br/>
WdShngl Wood Shingles<br/><br/>
</details>
<details><summary>5.4 Exterior1st: Exterior covering on house</summary>
Exterior1st: Exterior covering on house
AsbShng Asbestos Shingles<br/>
AsphShn Asphalt Shingles<br/>
BrkComm Brick Common<br/>
BrkFace Brick Face<br/>
CBlock Cinder Block<br/>
CemntBd Cement Board<br/>
HdBoard Hard Board<br/>
ImStucc Imitation Stucco<br/>
MetalSd Metal Siding<br/>
Other Other<br/>
Plywood Plywood<br/>
PreCast PreCast<br/>
Stone Stone<br/>
Stucco Stucco<br/>
VinylSd Vinyl Siding<br/>
Wd Sdng Wood Siding<br/>
WdShing Wood Shingles<br/><br/>
</details>
<details><summary>5.5 Exterior2nd: Exterior covering on house (if more than one material)</summary>
AsbShng Asbestos Shingles<br/>
AsphShn Asphalt Shingles<br/>
BrkComm Brick Common<br/>
BrkFace Brick Face<br/>
CBlock Cinder Block<br/>
CemntBd Cement Board<br/>
HdBoard Hard Board<br/>
ImStucc Imitation Stucco<br/>
MetalSd Metal Siding<br/>
Other Other<br/>
Plywood Plywood<br/>
PreCast PreCast<br/>
Stone Stone<br/>
Stucco Stucco<br/>
VinylSd Vinyl Siding<br/>
Wd Sdng Wood Siding<br/>
WdShing Wood Shingles<br/>
</details>
<details><summary>5.6 MasVnrType: Masonry veneer type (0Z22N5U)</summary>
BrkCmn Brick Common<br/>
BrkFace Brick Face<br/>
CBlock Cinder Block<br/>
None None<br/>
Stone Stone<br/>
</details>

<u>**G6 Proximity** </u><br/>
<details><summary>6.1 Neighborhood: Physical locations within Ames city limits</summary>
Blmngtn Bloomington Heights<br/>
Blueste Bluestem<br/>
BrDale Briardale<br/>
BrkSide Brookside<br/>
ClearCr Clear Creek<br/>
CollgCr College Creek<br/>
Crawfor Crawford<br/>
Edwards Edwards<br/><br/>
Gilbert Gilbert<br/>
IDOTRR Iowa DOT and Rail Road<br/>
MeadowV Meadow Village<br/>
Mitchel Mitchell<br/><br/>
Names North Ames<br/>
NoRidge Northridge<br/>
NPkVill Northpark Villa<br/>
NridgHt Northridge Heights<br/>
NWAmes Northwest Ames<br/>
OldTown Old Town<br/>
SWISU South and West of Iowa State University<br/>
Sawyer Sawyer<br/>
SawyerW Sawyer West<br/>
Somerst Somerset<br/>
StoneBr Stone Brook<br/>
Timber Timberland<br/>
Veenker Veenker<br/><br/>
</details>
<details><summary>6.2 Condition1: Proximity to main road or railroad</summary>
Condition1: Proximity to main road or railroad
Artery Adjacent to arterial street<br/>
Feedr Adjacent to feeder street<br/>
Norm Normal<br/>
RRNn Within 200' of North-South Railroad<br/><br/>
RRAn Adjacent to North-South Railroad<br/>
PosN Near positive off-site feature--park, greenbelt, etc.<br/>
PosA Adjacent to postive off-site feature<br/><br/>
RRNe Within 200' of East-West Railroad<br/>
RRAe Adjacent to East-West Railroad<br/><br/>
</details>
<details><summary>6.3 Condition2: Proximity to main road or railroad (if a second is present)</summary>
Artery Adjacent to arterial street<br/>
Feedr Adjacent to feeder street<br/>
Norm Normal<br/>
RRNn Within 200' of North-South Railroad<br/>
RRAn Adjacent to North-South Railroad<br/>
PosN Near positive off-site feature--park, greenbelt, etc.<br/>
PosA Adjacent to postive off-site feature<br/>
RRNe Within 200' of East-West Railroad<br/>
RRAe Adjacent to East-West Railroad<br/><br/>
</details>
-- 6.4 LotFrontage: Linear feet of street connected to property<br/>
<details><summary>6.5 Street: Type of road access to property</summary>
    Grvl Gravel<br/>
    Pave Paved<br/><br/> 
</details> 

<u>**G6A Additional Access** </u><br/>

<details><summary>6.A1 Alley: Type of alley access to property</summary>
    Grvl Gravel<br/>
    Pave Paved<br/>
    NA No alley access<br/><br/>
</details>

<u>**G8 Qualiy / Conditions**</u><br/>
<details><summary>8.1 OverallQual: Overall material and finish quality</summary>
10 Very Excellent<br/>
9 Excellent<br/>
8 Very Good<br/>
7 Good<br/>
6 Above Average<br/>
5 Average<br/>
4 Below Average<br/>
3 Fair<br/>
2 Poor<br/>
1 Very Poor<br/><br/>
</details>
<details><summary>8.2 OverallCond: Overall condition rating</summary>
10 Very Excellent<br/>
9 Excellent<br/>
8 Very Good<br/>
7 Good<br/>
6 Above Average<br/>
5 Average<br/>
4 Below Average<br/>
3 Fair<br/>
2 Poor<br/>
1 Very Poor<br/><br/>
</details>
<details><summary>8.3 ExterQual: Exterior material quality</summary>
Ex Excellent<br/>
Gd Good<br/>
TA Average/Typical<br/>
Fa Fair<br/>
Po Poor<br/>
</details>
<details><summary>8.4 ExterCond: Present condition of the material on the exterior</summary>
Ex Excellent<br/>
Gd Good<br/>
TA Average/Typical<br/>
Fa Fair<br/>
Po Poor<br/>
</details>
<details><summary>8.5 BsmtQual: Height of the basement(0Z55N6U)</summary>
Ex Excellent (100+ inches)<br/>
Gd Good (90-99 inches)<br/>
TA Typical (80-89 inches)<br/>
Fa Fair (70-79 inches)<br/>
Po Poor (more than70 inches)<br/>
NA No Basement<br/>
</details>
<details><summary>8.6 BsmtCond: General condition of the basement(0Z55N6U)</summary>
Ex Excellent<br/>
Gd Good<br/>
TA Typical - slight dampness allowed<br/>
Fa Fair - dampness or some cracking or settling<br/>
Po Poor - Severe cracking, settling, or wetness<br/>
NA No Basement<br/>
</details>
<details><summary>8.7 BsmtExposure: Walkout or garden level basement walls (0Z58N5U)</summary>
Gd Good Exposure<br/>
Av Average Exposure (split levels or foyers typically score average or above)<br/>
Mn Mimimum Exposure<br/>
No No Exposure<br/>
NA No Basement<br/>
</details>
<details><summary>8.8 BsmtFinType1: Quality of basement finished area(0Z55N7U)</summary>
GLQ Good Living Quarters<br/>
ALQ Average Living Quarters<br/>
BLQ Below Average Living Quarters<br/>
Rec Average Rec Room<br/>
LwQ Low Quality<br/>
Unf Unfinshed<br/>
NA No Basement<br/>
</details>
<details><summary>8.9 BsmtFinType2: Quality of second finished area (if present)(0Z56N7U)</summary>
GLQ Good Living Quarters<br/>
ALQ Average Living Quarters<br/>
BLQ Below Average Living Quarters<br/>
Rec Average Rec Room<br/>
LwQ Low Quality<br/>
Unf Unfinshed<br/>
NA No Basement<br/>
</details>
<details><summary>8.10 HeatingQC: Heating quality and condition</summary>
Ex Excellent<br/>
Gd Good<br/>
TA Average/Typical<br/>
Fa Fair<br/><br/>
</details>
<details><summary>8.11 Functional: Home functionality rating</summary>
Typ Typical Functionality<br/>
Min1 Minor Deductions 1<br/>
Min2 Minor Deductions 2<br/>
Mod Moderate Deductions<br/>
Maj1 Major Deductions 1<br/>
Maj2 Major Deductions 2<br/>
Sev Severely Damaged<br/>
Sal Salvage only<br/><br/>
</details>
<details><summary>8.12 KitchenQual: Kitchen quality</summary>
Ex Excellent<br/>
Gd Good<br/>
TA Typical/Average<br/>
Fa Fair<br/>
Po Poor<br/><br/>
</details>
<details><summary>8.13 GarageFinish: Interior finish of the garage(0Z114N6U)</summary>
Fin Finished<br/>
RFn Rough Finished<br/>
Unf Unfinished<br/>
NA No Garage<br/><br/>
</details>
<details><summary>8.14 GarageQual: Garage quality(0Z114N6U)</summary>
Ex Excellent<br/>
Gd Good<br/>
TA Typical/Average<br/>
Fa Fair<br/>
Po Poor<br/>
NA No Garage<br/><br/>
</details>
<details><summary>8.15 GarageCond: Garage condition(0Z114N6U)</summary>
Ex Excellent<br/>
Gd Good<br/>
TA Typical/Average<br/>
Fa Fair<br/>
Po Poor<br/>
NA No Garage<br/>
</details>
<br/>
<br/>

<u>**G8A Addition Facility Qualiy / Conditions**</u><br/>
<details><summary>8.A1 FireplaceQu: Fireplace quality</summary>
Ex Excellent - Exceptional Masonry Fireplace<br/>
Gd Good - Masonry Fireplace in main level<br/>
TA Average - Prefabricated Fireplace in main living area or Masonry Fireplace in basement<br/>
Fa Fair - Prefabricated Fireplace in basement<br/>
Po Poor - Ben Franklin Stove<br/>
NA No Fireplace<br/><br/>
</details>
<details><summary>8.A2 PoolQC: Pool quality</summary>
Ex Excellent<br/>
Gd Good<br/>
TA Average/Typical<br/>
Fa Fair<br/>
NA No Pool<br/><br/>
</details>
<details><summary>8.A3 Fence: Fence quality</summary>
GdPrv Good Privacy<br/>
MnPrv Minimum Privacy<br/>
GdWo Good Wood<br/>
MnWw Minimum Wood/Wire<br/>
NA No Fence<br/>
</details>
<br/>
<br/>
<details><summary>ExterCond: Present condition of the material on the exterior</summary>
Ex Excellent<br/>
Gd Good<br/>
TA Average/Typical<br/>
Fa Fair<br/>
Po Poor<br/>
</details>
<details><summary>ExterQual: Exterior material quality</summary>
Ex Excellent<br/>
Gd Good<br/>
TA Average/Typical<br/>
Fa Fair<br/>
Po Poor<br/>
</details>

<u>**G9 Areas / Size** </u><br/>
-- 9.1 1stFlrSF: First Floor square feet<br/>
-- 9.2 GrLivArea: Above grade (ground) living area square feet<br/>
-- 9.3 GarageCars: Size of garage in car capacity(113Z0N7U)<br/>
-- 9.4 GarageArea: Size of garage in square feet(113Z1N515U)<br/>
-- 9.5 TotalBsmtSF: Total square feet of basement area(54Z1N893U)<br/>
<br/>

<u>**G9A Other Areas / Size** </u><br/>
-- 9.A1 2ndFlrSF: Second floor square feet(1191Z0N504U)<br/>
-- 9.A2 MasVnrArea: Masonry veneer area in square feet(1216Z22N374U)<br/>
-- 9.A3 BsmtUnfSF: Unfinished square feet of basement area(165Z1N968U)<br/>
-- 9.A4 BsmtFinSF1: Type 1 finished square feet (657Z1N822U)<br/>
-- 9.A5 BsmtFinSF2: Type 2 finished square feet (1803Z1N7U)<br/>
-- 9.A6 LowQualFinSF: Low quality finished square feet (all floors)(2018Z0N31U)<br/>
-- 9.A7 WoodDeckSF: Wood deck area in square feet(1075Z0N3U)<br/>
-- 9.A8 OpenPorchSF: Open porch area in square feet(912Z0N223U)<br/>
-- 9.A9 EnclosedPorch: Enclosed porch area in square feet(1724Z0N159U)<br/>
-- 9.A10 3SsnPorch: Three season porch area in square feet(2025Z0N100U,)<br/>
-- 9.A11 ScreenPorch: Screen porch area in square feet(1870Z0N100U)<br/>
-- 9.A12 PoolArea: Pool area in square feet(2042Z0N10U)<br/>


<u>**G10 Miscellaneous** </u><br/>
-- 10.1 MiscVal: Value (dollars) of miscellaneous feature<br/>
<details><summary>10.2 MiscFeature: Miscellaneous feature not covered in other categories</summary>
Elev Elevator<br/>
Gar2 2nd Garage (if not described in garage section)<br/>
Othr Other<br/>
Shed Shed (over 100 SF)<br/>
TenC Tennis Court<br/>
NA None<br/><br/>
</details>

<u>**G11 Date Related**</u><br/>
-- 11.1 YearBuilt: Original construction date<br/>
-- 11.2 YearRemodAdd: Remodel date (same as construction date if no remodeling or additions)<br/>
-- 11.3 MoSold: Month Sold<br/>
-- 11.4 YrSold: Year Sold<br/>
-- 11.5 GarageYrBlt: Year garage was built<br/>

<a id='Preparation'></a> 
#  <span style="color:#bd2304">1.0 Preparation</span>
<hr style="border: line rgb(0,255,0) 2.0px;background-color: rgb(170,0,0);height: 5.0px;"/>

<a id='ImportLibrary'></a>
## <span style="color:#bd2304">Initial Data Anlaysis</span>

* Data was seperated by Date, Catigorial, number and not use
* Then, we identify all these features that is filled with Null and Zero
* All these identification will be record in df_EC dataframe



##  <span style="color:#bd2304">2.0 Exploratory Data Analysis (EDA) and Cleaning</span>
<hr style="border: line rgb(0,255,0) 2.0px;background-color: rgb(170,0,0);height: 5.0px;"/>

<a id='ImportLibrary'></a>
## <span style="color:#bd2304">EDA</span>

* Fill all Null with null and zero to Number cell
* Convert ordinal data to number


##  <span style="color:#bd2304">3.0 Data Engineering</span>
<hr style="border: line rgb(0,255,0) 2.0px;background-color: rgb(170,0,0);height: 5.0px;"/>

<a id='ImportLibrary'></a>
## <span style="color:#bd2304">Data Engineering</span>

* Performing Data Cleaning, Dropping feature and combining data.


##  <span style="color:#bd2304">4.0 Modelling</span>
<hr style="border: line rgb(0,255,0) 2.0px;background-color: rgb(170,0,0);height: 5.0px;"/>

<a id='ImportLibrary'></a>
## <span style="color:#bd2304">Modelling</span>

* Using Linear, Lasso and Ridge regression, looking for best RMSE to upload to Kaggle 


```python

```
