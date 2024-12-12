---
cssclasses:
  - cards
  - cards-cover
  - cards-2-3
  - table-max
publish: true
---
```dataview
table without id 
	("![](" + poster + ")") as Poster,
	file.link as Title,
	string(year) as Year, 
	actors as Actor,
	"🍿IMDB: " + IMDB as IMDB,
	"⭐ " + rating as Rating,
	"📺 " + length + " seasons" as length
	
where contains(file.folder, "Media Review/Series") 
SORT file.ctime DESC
```
