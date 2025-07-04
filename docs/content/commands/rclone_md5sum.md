---
title: "rclone md5sum"
description: "Produces an md5sum file for all the objects in the path."
versionIntroduced: v1.02
# autogenerated - DO NOT EDIT, instead edit the source code in cmd/md5sum/ and as part of making a release run "make commanddocs"
---
# rclone md5sum

Produces an md5sum file for all the objects in the path.

## Synopsis

Produces an md5sum file for all the objects in the path.  This
is in the same format as the standard md5sum tool produces.

By default, the hash is requested from the remote.  If MD5 is
not supported by the remote, no hash will be returned.  With the
download flag, the file will be downloaded from the remote and
hashed locally enabling MD5 for any remote.

For other algorithms, see the [hashsum](/commands/rclone_hashsum/)
command. Running `rclone md5sum remote:path` is equivalent
to running `rclone hashsum MD5 remote:path`.

This command can also hash data received on standard input (stdin),
by not passing a remote:path, or by passing a hyphen as remote:path
when there is data to read (if not, the hyphen will be treated literally,
as a relative path).


```
rclone md5sum remote:path [flags]
```

## Options

```
      --base64               Output base64 encoded hashsum
  -C, --checkfile string     Validate hashes against a given SUM file instead of printing them
      --download             Download the file and hash it locally; if this flag is not specified, the hash is requested from the remote
  -h, --help                 help for md5sum
      --output-file string   Output hashsums to a file rather than the terminal
```

Options shared with other commands are described next.
See the [global flags page](/flags/) for global options not listed here.

### Filter Options

Flags for filtering directory listings

```
      --delete-excluded                     Delete files on dest excluded from sync
      --exclude stringArray                 Exclude files matching pattern
      --exclude-from stringArray            Read file exclude patterns from file (use - to read from stdin)
      --exclude-if-present stringArray      Exclude directories if filename is present
      --files-from stringArray              Read list of source-file names from file (use - to read from stdin)
      --files-from-raw stringArray          Read list of source-file names from file without any processing of lines (use - to read from stdin)
  -f, --filter stringArray                  Add a file filtering rule
      --filter-from stringArray             Read file filtering patterns from a file (use - to read from stdin)
      --hash-filter string                  Partition filenames by hash k/n or randomly @/n
      --ignore-case                         Ignore case in filters (case insensitive)
      --include stringArray                 Include files matching pattern
      --include-from stringArray            Read file include patterns from file (use - to read from stdin)
      --max-age Duration                    Only transfer files younger than this in s or suffix ms|s|m|h|d|w|M|y (default off)
      --max-depth int                       If set limits the recursion depth to this (default -1)
      --max-size SizeSuffix                 Only transfer files smaller than this in KiB or suffix B|K|M|G|T|P (default off)
      --metadata-exclude stringArray        Exclude metadatas matching pattern
      --metadata-exclude-from stringArray   Read metadata exclude patterns from file (use - to read from stdin)
      --metadata-filter stringArray         Add a metadata filtering rule
      --metadata-filter-from stringArray    Read metadata filtering patterns from a file (use - to read from stdin)
      --metadata-include stringArray        Include metadatas matching pattern
      --metadata-include-from stringArray   Read metadata include patterns from file (use - to read from stdin)
      --min-age Duration                    Only transfer files older than this in s or suffix ms|s|m|h|d|w|M|y (default off)
      --min-size SizeSuffix                 Only transfer files bigger than this in KiB or suffix B|K|M|G|T|P (default off)
```

### Listing Options

Flags for listing directories

```
      --default-time Time   Time to show if modtime is unknown for files and directories (default 2000-01-01T00:00:00Z)
      --fast-list           Use recursive list if available; uses more memory but fewer transactions
```

## See Also

* [rclone](/commands/rclone/)	 - Show help for rclone commands, flags and backends.

