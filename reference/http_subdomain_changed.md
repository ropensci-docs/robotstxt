# Check if HTTP subdomain changed

Check if HTTP subdomain changed

## Usage

``` r
http_subdomain_changed(response)
```

## Arguments

- response:

  an httr response object, e.g. from a call to httr::GET()

## Value

logical of length 1 indicating whether or not any subdomain change
happened during the HTTP request
