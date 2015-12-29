---
title       : Store 101 monthly sales study
subtitle    : From 2013-8 to 2015-7
author      : luxiaoguang_leon@hotmail.com
job         : data science
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
ext_widgets : {rCharts: [libraries/nvd3]}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Getting Data


```
## [1] 5
```

```
## [1] "bnh_basks"     "bnh_customers" "bnh_items"     "bnh_products" 
## [5] "bnh_stores"
```

```
##  [1] "bask_id"                "bask_code"             
##  [3] "cust_id"                "cust_code"             
##  [5] "store_id"               "store_code"            
##  [7] "shop_datetime"          "original_shop_datetime"
##  [9] "bask_spend"             "bask_quantity"         
## [11] "payment_type"           "bask_discount"
```

```
##   count(*)
## 1  1426701
```

```
## [1] TRUE
```



--- .class #id 

## Cleaning Data

```
##             bask_code cust_code store_code       shop_datetime bask_spend
## 1419783 1507316130167                  101 2015-07-31 21:08:56         20
## 1419784 1507316130168                  101 2015-07-31 21:13:11         70
## 1419785 1507316130169                  101 2015-07-31 21:13:55         70
## 1419786 1507316130170                  101 2015-07-31 21:15:34        700
## 1419787 1507316130171                  101 2015-07-31 21:21:59         45
## 1419788 1507316130172                  101 2015-07-31 21:32:01        180
##         bask_quantity
## 1419783             1
## 1419784             1
## 1419785             1
## 1419786             1
## 1419787             1
## 1419788             4
```



---.




## Sales Study

