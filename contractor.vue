{
  "Collection_Aggregate" : {
    "jsonVersion" : 1,
    "pipeline" : "/*\r\n{\r\n$unwind :\"$reviews\"\r\n},\r\n{\r\n\t$group :{\r\n\t\t\t_id:\"$_id\", numberofReviews : {$sum:1}\r\n\t\t\t}\r\n},\r\n{\r\n\t$match : {\r\n\t\t\tnumberofReviews : {$gt : 0}\r\n\t}\r\n}\r\n*/\r\n\r\n\r\n { \"$unwind\" : \"$reviews\"} , \r\n { \"$group\" : { \"_id\" : \"$id\" , \"avgRevs\" : { \"$avg\" : \"$reviews.rating\"}}} , \r\n { \"$match\" : { \"avgRevs\" : { \"$gte\" : 3}}} , \r\n { \"$sort\" : { \"avgRevs\" : -1}}"
  }
}