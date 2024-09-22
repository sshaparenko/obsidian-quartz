---
date: 2024-09-01T17:01
tags:
  - Postgres
cssclasses:
  - page-white
---
`PREPARE` - prepare a statement for execution

A prepared statement is a query that you prepare on server side, which does the query parsing, analysis and any rewriting.

The advantage of prepared statement is that the parsing and planning stages are done once, and the execution can be related with different parameters, which can improve performance and efficiency

```postgresql
prepare foo as
	select date, shares, trades, dollars
		from factbook
	where date >= $1::date
		and date < $1::date + interval '1 month'
	order by date

execute foo('2024-09-03');
```

