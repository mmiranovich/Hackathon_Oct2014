{
  "Collection_Aggregate" : {
    "jsonVersion" : 1,
    "pipeline" : " { $group : { _id : \"$state\",     totalPop : { $sum : \"$pop\" } } },\r\n                       { $match : {\r\n\t\t\t\t\t   \t\t$and:[{\r\n\t\t\t\t\t   \t\ttotalPop : \r\n\t\t\t\t\t\t\t{ $gte : 10000000 }, \r\n\t\t\t\t\t\t\t_id:{$eq:\"CA\"}\r\n\t\t\t\t\t\t\t}\r\n\t\t\t\t\t\t\t]\r\n\t\t\t\t\t\t\t} \r\n\t\t\t\t\t\t\t}\r\n\t\t\t\t\t"
  }
}