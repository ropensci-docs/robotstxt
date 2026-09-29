# Check if a bot has permissions to access page(s)

Check if a bot has permissions to access page(s)

## Usage

``` r
paths_allowed(
  paths = "/",
  domain = "auto",
  bot = "*",
  user_agent = utils::sessionInfo()$R.version$version.string,
  check_method = c("spiderbar"),
  warn = getOption("robotstxt_warn", TRUE),
  force = FALSE,
  ssl_verifypeer = c(1, 0),
  use_futures = TRUE,
  robotstxt_list = NULL,
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

- paths:

  paths for which to check bot's permission, defaults to "/". Please
  note that path to a folder should end with a trailing slash ("/").

- domain:

  Domain for which paths should be checked. Defaults to "auto". If set
  to "auto" function will try to guess the domain by parsing the paths
  argument. Note however, that these are educated guesses which might
  utterly fail. To be on the safe side, provide appropriate domains
  manually.

- bot:

  name of the bot, defaults to "\*"

- user_agent:

  HTTP user-agent string to be used to retrieve robots.txt file from
  domain

- check_method:

  at the moment only kept for backward compatibility reasons - do not
  use parameter anymore –\> will let the function simply use the default

- warn:

  suppress warnings

- force:

  if TRUE instead of using possible cached results the function will
  re-download the robotstxt file HTTP response status 404. If this
  happens,

- ssl_verifypeer:

  either 1 (default) or 0, if 0 it disables SSL peer verification, which
  might help with robots.txt file retrieval

- use_futures:

  Should future::future_lapply be used for possible parallel/async
  retrieval or not. Note: check out help pages and vignettes of package
  future on how to set up plans for future execution because the
  robotstxt package does not do it on its own.

- robotstxt_list:

  either NULL – the default – or a list of character vectors with one
  vector per path to check

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
