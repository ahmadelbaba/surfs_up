# surfs_up
## Overview and objective:
### W. Avy  wants more information about temperature trends before opening the surf shop. Specifically, he wants temperature data for the months of June and December in Oahu, in order to determine if the surf and ice cream shop business is sustainable year-round.

## Results

- On average June is ~4 degrees warmer than Decemnber 74.94 vs 71.04
- The minimum temperature in December (56) is 8 degrees cooler than the minimum in June (64)
- The maximum temperature in June (85) is only 2 degrees higher than the maximum temperature in December (83)

![June tmp](/Jun_temps.PNG)
![Dec tmp](/Dec_temps.PNG)

## Summary

### From the above analysis we can see than temperatures don't differ widely between June and December. That is a promising sign and a reason to be confident in our investment in a surfing and ice cream shop in Oahu.

A few other queries we could suggest: 

1) We can query June precepitation data

  ```
  June_prcp = session.query(Measurement).filter(extract('month', Measurement.date) == 6)
  June_prcp_list = [temp.prcp for temp in June_prcp]
  June_prcp_df = pd.DataFrame(June_prcp_list, columns=["June Prcp"])
  June_prcp_df.describe()
  ```
  
3) We can query December precepitation data

  ```
  Dec_prcp = session.query(Measurement).filter(extract('month', Measurement.date) == 12)
  Dec_prcp_list = [temp.prcp for temp in Dec_prcp]
  Dec_prcp_df = pd.DataFrame(Dec_prcp_list, columns=["December Prcp"])
  Dec_prcp_df.describe()
  ```
![June prcp](/Jun_prcp.PNG)
![Dec prcp](/Dec_prcp.PNG)

We can see that Dec has a bit more rain on the rainiest day (6.4 vs 4.4). December is slightly rainier on average (0.21 vs 0.13). The differences aren't significant to change our view about Oahu!
