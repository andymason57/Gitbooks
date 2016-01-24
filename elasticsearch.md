# Elasticsearch


To run Sense (ES query tool) need to start Kibana on Localhost:5601. 



Shutdown ES - CURL -XPOST 'http://localhost:9200/_shutdown'

Two ways of communicating with ES : 

1. Java - 2 clients - Node and transport client via Java API. 
2. Rest API via JSON and Http. 


Request to ES takes form :

curl -X<VERB> '<PROTOCOL>://<HOST>/<PATH>?<QUERY_STRING>' -d '<BODY>'


####**Search for records : **

GET /indexName/Type/_search


####**query-string search**

GET /megacorp/employee/_search?q=last_name:Smith

###**Search with Query DSL** 

GET /megacorp/employee/_search
{
        "query" : {
            "match" : {
                "last_name" : "Smith"
                }
            }
}

####**Return exactly matched phrase**
GET /index/type/_search
{
    "query" : {
        "match_phrase" : {
            "field name" : "phrase to find"
        }
    }
}



