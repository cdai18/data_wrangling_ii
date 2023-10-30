Reading Data from the Web
================
Christina Dai

## Scrape a table

I want the first table from this page

Read in the html

``` r
url = "https://samhda.s3-us-gov-west-1.amazonaws.com/s3fs-public/field-uploads/2k15StateFiles/NSDUHsaeShortTermCHG2015.htm"

drug_use_html = read_html(url)
```

Extract the table(s); focus on the first one

``` r
table_marj = 
  drug_use_html %>% 
    html_nodes(css = "table") %>% 
    html_table() %>% 
    first() %>% 
    slice(-1) %>% 
    as_tibble()
```
