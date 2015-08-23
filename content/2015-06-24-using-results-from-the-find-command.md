Title: Using results from the find command
Date: 2015-06-24 16:42:23 -0600
Modified: 2015-06-24 16:42:23 -0600
Category: Programming
Tags: unix

The following will find all `.patch` files and copy them to some directory:

```bash
find . -name '*.patch' -print0 | xargs -0 -I % cp % some/directory
```

## Explanation

Each result is printed to stdout, followed by an ASCII NUL character `-print0`.  These are passed to `xargs` which is configured to expect the NUL character `-0` as the separator. `-I %` is used to identify a substitution character, which will be replaced in the following command `cp % some/directory`.
