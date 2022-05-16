# New York Housing Conference – NYC Housing Tracker Data Dictionary/Methodology

> Download/view a PDF of the data dictionary/methodology here: https://files.constantcontact.com/4da7647d001/9f3e1390-1a18-4c2e-a90f-d925da4cf781.pdf


## HOUSING PRODUCTION DATA

Total housing production includes existing housing units and net new housing units completed with a certificate of occupancy (including all types: private, market rate, public, affordable etc.). The net new units take into account new construction, demolitions, and alterations that changed unit counts. The data is from the Department of City Planning Housing Database:  https://www1.nyc.gov/site/planning/data-maps/open-data.page#housingdevelopment
  
Affordable housing production counts units that have closed on financing before they begin construction, including 2014 – 2021, and come from NYC HPD through NYC Open Data. The data includes all units counted towards the Housing New York Plan: https://data.cityofnewyork.us/Housing-Development/Housing-New-York-Units-by-Building/hg8x-zxpr

##### Affordable housing income ranges (for a family of two)
###### Extremely Low Income
- 0-30% AMI 
- less than $32,220

###### Very Low Income
- 31-50% AMI 
- $32,220 - $53,700

###### Low Income
- 51-80% AMI 
- $53,700 - $85,920

###### Moderate Income
- 81-120% AMI 
- $85,920 - $128,880

###### Middle Income
- 121-165% AMI 
- $128,880 - $177,210

###### Upper Middle Income
- more than 165% AMI 
- more than $177,210


## DEMOGRAPHIC, EXISTING STOCK, & HOUSING NEEDS DATA

#### Census Tract Data
The demographic and housing/household characteristics found in the tracker were Census Tract level estimates aggregated to the City Council District level. Census Tracts were assigned to Council Districts using the crosswalk found in the nyccensus data package: https://github.com/natalieoshea/nyccensus

The crosswalk did not have a matching council district for 45 NYC census tracts. They are parkland, cemeteries, large green spaces like golf courses, and airports. All have been manually matched and included in the data, with the exception of 3 tracts which's areas are entirely made up of water; these tracts have "N/A" in the "Council District" column. All of which can be found here at NYHC's Github:
 https://github.com/thenyhc/citycouncildistricthousingtracker/blob/main/Parkland%20and%20omitted%20census%20tracts

The final crosswalk used for the tracker can be found here: https://github.com/thenyhc/citycouncildistricthousingtracker/blob/main/master_crosswalk

Related data for every NYC census tract was pulled from the U.S. Census website. The tracker's statistics stem from estimates in the tables as follows:

##### 2020 Decennial Census Redistricting Data
Every decade the U. S. Census Bureau conducts a decennial census. These censuses attempt to count every person in the country and collect basic demographics like, age, sex, and race. The decennial census is the most accurate and geographically detailed way to understand who lives where. 
•	(Table P2)
o	Total Population*
o	Race
o	Density

##### 2015-2019 American Communities Survey (5-Year Estimates)
The American Community Survey (ACS) is the most comprehensive nationwide survey, bringing the gaps in the Decennial Census and providing much more detail. The monthly ACS surveys samples approximately 300,000 addresses. These are then released into includes both annual releases of survey data and "5-year roll-ups" of estimates ranging from demographic and financial information to household characteristics and employment. The tracker utilizes the 5-year estimates of the ACS.

•	(Table DP04)
o	Total Housing Units*
o	Rental and homeownership rate*
o	Units in structure (1, 2, 3-4 etc.)
o	Rent Burdened
•	(Table S1701)
o	Below Poverty*
o	65 and older*
o	Families with children under 18
•	(Table DS1101)
o	Renter-occupied*
o	Owner-occupied*
•	(Table DP03)
o	Unemployment Rate*
•	(Table B19025)
o	Median Household Income*
•	(Table B25004 and DP04)
o	Vacancy Rate*
Statistics without an asterisk (*) were aggregated as they were from the census site, while all others required calculation to develop.

##### Census Data Calculations

For Race, White, Black, and Asian are made up of those racial categories minus those with Hispanic ethnicity. The "Hispanic" categorization includes all individuals who responded with "Hispanic" as their ethnicity despite what race(s) respondents noted. "Other" includes the percentage left after accounting for these four groupings.
The Racial Diversity Index calculates the probability that two randomly chosen people in a given geographic area will be of a different race. NYHC used the categories listed above – Asian, Black, Hispanic, and white to calculate the index, excluding the category of other, which is the percentage that were not in one of those four groups. The index is calculated using the following formula: 1 – (Percent Asian2 + Percent Black2 + Percent Hispanic2 + Percent white2). 
A higher number indicates a more racially diverse population. If a Council district is inhabited by a single racial/ethnic group, its Racial Diversity Index would be zero while if the population is evenly distributed among the four groups (25% of residents are Asian, 25% are Black, 25% are Hispanic and 25% are white), its Racial Diversity Index would be 0.75. 
Density was calculated using the total land area converted from square feet to acres, divided by the total population. 

