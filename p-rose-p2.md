# Part 2
example query:
click on the database icon
then click on a label, or make a query directly in the command line

`match (c:City {name: 'San Diego'}) return c`
`match (c:City {name: 'San Diego'}) WHERE c.population > 1000000 return c`
`match (c:City {name: 'San Diego'})-[:IN]->(a:Admin2 {name: 'San Diego'})-[:IN]->(a:Admin1 {name: 'San Diego'}) return c`

to return entire path:

`match p=(:City {name: 'San Diego'})-[:IN]->(:Admin2 {name: 'San Diego'})-[:IN]->(:Admin1 {name: 'San Diego'}) return p`

return democraphics

`match p=(:City {name: 'San Diego'})-[:IN]->[:HAS_ECONOMICS]->() return p`

you can use [:IN*] to skip the intermediary processes, to go directly from city to world for instance