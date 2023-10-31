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

The official source where to find holidays in Spain is the labour calendar approved each year and published on the Official State Bulletin or BOE - [Boletín Oficial del Estado](https://boe.es/). 

Holidays checked with official sources for 2010-2023 only.
 
References:
Calendario laboral: https://administracion.gob.es/pag_Home/atencionCiudadana/calendarios.html
This reference only include labour calendars from the previous 5 years

Calendario de días inhábiles: https://administracion.gob.es/pag_Home/atencionCiudadana/calendarios/diasInhabiles.html

BOE - Labour Calendar resolutions (2010-2024):
2010: https://www.boe.es/buscar/doc.php?id=BOE-A-2009-18477
2011: https://www.boe.es/buscar/doc.php?id=BOE-A-2010-15722
2012: https://www.boe.es/buscar/doc.php?id=BOE-A-2011-16116
2013: https://www.boe.es/buscar/doc.php?id=BOE-A-2012-13644
2014: https://www.boe.es/buscar/doc.php?id=BOE-A-2013-12147
2015: https://www.boe.es/buscar/doc.php?id=BOE-A-2014-10823
2016: https://www.boe.es/buscar/doc.php?id=BOE-A-2015-11348
2017: https://www.boe.es/buscar/doc.php?id=BOE-A-2016-9244
2018: https://www.boe.es/buscar/doc.php?id=BOE-A-2017-11639
2019: https://www.boe.es/buscar/doc.php?id=BOE-A-2018-14369
2020: https://www.boe.es/buscar/doc.php?id=BOE-A-2019-14552
2021: https://www.boe.es/buscar/doc.php?id=BOE-A-2020-13343
2022: https://www.boe.es/buscar/doc.php?id=BOE-A-2021-17113
2023: https://www.boe.es/buscar/doc.php?id=BOE-A-2022-16755
2024: https://www.boe.es/buscar/doc.php?id=BOE-A-2023-22014
