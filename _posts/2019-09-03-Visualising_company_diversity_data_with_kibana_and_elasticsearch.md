---
layout: post
title: "Visualising Company Diversity Data with Kibana and Elasticsearch"
date: 2019-09-03
---


Kibana is an open source analytics and visualisation platform that works with elasticsearch. 
It's a great way of seeing the relationships that exist in your datasets.

## 1. How do you set up kibana and elasticsearch?
Setting up kibana and elasticsearch requires downloading both from [elastic.co](https://www.elastic.co/products/elastic-stack).  
Once you have done so, run the commands navigate to the folder from your command prompt / terminal and run the command ./bin/elasticsearch.bat
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
- to access kibana run: 127.0.0.1:5601 in the browser.

## 2. Source of data
Since I'm still learning and wanted to play around a little with kibana, I decided to use a dataset I was already familiar with: 
[Diversity in Tech](https://informationisbeautiful.net/visualizations/diversity-in-tech/). This is the same set we used in March 2019's
Boston TechTogether Hackathon to build a google chrome extension where you can visualise company diversity date. (You can download that
cool project [here](https://github.com/raphaelletseng/know_your_company)!) 
I reformatted it slightly to make it easier to work with and you can download that [here](https://github.com/raphaelletseng/hello-world/blob/master/employeediversity5.csv).
This dataset only contains 36 companies, which makes it a good starting point to play around with. It was also last updated in May 2018
which means it isn't completely outdated and still somewhat relevant. 

## 3. Visualising outcomes
This data can be simply be uploaded to Kibana using the Machine Learning > import data function of kibana.

-Percentage of Women in companies visualised in a TagCloud:
![Link](/assets/img/Percentage%20Female%20Tag%20Cloud.PNG)
This visualisation is useful to get a brief overview, but it lacks key information. A useful metric here is the tag 'US Population', which represents 51% women. From this, we can see that companies like Google, the US congress, Fortune 500 CEOs, Cisco and Microsoft all have incredibly male-dominated demographics. Yelp, on the otherhand, employs more women than men. However, a limitation of this dataset is that we cannot see the breakdown of departments; does Yelp hire an equal amount of female software engineers as male? Or do women dominate in fields such as HR? This is impossible to tell here.

5. Conclusions that can be drawn
6. Plug extension we made. 
