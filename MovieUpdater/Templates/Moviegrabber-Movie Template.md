---
type:
  - "{{Type}}"
country: "{{Country}}"
title: "{{Title}}"
year: "{{Year}}"
director: "{{Director}}"
actors: [{{Actors}}] 
genre: [{{Genre}}] 
length: "{{Runtime}}"
Writer: "{{writer}}"
poster: "{{Poster}}"
Box_office: "{{BoxOffice}}"
RT: '{{Ratings|"|"|<$Rotten Tomatoes\: .*$>}}'
Creation Date: <% tp.file.creation_date() %>
seen: true
publish: true
location: 
year watched: 
seen with: 
rating:
---
# 🎥 **{{Title}}** 
*Creation Date: <% tp.file.creation_date() %>*

**Year:** {{Year}}
**Directed by:** {{Director|"[[|]]"}}
**Writer:** {{Writer|"[[|]]"}}
**Starring:**  {{Actors|"[[|]]"}}
**Genre:** {{genre}}
**Run Time:** {{Runtime|| mins}}
**Box Office:** {{BoxOffice}}
**Awards:** {{Awards}}
**RT:** {{Ratings|"|"|<$Rotten Tomatoes\: .*$>}}

> [!note]- YouTube Trailer
> {{YoutubeEmbed}}

## 🗒️Plot

{{Plot}}

## ⭐ Quick Ratings

1. **Story:** 
	- :Story = 
2. **Acting:** 
	- :Acting = 
3. **Cinematography:** 
	- :Cinematography = 
4. **Music:** 
	- :Music = 
5. **Overall:** 
	- (:Story + :Acting + :Cinematography + :Music)/4 = 

