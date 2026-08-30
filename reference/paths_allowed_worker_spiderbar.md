# Check if a spiderbar bot has permissions to access page(s)

Check if a spiderbar bot has permissions to access page(s)

## Usage

``` r
paths_allowed_worker_spiderbar(domain, bot, paths, robotstxt_list)
```

## Arguments

- domain:

  Domain for which paths should be checked. Defaults to "auto". If set
  to "auto" function will try to guess the domain by parsing the paths
  argument. Note however, that these are educated guesses which might
  utterly fail. To be on the safe side, provide appropriate domains
  manually.

- bot:

  name of the bot, defaults to "\*"

- paths:

  paths for which to check bot's permission, defaults to "/". Please
  note that path to a folder should end with a trailing slash ("/").

- robotstxt_list:

  either NULL – the default – or a list of character vectors with one
  vector per path to check
