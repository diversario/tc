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

## Sample output
```shell
➜  tc 2016-09-05 00:13:39
Input string processed with timezone America/New_York

UTC: Mon Sep 05 2016 04:13:39 GMT+0000
EST: Mon Sep 05 2016 00:13:39 GMT-0400
MST: Sun Sep 04 2016 22:13:39 GMT-0600
PST: Sun Sep 04 2016 21:13:39 GMT-0700

➜  tc 2016-09-05 00:13:39 -t utc
UTC: Mon Sep 05 2016 00:13:39 GMT+0000
EST: Sun Sep 04 2016 20:13:39 GMT-0400
MST: Sun Sep 04 2016 18:13:39 GMT-0600
PST: Sun Sep 04 2016 17:13:39 GMT-0700

➜ tc Tue Sep 06 2016 22:53:39 GMT-0700 (PDT)
UTC: Wed Sep 07 2016 05:53:39 GMT+0000
EST: Wed Sep 07 2016 01:53:39 GMT-0400
MST: Tue Sep 06 2016 23:53:39 GMT-0600
PST: Tue Sep 06 2016 22:53:39 GMT-0700

➜ tc 2016-09-07T05:53:51.865Z
UTC: Wed Sep 07 2016 05:53:51 GMT+0000
EST: Wed Sep 07 2016 01:53:51 GMT-0400
MST: Tue Sep 06 2016 23:53:51 GMT-0600
PST: Tue Sep 06 2016 22:53:51 GMT-0700
```

## License

MIT, you know what to do.
