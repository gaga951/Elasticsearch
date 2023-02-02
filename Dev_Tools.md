GET _cluster/health

GET _search
{
  "query": {
    "match_all": {}
  }
}

GET _cat/indices?v&s=health:desc,index&h=health,status,index,docs.count,pri,rep

GET _cat/allocation?v

PUT */_settings
{
  "index": {
    "blocks": {
      "read_only_allow_delete": null
    }
  }
}

GET */_settings
