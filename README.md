# community-extensions
Central location for SigMF users to make their extensions publicly available to all.

The (SigMF Standard)[https://sigmf.org/] requires that references to extensions
(such as the ones this this repository) contain a URI reference from whence it can
be downloaded.
As there is no coordinated release cycle among these community-maintained extensions,
there must exist some mechanism by which a specific version of one of the `-schema.json`
files in this repo can be referenced.
However, using a GitHub "permalink" is not suitable for this purpose, because the
`"$id"` field must indicate that URI, and (as part of the content of a commit) this
value will affect the commit hash ...

Consequently, we use the following "two tiered" versioning approach to the "one-stop
shopping" scope of this repo:
  1. git tags will be assigned by the maintainers of this repo whenever any schema
     contributor indicates that a "release" is desired.
     This will always be a date of the form YYYY-mm-dd (e.g., `2025-01-02`).
  1. Individual schema should include a `"$comment"` key-value pair (ideally) on the
     line after the `"$id"` key-value pair which will use
     [Semantic Versioning](https://semver.or) as a means of indicating
     backwards-incompatible/new-functionality/bug-fixes of that individual schema.

An example of such a schema id: https://raw.githubusercontent.com/sigmf/community-extensions/refs/tags/2025-01-01/sigmf-wifi-schema.json
