# Handle robotstxt object retrieved from HTTP request

A helper function for get_robotstxt() that will extract the robots.txt
file from the HTTP request result object. It will inform get_robotstxt()
if the request should be cached and which problems occurred.

## Usage

``` r
rt_request_handler(
  request,
  on_server_error = on_server_error_default,
  on_client_error = on_client_error_default,
  on_not_found = on_not_found_default,
  on_redirect = on_redirect_default,
  on_domain_change = on_domain_change_default,
  on_sub_domain_change = on_sub_domain_change_default,
  on_file_type_mismatch = on_file_type_mismatch_default,
  on_suspect_content = on_suspect_content_default,
  warn = TRUE,
  encoding = "UTF-8"
)

on_server_error_default

on_client_error_default

on_not_found_default

on_redirect_default

on_domain_change_default

on_sub_domain_change_default

on_file_type_mismatch_default

on_suspect_content_default
```

## Format

An object of class `list` of length 4.

An object of class `list` of length 4.

An object of class `list` of length 4.

An object of class `list` of length 2.

An object of class `list` of length 3.

An object of class `list` of length 2.

An object of class `list` of length 4.

An object of class `list` of length 4.

## Arguments

- request:

  result of an HTTP request (e.g. httr::GET())

- on_server_error:

  request state handler for any 5xx status

- on_client_error:

  request state handler for any 4xx HTTP status that is not 404

- on_not_found:

  request state handler for HTTP status 404

- on_redirect:

  request state handler for any 3xx HTTP status

- on_domain_change:

  request state handler for any 3xx HTTP status where domain did change
  as well

- on_sub_domain_change:

  request state handler for any 3xx HTTP status where domain did change
  but only to www-sub_domain

- on_file_type_mismatch:

  request state handler for content type other than 'text/plain'

- on_suspect_content:

  request state handler for content that seems to be something else than
  a robots.txt file (usually a JSON, XML or HTML)

- warn:

  suppress warnings

- encoding:

  The text encoding to assume if no encoding is provided in the headers
  of the response

## Value

a list with three items following the following schema:  
` list( rtxt = "", problems = list( "redirect" = list( status_code = 301 ), "domain" = list(from_url = "...", to_url = "...") ) ) `
