# modsecgrep

Adapted from http://endlessgeek.com/2014/02/search-modsecurity-audit-log-analysis/

## Usage ##

modsecgrep -s "Some search"

    -h        : this help message
    -n        : negate the search string
    -a        : show all activity (defaults to Interceptions only)
    -f file   : file to search (defaults to /usr/local/apache/logs/modsec_audit.log)
    -s search : string to match on - enclosed in quotes if it contains spaces
