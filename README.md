# festivoR
An R package that helps you know whether a date is a bank holiday or a national holiday (festivo) in Spain

This package gathers inspiration for those who had solved this problem before, and likely better in Python. 
Particularly, from 
https://github.com/vacanza/python-holidays/tree/beta, and https://github.com/workalendar/workalendar. 

In addition, it explores the possibility of using the [Nager.Date](https://date.nager.at/PublicHoliday/Spain) public API to get holidays both in Spain, and in their Autonomous Communities (Regions). 

[Nager.Date GitHub repository](https://github.com/nager/Nager.Date)
[Nager.Date public API](https://date.nager.at/Api)
[Nager.Date public API documentation](https://date.nager.at/swagger/index.html)

Example of a query to the Nager.Date public API for holidays in Spain in the year 2000. 
https://date.nager.at/api/v2/publicholidays/2000/ES.


```
library(jsonlite)

df <- fromJSON(txt = "https://date.nager.at/api/v2/publicholidays/2000/ES")
# Gets all holidays from year 2000 in Spain

colnames(df)
# [1] "date"        "localName"   "name"        "countryCode" "fixed"       "global"     
# [7] "counties"    "launchYear"  "type"  

# "date" <chr>, "localName" <chr>, "name" <chr>, "countryCode" <chr>, 
# "fixed" <lgl>, "global" <lgl>, "counties" <list>, "launchYear" <int>, 
# "type" <chr>



```
