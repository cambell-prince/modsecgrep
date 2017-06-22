# modsecgrep

Adapted from http://endlessgeek.com/2014/02/search-modsecurity-audit-log-analysis/

'modsecgrep' is a command-line tool for searching content in the audit logs of mod-security.

## Usage ##

    modsecgrep -s "Some search"
    
    -h        : this help message
    -n        : negate the search string
    -a        : show all activity (defaults to Interceptions only)
    -f file   : file to search (defaults to /usr/local/apache/logs/modsec_audit.log)
    -s search : string to match on - enclosed in quotes if it contains spaces

## Tips ##

I find it useful to remove much of the haystack in order to find the needles worth investigating
more closely.  To that end I will do a negative search to exclude content I don't want to consider.

**Example:**
To exclude all records that are tagged as robots.

    modsecgrep -n -s "robots" | less

**Example:**
To focus on a particular day and excluding robots.

    modsecgrep -s "11/Jun" | modsecgrep -n -s "robots" | less

