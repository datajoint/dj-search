# dj-search
DataJoint utility to facilitate text search on a DataJoint pipeline

# Installation
Install using pip from GitHub repository:

    
    pip install git+https://github.com/datajoint/dj-search.git

# Usage

```
from dj_search import DJSearch

# limit the search scope to schemas with a particular prefix
djsearch = DJSearch('dbprefix_')

# several ways to do search:

# search all schemas
djmatch = djsearch.search('Scan')

# or search by table-name only
djmatch = djsearch.search('ScanInfo', level='table')

# or search in comment only
djmatch = djsearch.search('depth', level='comment')

# or search by attribute-name only
djmatch = djsearch.search('field', level='attribute')
```

***djmatch.matches*** returns a dictionary with:
+ key: <schema_name>.<table_name>
+ value: a dictionary with:
    + ***definition***: string of the table definition
    + ***table***: DJ table for this table
    + ***tier***: tier of this table
    
