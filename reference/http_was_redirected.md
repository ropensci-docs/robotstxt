# Check if HTTP redirect occurred

Check if HTTP redirect occurred

## Usage

``` r
http_was_redirected(response)
```

## Arguments

- response:

  an httr response object, e.g. from a call to httr::GET()

## Value

logical of length 1 indicating whether or not any redirect happened
during the HTTP request