The vacancy rate was calculated using estimates for all unoccupied rental units (for rent and not for rent) divided by the sum of total of occupied rental units and unoccupied rental units.
The units-in-structure estimates are percentages of the sum total of the structure types listed and "mobile homes" and the "Boats, vans, etc." responses from the ACS.
Rent burden was calculated using the estimate of those respondents with a Gross Rent as a Percentage of Household Income (GRAPI) of 30-49 percent and 50 or more percent of total rental unit count (with vacant rental units subtracted).
Median Household Income was estimated using linear interpolation. The estimates are presented in inflation-adjusted 2021 dollars calculated using the U.S. Bureau of Labor and Statistics historic Consumer Price Index tables found here: https://www.bls.gov/regions/mid-atlantic/data/consumerpriceindexhistorical_us_table.htm

###### Households Entering DHS Shelters

This data shows the number of households whose last address was in the community board. We used the NYC Open Data set Associated Address by Borough and Community District. The data was not detailed enough to be calculated at the council district level so we included it by community board. The tracker displays the data for community boards that overlap with that council district.
 https://data.cityofnewyork.us/Social-Services/Associated-Address-by-Borough-and-Community-Distri/ur7y-ziyb 


###### Rent Regulated Units

Rent stabilized units courtesy of the Community Service Society of New York via the U.S. Census 2017 New York City Housing and Vacancy Survey.

###### Housing Code Violations Per 100 Units

Code violations come from NYC Open Data Housing Maintenance Code Violations dataset. We included only violations with an issue date (NOVIssueDate) in 2020 (1/1/2020 - 12/31/2020). We divided the number of violations in the district by the number of units in the district multiplied by 100. 
https://data.cityofnewyork.us/Housing-Development/Housing-Maintenance-Code-Violations/wvxf-dwi5 

###### New York Housing Authority (NYCHA) Data

Two data points in the tracker are sourced from NYCHA, detailing the level of need (capital construction work) and the total amount of housing run by NYCHA in each council district. 
Capital Needs
The Capital Need figure is an estimate of physical need provided by NYCHA to the New York Housing Conference. The estimate is based on the Physical Needs Assessment conducted by NYCHA surveying building conditions, including a comprehensive inspection of various building components and sub-components, which range from roofs to corridors to heating/cooling systems. The estimate excludes add-on for Lead-Based Paint Abatement, Asbestos Abatement, Pest & Waste Management, Electrification, as well as developments that have converted under the PACT Program. Physical Needs estimates for developments located in multiple districts are equally distributed across those districts.
Unit Count
The total NYCHA unit counts by council district are based off of the number of current units in the 2021 NYCHA Development Databook produced by NYCHA’s Performance Tracking and Analytics Department (PTAD); it includes data for all 285 developments in NYCHA’s public housing portfolio as of March 2021, however, the tracker includes only the 275 projects (167,083 units). The 10 excluded developments are FHA REPOSSESSED HOUSES Groups 1 through 10.
There are 6 developments that have units located in multiple council districts. These developments had a total of 4230 units that were divided into a council district based on the borough block lot (BBL) information for the development’s buildings listed on NYCHA’s Development Maps found here: https://www1.nyc.gov/site/nycha/about/developments.page
Per building unit counts were found by using NYC Department of City Planning’s New York City's Zoning & Land Use Map (ZOLA) and the PLUTO database. The “residential units” cited on ZOLA and PLUTO includes units not found in the “current units” provided in NYCHA’s data. This discrepancy impacts the counts for 4 of the developments with 3352 units combined. Instead of splitting the units evenly, the tracker shows an estimation based off the proportionate unit split in ZOLA, and therefore the margin of error for the council district NYCHA unit count for each is closer to 0 than it is to +/- the number of units in the development.

 

The 2021 NYCHA Development Databook can be found here: https://www1.nyc.gov/assets/nycha/downloads/pdf/pdb2021.pdf

Housing Choice Voucher (HCV) Program (formerly Section 8) Units

Section 8-unit counts use the US Department of Housing and Urban Development’s (HUD) Data Dictionary for Picture of Subsidized Households: 2021. The tracker uses Housing Choice Voucher total units defined as the “Number of units under contract for federal subsidy and available for occupancy” by HUD. Entries with values labeled as “missing” were omitted. The census tracts listed were matched using the tracker’s master crosswalk and unit counts were aggregated to the council district level.   
