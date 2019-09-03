---
layout: post
title: "Visualising Company Diversity Data with Kibana and Elasticsearch"
date: 2019-09-03
---


Kibana is an open source analytics and visualisation platform that works with elasticsearch. 
It's a great way of seeing the relationships that exist in your datasets. This is a short explanation of my first explorations with Kibana.

## 1. How do you set up kibana and elasticsearch?
Setting up kibana and elasticsearch requires downloading both from [elastic.co](https://www.elastic.co/products/elastic-stack).  
Once you have done so, navigate to the folder from your command prompt / terminal and run the commands: ./bin/elasticsearch.bat
and ./bin/kibana.bat. To check both elasticsearch and kibana are running:
- go to http://localhost:9200 and you should something along the lines of:
```
{
  "name" : "RAPHAELLE-PC",
  "cluster_name" : "elasticsearch",
  "version" : {
    "number" : "7.3.1",
    "build_flavor" : "default",
    "build_type" : "zip",
    "build_hash" : "4749ba6",
    "build_date" : "2019-08-19T20:19:25.651794Z",
    "build_snapshot" : false,
    "lucene_version" : "8.1.0",
    "minimum_wire_compatibility_version" : "6.8.0",
    "minimum_index_compatibility_version" : "6.0.0-beta1"
  },
  "tagline" : "You Know, for Search"
}
```
- to access kibana, run: 127.0.0.1:5601 in the browser.

## 2. Source of data
Since I'm still learning and wanted to play around a little with kibana, I decided to use a dataset I was already familiar with: 
[Diversity in Tech](https://informationisbeautiful.net/visualizations/diversity-in-tech/). This is the same set we used in March 2019's
Boston TechTogether Hackathon to build a google chrome extension where you can visualise company diversity data. (You can download that
cool project [here](https://github.com/raphaelletseng/know_your_company)!) 
I reformatted it slightly to make it easier to work with and you can download that [here](https://github.com/raphaelletseng/hello-world/blob/master/employeediversity5.csv).
This dataset only contains 36 companies, which makes it a good starting point to play around with. It was also last updated in May 2018
which means it isn't completely redundant and outdated. 
For the purposes of this visualisation, I am grouping the US Congress, Fortune 500 CEOs and the US population as companies. 

## 3. Visualising outcomes: Examples
This data can be simply be uploaded to Kibana using the Machine Learning > import data function of kibana.

### TagClouds
- Percentage of Women in companies:
![Link](/assets/img/Percentage%20Female%20Tag%20Cloud.PNG)
- Percentage of Asians in companies:
![Link](/assets/img/AsianTagCloud.PNG)
- Percentage of Latinos in companies:
![Link](/assets/img/LatinoTagCloud.PNG)
Tag clouds are useful visualisations to get brief overviews of data. A useful metric to get some idea of the scale in this data is 'US Population'. 'Average from our sample' may also be used to get an understanding of which companies higher particularly low numbers of certain groups and aren't particularly diverse. For example, 51% of the US population is made up of women. So companies like Google, the US Congress, Fortune 500 CEOs, Cisco and Microsoft all have incredibly male-dominated demographics. Yelp, on the otherhand, employs more women than men. TagClouds however, make it difficult to see specific information about certain groups and numbers. 

### Area Graphs
- Percentage of Black and Latino employees 
![Link](/assets/img/Black_Latino.PNG)
This graph looks at the companies with the highest percentage of black employees and splits the area beneath the graph with percentage of Latino employees per company. From this, we can see that Amazon's employees are made up of 21% black and 13% latino. On average, companies tend to have a higher %Latino than %Black employees. This isn't surprising given that the US population is made up of 13% Black and 18% Latino employees. The exceptions to this trend are Groupon and Linkedin, which have equal percentages of Black and Latino employees and Amazon, the US congress, Uber and Diversity Inc. top 50, which have more Black employees than Latino. 

### Bar Charts
- Gender
![Link](/assets/img/Gender2.PNG)
This graph displays percentage of male employees on the Y axis against percentage of female employees on the X axis for all the companies in the dataset. Out of 38 data points, only 2 have a majority of women: Etsy and Yelp, despite the US population being split 51% women and 49% men. Indiegogo is the only company with an even split of 50% men and 50% women. Perhaps the most disheartening statistic of all is the fact that 94% of Fortune 500 CEOs are men. 

- Kibana allows you to visualise data in several more manners including geomaps, heat maps, pie charts, etc. 

## Conclusions
I still have a lot to learn in Kibana but this was a cool way to start visualising some relevant information about diversity in tech companies, an area that I am particularly interested in given the impact it will have on my future. Although the results aren't super promising at the moment, it is by making data like this more accessible and visual that we can start making people more aware about the need for ethnic and gender diversity in the workspace. 
With regards to Kibana I'd like to try and explore using different types of data such as the geomaps, and diving into more complex relationships.
