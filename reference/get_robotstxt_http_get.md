# Storage for HTTP request response objects

Storage for HTTP request response objects

Execute HTTP request for get_robotstxt()

## Usage

``` r
rt_last_http

get_robotstxt_http_get(
  domain,
  user_agent = utils::sessionInfo()$R.version$version.string,
  ssl_verifypeer = 1
)
```

## Format

An object of class `environment` of length 1.

## Arguments

- domain:

  the domain to get robots.txt file for.

- user_agent:

  the user agent to use for HTTP request header. Defaults to current
  version of R. If \`NULL\` is passed, httr will use software versions
  for the header, such as \`libcurl/8.7.1 r-curl/5.2.3 httr/1.4.7\`

- ssl_verifypeer:

  either 1 (default) or 0, if 0 it disables SSL peer verification, which
  might help with robots.txt file retrieval
