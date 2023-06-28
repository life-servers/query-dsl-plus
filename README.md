# query-dsl-plus


#### Brief introduction

1. The foreground passes variable query parameters through strings
2. The backend encapsulates the query scenario, a method that query all data


#### Examples
![postman query1](postman_query1.png)
![postman query2](postman_query2.png)


#### Installation tutorial

1. deploy to you maven repository
2. import into you project pom.xml
3. extends SearchService
4. function use
    // search string, passed by the frontend, example: search age>18 and addr=addr

    String search = "age>18,addr:addr";

    BooleanExpression exp = this.buildPredicate(search, TestEntity.class);

#### Instructions for use

    case ":"  eq, example: search=name:jack, like sql >> name="jack" 

    case ">"  gt, example: search=age>18, like sql >> age>18 

    case "<"  lt, example: search=age<18, like sql >> age<18 

    case ")"  goe, example: search=age)18, like sql >> age>=18 

    case "("  loe, example: search=age(18, like sql >> age<=18 

    case "!"  né, example: search=age!18, like sql >> age!=18 or age<>18

    case "*"  like, example: search=name*%abc%, like sql >> name like "%abc%"

    case "^"  not like, example: search=name^%abc%, like sql >> name not like "%abc%" 

    case "@"  in, example: search=name@a|b|c, like sql >> name in ("a","b","c")  

    case "#"  contains, example: search=name#abc, like sql >> contains (name,"abc")  

    case "~"  or, example: search=name:abc~age:18, like sql >> name="abc" and age=18  

    case "|"  list separator, example: search=name@a|b|c, like sql >> name in ("a","b","c") 

    other "," params split,more than 2 params, use the "," to separated <br>
