# Handle robotstxt handlers

Helper function to handle robotstxt handlers.

## Usage

``` r
request_handler_handler(request, handler, res, info = TRUE, warn = TRUE)
```

## Arguments

- request:

  the request object returned by call to httr::GET()

- handler:

  the handler either a character string entailing various options or a
  function producing a specific list, see return.

- res:

  a list with elements '\[handler names\], ...', 'rtxt', and 'cache'

- info:

  info to add to problems list

- warn:

  if FALSE warnings and messages are suppressed

## Value

a list with elements '\[handler name\]', 'rtxt', and 'cache'
