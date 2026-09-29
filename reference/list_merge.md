# Merge a number of named lists in sequential order

Merge a number of named lists in sequential order

## Usage

``` r
list_merge(...)
```

## Arguments

- ...:

  named lists

## Details

List merging is usually useful in the merging of program settings or
configuraion with multiple versions across time, or multiple
administrative levels. For example, a program settings may have an
initial version in which most keys are defined and specified. In later
versions, partial modifications are recorded. In this case, list merging
can be useful to merge all versions of settings in release order of
these versions. The result is an fully updated settings with all later
modifications applied.

## Author

Kun Ren \<mail@renkun.me\>

The function merges a number of lists in sequential order by
`modifyList`, that is, the later list always modifies the former list
and form a merged list, and the resulted list is again being merged with
the next list. The process is repeated until all lists in `...` or
`list` are exausted.
