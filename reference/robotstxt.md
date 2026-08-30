# Generate a representation of a robots.txt file

The function generates a list that entails data resulting from parsing a
robots.txt file as well as a function called check that enables to ask
the representation if bot (or particular bots) are allowed to access a
resource on the domain.

## Usage

``` r
robotstxt(
  domain = NULL,
  text = NULL,
  user_agent = NULL,
  warn = getOption("robotstxt_warn", TRUE),
  force = FALSE,
  ssl_verifypeer = c(1, 0),
  encoding = "UTF-8",
  verbose = FALSE,
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

  Domain for which to generate a representation. If text equals to NULL,
  the function will download the file from server - the default.

- text:

  If automatic download of the robots.txt is not preferred, the text can
  be supplied directly.

- user_agent:

  HTTP user-agent string to be used to retrieve robots.txt file from
  domain

- warn:

  warn about being unable to download domain/robots.txt because of

- force:

  if TRUE instead of using possible cached results the function will
  re-download the robotstxt file HTTP response status 404. If this
  happens,

- ssl_verifypeer:

  either 1 (default) or 0, if 0 it disables SSL peer verification, which
  might help with robots.txt file retrieval

- encoding:

  Encoding of the robots.txt file.

- verbose:

  make function print out more information

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

## Value

Object (list) of class robotstxt with parsed data from a robots.txt
(domain, text, bots, permissions, host, sitemap, other) and one function
to (check()) to check resource permissions.

## Fields

- `domain`:

  character vector holding domain name for which the robots.txt file is
  valid; will be set to NA if not supplied on initialization

- `character`:

  vector of text of robots.txt file; either supplied on initialization
  or automatically downloaded from domain supplied on initialization

- `bots`:

  character vector of bot names mentioned in robots.txt

- `permissions`:

  data.frame of bot permissions found in robots.txt file

- `host`:

  data.frame of host fields found in robots.txt file

- `sitemap`:

  data.frame of sitemap fields found in robots.txt file

- `other`:

  data.frame of other - none of the above - fields found in robots.txt
  file

- `check()`:

  Method to check for bot permissions. Defaults to the domains root and
  no bot in particular. check() has two arguments: paths and bot. The
  first is for supplying the paths for which to check permissions and
  the latter to put in the name of the bot. Please, note that path to a
  folder should end with a trailing slash ("/").

## Examples

``` r
if (FALSE) { # \dontrun{
rt <- robotstxt(domain="google.com")
rt$bots
rt$permissions
rt$check( paths = c("/", "forbidden"), bot="*")
} # }
```
