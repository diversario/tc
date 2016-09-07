I have to look at date string a lot at work so I wrote this tool to output most useful (for me) conversions.

## Usage

`tc` takes as input:

* epoch timestamps (ms)
* second timestamps – converted to epoch
* Javascript `Date#toString` and `Date#toISOString` output
* `tc` output (not multiline though)
* mysql dates like `2016-09-05 00:10:33`

Anything else is simply passed to `new Date` in hopes it'll work somehow.

## Options

`tc` has one option:

`-t [est|pst|mst|utc]` Timezone to use _**for the input string**_. Used **only** when MySQL date is detected and defaults to EST (New York).

## License

MIT, you know what to do.
