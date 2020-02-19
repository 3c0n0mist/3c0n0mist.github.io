---
layout: post
title:  "The Quest for Ramen"
date:   2020-02-18 23:57:11 PST 2020
categories: discussion
---

I have been visiting three great ramen spots in Vancouver for the past three years, its time i find another great spot.
I decided to avoid searching on google, as those restaurants are likely to be crowded.

My Accounting professor often used to say. It is typical for a business to get its first profit after five years in operation, 
suggesting the first five years a firm is at its incumbent stage and its too early to judge if its a successful model.

Building of that intuition, i thought a great ramen place is likely to be the one with a great history. Hence i procured the Vancouver City's Open 
Database and analysed the Business Permits dataset.

I looked for restaurants whose name includes 'Ramen', and have issued a business permit in the year 2012.

The results are as follows
* "Benke Ramen"
* "Benkei Ramen Noodle Shop"
* "Kintaro Ramen Noodle"
* "Hokkaido Ramen Santouka"
* "Ikkyu Ramen Ten"
* "Hida Takaya Ramen"
* "Sapporo Ramen Shogun Restaurant"
* "Ramen Jinya Japanese Noodle Bar"

## Future
I like to work on this further, possibly using exogenous data such as reviews and proximity to the user. To determine if the restaurant is a good pick.

After developing this model, i would like to implement similar models in other cuisines such as Italian Pasta. Then combine them into an Application that recommends restaurant picks without taking into account advertising fees paid to google. 

```Command
# downloading the dataset in the JSON format
curl https://opendata.vancouver.ca/api/records/1.0/search/\?dataset\=business-licences-1997-to-2012\&q\=%27Ramen%27\&rows\=145\&facet\=folderyear\&facet\=licencerevisionnumber\&facet\=status\&facet\=issueddate\&facet\=businesstype\&facet\=businesssubtype\&facet\=city\&facet\=province\&facet\=localarea\&refine.city\=Vancouver\&refine.folderyear\=12\&exclude.businesstype\=Wholesale+Dealer --output ramen_df.json

# filtering the json object, to return the names of the restaurants
cat ramen_df.json| jq '.records[] | .fields.businesstradename' 
```

  
