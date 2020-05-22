## NYC Zipcode Profitability Analysis
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

#### V. Analytical Approach

Refer to the [R notebook](https://meenal-narsinghani.github.io/Zipcode-Profitability-Analysis/Narsinghani.Meenal_DataChallenge_Code.html) to know more about the problem statement, data sources, approach used, findings and insights derived and final recommendations made.


#### VI. Conclusion

Considering all the factors analyzed above, we will select the zipcodes that satisfy maximum number of conditions.

Here is the final list of zipcodes that should be considered for investment -

* Zipcode 11201(Brooklyn) satifies all the criteria and is our best bet
* Zipcodes 10011(Manhattan), 10036(Manhattan), 10023(Manhattan) are the profitable, popular zipcodes. Even though they have high cost of investment, the higher Price/Night value compensates for it and makes these zipcodes profitable
* Zipcode 11434(Queens) looks promising and is highly recommended considering the increasing popularity of the zipcode. A couple of new properties that have come up recently in this area have been well recieved by the guests. Even though a nigh stay is charged less, it is still profitable

#### VII. Next Steps

  1. **Additional data procurement**
    i. Including more zipcodes into analysis
       We have AirBnb Listing data for 166 zipcodes(with information on 2BR properties available). However, due to non-availability of the Zillow Cost data, we were able to carried out analysis for only 24 zipcodes (that is only about 15% of zipcodes). Procurement of this data could help make better recommendations about the profitable zipcodes across New York City
    ii. Better approach to estimating revenue figures
        The 2 approaches used here to estimate the revenue/year/listing have their onw shortcomings.
        Taking 75% occupancy for all properties across all zipcodes overestimates the revenue (since less popular zipcodes may not have 75% occupancy throughout a year)
        Taking number of reviews as an approximation for the number of bookings mades underestimates the revenue (as not all guests will write a review)
        If we could obtain the booking information for the listings, estimation of revenue could be more accurate. OR Consider creating a model that will help in predicting the occupancy rate based on key influential factors.

  2. **Better outlier treatment for price**
  
   Considering the nature and scope of this analysis, we have considered any price/night figure 3 standard deviations above mean as an outlier, this may have caused dropping of luxurious properties.
   Price depends multiple factors like - property type, room type, amenetities, etc. While deciding if a price/night value for a listing is a data recording error or not, we need t consider all such factors.
    A model that clusters similar properties together based on these price-influencing factors and provide us an estimate of a resonable price for such properties, then we will be able to identify erroneous price information.

  3. **Customer Review and Review Scores analysis**
    Currently, we have considered only number of reviews as a metric to identify popular zipcodes. Analysis of customer reviews and making use of review scores can be included to select favorable zipcodes

  4. **Property Cost prediction**
    We have used the maximum cost observed in last 5 years as the cost estimate for year 2019. However, we can build a time-series model to better predict cost for coming years
