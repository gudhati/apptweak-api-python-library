
# informations
Allow to access the apptweak-io api easily.

## Github
https://github.com/apptweak/apptweak-api-python-library

## Required
You will need an api_key from 
https://www.apptweak.io/

## install
`pip install apptweak --user`

## use
 ```python
import apptweak

# your apptweak-io API key
apptweak.API_KEY = "XYZ"

# the id of your app (ios or android)
app_id = "686449807"

# print(device.end-point.__doc__) tells me whitch arguments and params the method needs
end_point_documentation = apptweak.Ios.power.__doc__

# depending on your app id (params specific to the device.end-point)
params={"country":"us","start_date":"2018-10-03","end_date":"2018-10-10","device":"iphone"}

# depending on your app id (if ios app_id choose the ios end-points)
json_response = apptweak.Ios.power(app_id,params)
 ```

## end-points
### all params
```python
application_id = "1234" # ios or android app_id

sort = "most_useful" # (most_useful | most_recent | most_critical | most_positive)

category_id = "4" # ios or android category id

params={
    "country":"be", # ISO Alpha-2
    "language":"be", # ISO Alpha-2
    "device":"iphone" # (iphone | ipad)
    "start_date":"2019-01-04", # YYYY-MM-DD
    "end_date":"2019-05-24", # YYYY-MM-DD
    "max-age":"96040", # integer in seconds >0
    "min_rating":"1", # integer >= 1 && <= 5
    "max_rating":"5", # integer >= 1 && <= 5
    "term":"game", # string (the term of the search)
    "from":"42", # integer > 0 (like an offset)
    "type":"free", # (free | paid | grossing)
    "num":"3", # integer > 0 ( number of result)
    "size":"40", # integer > 0 (size of the result)
    "keywords":["games","fun",], # list of string, max 10
    "applications":["1234","4567",] # list of app_ids
}
```
To use the following end point
```python
apptweak.Ios.title_of_end-point(options,params_dict)
or
apptweak.Android.title_of_end-point(options,params_dict)
```
!! Some params, options or end-points are specific to Ios or Android !!
### metadata
- application_id
- params
  - country
  - language
  - device ( IOS ! )
  - max-age
### ratings
- application_id
- params
  - country ( IOS ! )
  - start_date
  - end_date
### rankings
- application_id
- params
  - country ( IOS ! )
  - device ( IOS ! )
  - start_date
  - end_date

### power
- application_id
- params
  - country
  - device ( IOS ! )
  - start_date
  - end_date
### backlinks ( Android ! )
- application_id

### donwloads
- application_id
- params
  - country ( IOS ! )
  - device ( IOS ! )
  - start_date
  - end_date
### revenues ( Ios ! )
- application_id
- params
  - country
  - device
  - start_date
  - end_date
### reviews ( Ios ! )
- application_id
- params
  - country
### searches
- application_id
- params
  - country
  - language
  - device ( Ios ! )
  - term
  - num
### top_charts
- application_id
- category_id
- params
  - country
  - language
  - device ( Ios ! )
  - type
  - term
### top_displayed_reviews
- application_id
- sort_type
- params
  - country
  - size 
### filtered_reviews
- application_id
- params
  - min_rating
  - max_rating
  - start_date
  - end_date
  - term
  - from
  - size 
### reviews_stats
- application_id
- params
  - min_rating
  - max_rating
  - start_date
  - end_date
  - term
### app_top_keywords
- application_id
- params
  - country
  - language
  - device ( Ios ! )
### keywords_stats
- application_id
- params
  - country
  - language
  - keywords
  - device ( Ios ! )
### keywords_competitiors
- application_id
- params
  - country
  - language
  - device ( Ios ! )
### keywords_ranking_competitors
- application_id
- params
  - country
  - language
  - start_date
  - end_date
  - keywords
  - applications
  - device ( Ios ! )
### category_top_keywords
- application_id
- category_id
- params
  - country
  - language
  - type
  - device ( Ios ! )
### keywords_trending  ( Ios ! )
- application_id
- params
  - country
  - language
  - device
### keywords_volume_history ( Ios ! )
- application_id
- params
  - country
  - language
  - start_date
  - end_date
  - type

