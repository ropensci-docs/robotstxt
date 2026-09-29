# Download a robots.txt file

Download a robots.txt file

## Usage

``` r
get_robotstxt(
  domain,
  warn = getOption("robotstxt_warn", TRUE),
  force = FALSE,
  user_agent = utils::sessionInfo()$R.version$version.string,
  ssl_verifypeer = c(1, 0),
  encoding = "UTF-8",
  verbose = FALSE,
  rt_request_handler = robotstxt::rt_request_handler,
  rt_robotstxt_http_getter = robotstxt::get_robotstxt_http_get,
  on_server_error = on_server_error_default,
  on_client_error = on_client_error_default,
  on_not_found = on_not_found_default,
  on_redirect = on_redirect_default,
  on_domain_change = on_domain_change_default,
  on_file_type_mismatch = on_file_type_mismatch_default,
  on_suspect_content = on_suspect_content_default
)
```

## Arguments

- domain:

  domain from which to download robots.txt file

- warn:

  warn about being unable to download domain/robots.txt because of

- force:

  if TRUE instead of using possible cached results the function will
  re-download the robotstxt file HTTP response status 404. If this
  happens,

- user_agent:

  HTTP user-agent string to be used to retrieve robots.txt file from
  domain

- ssl_verifypeer:

  either 1 (default) or 0, if 0 it disables SSL peer verification, which
  might help with robots.txt file retrieval

- encoding:

  Encoding of the robots.txt file.

- verbose:

  make function print out more information

- rt_request_handler:

  handler function that handles request according to the event handlers
  specified

- rt_robotstxt_http_getter:

  function that executes HTTP request

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

- on_file_type_mismatch:

  request state handler for content type other than 'text/plain'

- on_suspect_content:

  request state handler for content that seems to be something else than
  a robots.txt file (usually a JSON, XML or HTML)
