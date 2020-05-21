## NY Zipcode Profitability Analysis
**Analyzing the AirBnB revenue and Zillow cost datasets to identify favorable zip codes to invest in**

#### I. Problem Description

Our client is a real estate company that has a niche in purchasing properties to rent out short-term as part of their business model specifically within New York City.

The client has already concluded that two bedroom properties are the most profitable. However, they want to identify the zip codes are the best to invest in.

#### II. Objective
The objective of this analysis is to build a data product that assists the client in identifying the zipcodes that are favorable and will generate the most profit on short term rentals within New York City.

#### III. Assumptions
The following assumptions have been made while implementing this data model -

* The investor will pay for the property in cash (i.e. no mortgage/interest rate will need to be accounted for).
* The time value of money discount rate is 0% (i.e. $1 today is worth the same 100 years from now).
* All properties and all square feet within each locale can be assumed to be homogeneous (i.e. a 1000 square foot property in a locale such as Bronx or Manhattan generates twice the revenue and costs twice as much as any other 500 square foot property within that same locale.)
* Number of reviews have been used to estimate revenue figures. We assume that number of reviews that a property has recieved reflects the number of bookings that have been made. This, however is more conservative appraoch to estimating revenue.
* In this analysis, we make a comparison between revenue estimated based one number of reviews vs assuming all properties observe a 75% occupancy in a year.
* Considering the increasing Cost trend over last 5 years, we use maximum value of cost observed in last 5 years as an estimate of cost of year 2019

#### IV. Datasets used

We have used 2 datasets in our analysis -

  1. AirBnb Listings data for New York City - Contains information, such as location, host information, number of bedrooms, reviews recieved, etc.,about listings in New York City _http://data.insideairbnb.com/united-states/ny/new-york-city/2019-07-08/data/listings.csv.gz_

  2. Zillow Property Cost data - Contains selling cost of 2 bedroom properties in each zipcode for various cities. The cost information is available from April 1996 to June 2017. _https://www.zillow.com/research/data/_

Refer to the [R notebook](https://meenal-narsinghani.github.io/Zipcode-Profitability-Analysis/Narsinghani.Meenal_DataChallenge_Code.html) to know more about the problem statement, data sources, approach used, findings and insights derived and final recommendations made.
