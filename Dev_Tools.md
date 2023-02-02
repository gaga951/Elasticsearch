GET _cluster/health

GET _search
{
  "query": {
    "match_all": {}
  }
}


GET _cat/indices?v&s=health:desc,index&h=health,status,index,docs.count,pri,rep


GET _cat/allocation?v

## to change from read only indexes
## it happens when disk is low than 80% indexes ar automatically gou

## for specific single index use 

PUT index_name/_settings
{
  "index": {
    "blocks": {
      "read_only_allow_delete": null
    }
  }
}

## for all indexes

PUT */_settings
{
  "index": {
    "blocks": {
      "read_only_allow_delete": null
    }
  }
}

### If the request was successful, you should see a response like this:
{
    "acknowledged": true
}
## #########################


GET */_settings
