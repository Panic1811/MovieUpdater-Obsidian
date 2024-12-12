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
	length + " mins" as "Runtime",
	director as Director,
	"⭐ " + rating as Rating,
	"🍅 " + substring(RT, length(RT) - 3, length(RT)) as "Rotten Tomatoes",
	Box_office as "Box Office"
where contains(file.folder, "Media Review/Movies") 
SORT file.ctime DESC
```
