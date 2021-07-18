# Surfs Up
## Overview of the statistical analysis:

This analysis was to better understand the weather of the island and see how it would effect business for a surf shop that also happens to sell ice cream.

## Results:
It seems in the island, the temps don't shift drastically. Both months average just above 70 degrees giving the perfect weather to be at the beach. While in June it can drop to 64 which is not too bad, December still tends to stay close to the 70 degree area with the lowest temp being a 69. December also historically tends to be a high busy season for travelers either way.

|June|temps|
|----|-----|
|count|1700.000000|
|mean|74.944118|
|std|3.257417|
|min|64.000000|
|25%|73.000000|
|50%|75.000000|
|75%|77.000000|
|max|85.000000|


|December|temps|
|--------|-------|
|count|1517.000000|
|mean|71.041529|
|std|3.745920|
|min|56.000000|
|25%|69.000000|
|50%|71.000000|
|75%|74.000000|
|max|83.000000|

## Summary:
Overall the two high seasonal months tend to keep consistent in temperature and do not seem to stray any more than 3-4 degrees in temp. To further investigate further, I believe two more queries should be run in order to be sure that the island is the best place for the shop. It would be helpful to look into the precipitation and the number of stations reporting the weather.
- precipation
`precipitation = session.query(Measurement.date, Measurement.prcp).filter(Measurement.date >= prev_year).all()`
- and station
`session.query(Measurement.station, func.count(Measurement.station)).\
group_by(Measurement.station).order_by(func.count(Measurement.station).desc()).all()`