<div id = 'chart76c1f5d2e95' class = 'rChart nvd3'></div>
<script type='text/javascript'>
 $(document).ready(function(){
      drawchart76c1f5d2e95()
    });
    function drawchart76c1f5d2e95(){  
      var opts = {
 "dom": "chart76c1f5d2e95",
"width":    800,
"height":    500,
"x": "shop_month",
"y": "sales",
"group": "shop_year",
"type": "multiBarChart",
"id": "chart76c1f5d2e95" 
},
        data = [
 {
 "shop_month": "08",
"sales":      3246302.3,
"quantity": 441204,
"shop_year": "2013" 
},
{
 "shop_month": "09",
"sales":      3309174.8,
"quantity": 347562,
"shop_year": "2013" 
},
{
 "shop_month": "10",
"sales":      3008963.9,
"quantity": 350632,
"shop_year": "2013" 
},
{
 "shop_month": "11",
"sales":      3376325.1,
"quantity": 363357,
"shop_year": "2013" 
},
{
 "shop_month": "12",
"sales":      3788780.6,
"quantity": 396232,
"shop_year": "2013" 
},
{
 "shop_month": "01",
"sales":      6242834.4,
"quantity": 488831,
"shop_year": "2014" 
},
{
 "shop_month": "02",
"sales":      2919832.6,
"quantity": 241441,
"shop_year": "2014" 
},
{
 "shop_month": "03",
"sales":      2886591.6,
"quantity": 297673,
"shop_year": "2014" 
},
{
 "shop_month": "04",
"sales":      3138537.4,
"quantity": 340070,
"shop_year": "2014" 
},
{
 "shop_month": "05",
"sales":        2945621,
"quantity": 331443,
"shop_year": "2014" 
},
{
 "shop_month": "06",
"sales":      2913301.6,
"quantity": 346379,
"shop_year": "2014" 
},
{
 "shop_month": "07",
"sales":      3254760.6,
"quantity": 399918,
"shop_year": "2014" 
},
{
 "shop_month": "08",
"sales":      3547200.5,
"quantity": 399844,
"shop_year": "2014" 
},
{
 "shop_month": "09",
"sales":      3091427.6,
"quantity": 315283,
"shop_year": "2014" 
},
{
 "shop_month": "10",
"sales":      3017532.1,
"quantity": 335358,
"shop_year": "2014" 
},
{
 "shop_month": "11",
"sales":      3196507.8,
"quantity": 330898,
"shop_year": "2014" 
},
{
 "shop_month": "12",
"sales":      4133623.1,
"quantity": 379164,
"shop_year": "2014" 
},
{
 "shop_month": "01",
"sales":     15423855.2,
"quantity": 354198,
"shop_year": "2015" 
},
{
 "shop_month": "02",
"sales":      5729655.7,
"quantity": 411146,
"shop_year": "2015" 
},
{
 "shop_month": "03",
"sales":      2323956.9,
"quantity": 221408,
"shop_year": "2015" 
},
{
 "shop_month": "04",
"sales":      2534820.7,
"quantity": 273003,
"shop_year": "2015" 
},
{
 "shop_month": "05",
"sales":      2293598.5,
"quantity": 244494,
"shop_year": "2015" 
},
{
 "shop_month": "06",
"sales":      2445570.2,
"quantity": 272743,
"shop_year": "2015" 
},
{
 "shop_month": "07",
"sales":      3011401.3,
"quantity": 343574,
"shop_year": "2015" 
} 
]
  
      if(!(opts.type==="pieChart" || opts.type==="sparklinePlus" || opts.type==="bulletChart")) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? 'main' : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .width(opts.width)
          .height(opts.height)
          
        if (opts.type != "bulletChart"){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        
          
        

        
        
        
      
       d3.select("#" + opts.id)
        .append('svg')
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
</script>


---.



## Sales Study

<div id = 'chart76c2773254e' class = 'rChart nvd3'></div>
<script type='text/javascript'>
 $(document).ready(function(){
      drawchart76c2773254e()
    });
    function drawchart76c2773254e(){  
      var opts = {
 "dom": "chart76c2773254e",
"width":    800,
"height":    500,
"x": "shop_month",
"y": "quantity",
"group": "shop_year",
"type": "multiBarChart",
"id": "chart76c2773254e" 
},
        data = [
 {
 "shop_month": "08",
"sales":      3246302.3,
"quantity": 441204,
"shop_year": "2013" 
},
{
 "shop_month": "09",
"sales":      3309174.8,
"quantity": 347562,
"shop_year": "2013" 
},
{
 "shop_month": "10",
"sales":      3008963.9,
"quantity": 350632,
"shop_year": "2013" 
},
{
 "shop_month": "11",
"sales":      3376325.1,
"quantity": 363357,
"shop_year": "2013" 
},
{
 "shop_month": "12",
"sales":      3788780.6,
"quantity": 396232,
"shop_year": "2013" 
},
{
 "shop_month": "01",
"sales":      6242834.4,
"quantity": 488831,
"shop_year": "2014" 
},
{
 "shop_month": "02",
"sales":      2919832.6,
"quantity": 241441,
"shop_year": "2014" 
},
{
 "shop_month": "03",
"sales":      2886591.6,
"quantity": 297673,
"shop_year": "2014" 
},
{
 "shop_month": "04",
"sales":      3138537.4,
"quantity": 340070,
"shop_year": "2014" 
},
{
 "shop_month": "05",
"sales":        2945621,
"quantity": 331443,
"shop_year": "2014" 
},
{
 "shop_month": "06",
"sales":      2913301.6,
"quantity": 346379,
"shop_year": "2014" 
},
{
 "shop_month": "07",
"sales":      3254760.6,
"quantity": 399918,
"shop_year": "2014" 
},
{
 "shop_month": "08",
"sales":      3547200.5,
"quantity": 399844,
"shop_year": "2014" 
},
{
 "shop_month": "09",
"sales":      3091427.6,
"quantity": 315283,
"shop_year": "2014" 
},
{
 "shop_month": "10",
"sales":      3017532.1,
"quantity": 335358,
"shop_year": "2014" 
},
{
 "shop_month": "11",
"sales":      3196507.8,
"quantity": 330898,
"shop_year": "2014" 
},
{
 "shop_month": "12",
"sales":      4133623.1,
"quantity": 379164,
"shop_year": "2014" 
},
{
 "shop_month": "01",
"sales":     15423855.2,
"quantity": 354198,
"shop_year": "2015" 
},
{
 "shop_month": "02",
"sales":      5729655.7,
"quantity": 411146,
"shop_year": "2015" 
},
{
 "shop_month": "03",
"sales":      2323956.9,
"quantity": 221408,
"shop_year": "2015" 
},
{
 "shop_month": "04",
"sales":      2534820.7,
"quantity": 273003,
"shop_year": "2015" 
},
{
 "shop_month": "05",
"sales":      2293598.5,
"quantity": 244494,
"shop_year": "2015" 
},
{
 "shop_month": "06",
"sales":      2445570.2,
"quantity": 272743,
"shop_year": "2015" 
},
{
 "shop_month": "07",
"sales":      3011401.3,
"quantity": 343574,
"shop_year": "2015" 
} 
]
  
      if(!(opts.type==="pieChart" || opts.type==="sparklinePlus" || opts.type==="bulletChart")) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? 'main' : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .width(opts.width)
          .height(opts.height)
          
        if (opts.type != "bulletChart"){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        
          
        

        
        
        
      
       d3.select("#" + opts.id)
        .append('svg')
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
</script>




