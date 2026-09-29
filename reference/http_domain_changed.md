# Check if HTTP domain changed

Check if HTTP domain changed

## Usage

``` r
http_domain_changed(response)
```

## Arguments

- response:

  an httr response object, e.g. from a call to httr::GET()

## Value

logical of length 1 indicating whether or not any domain change happened
during the HTTP request
