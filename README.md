# data-512-homework_1-

## Goal
The goal of this project is to learn how to utilize API calls, develop a good reproducibility framework, and create a polished, usuable repository. On a more detailed level, learning how to use Wikipedia, plotting tools like matplotlib, and helper functions are also goals of this project. Finally, the prompt of this homework revolves around visualizing the page views for diseases from July 2015 to September 2024.

## License

The license to the source data is the Wikimedia Foundation Terms of Use: https://foundation.wikimedia.org/wiki/Policy:Terms_of_Use
The ToU is applicable to this project since we are using a free and open license and the results cause no harm to anyone.

The API documentation is linked here: https://doc.wikimedia.org/generated-data-platform/aqs/analytics-api/reference/page-views.html

I also used sample code from Dr. David McDonald which is licensed through CC-BY, linked here: https://creativecommons.org/licenses/by/4.0/
## Data produced

My notebook creates two intermediary data files (found in the results folder):
1. results/rare-disease_monthly_mobile-app_201507-202409.json
2. results/rare-disease_monthly_mobile-web_201507-202409.json
Both files above are used to create the combined "mobile" json file (rare-disease_monthly_mobile_201507-202409.json) which combines the page views from the two intermediary files

My notebook creates three final output files (found in the results folder):

1. results/rare-disease_monthly_mobile_201507-202409.json
2. results/rare-disease_monthly_desktop_201507-202409.json
3. results/rare-disease_monthly_cumulative_201507-202409.json

The data schema for all json files is:

```python
{
    "Article title": [
        {
            "project": "en.wikipedia",
            "article": "Article title",
            "granularity": "monthly",
            "timestamp": string,
            "agent": "user",
            "views": integer
        },
        ...
    ]
}
```

The overall structure of each json file is a dictionary. At the top level, each key is a different disease and the values are a list of timestamps. One is shown above.

Each Article title is a different disease (eg. Klinefelter Syndrome). The timestamps are given in the format "YYYYMMDDSS" and the views are an integer.

## Known issues

Some diseases have been added more recently than July 2015. A few of these are noted in the plots, but that is not a comprehensive list. Use caution when comparing page views that you account for this disparity. 
