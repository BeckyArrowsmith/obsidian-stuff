---
created: <% tp.file.creation_date() %>
---
tags: [[+Daily Notes]]

# <% moment(tp.file.title,'YYYY-MM-DD').format('dddd, MMMM DD, YYYY') %>

<< [[<% fileDate = moment(tp.file.title, 'YYYY-MM-DD-dddd').subtract(1, 'd').format('YYYY-MM-DD-dddd') %>|Yesterday]] | [[<% fileDate = moment(tp.file.title, 'YYYY-MM-DD-dddd').add(1, 'd').format('YYYY-MM-DD-dddd') %>|Tomorrow]] >>


---
# ✅ Todo

```todoist

name: Highest Priority & Date

filter: "today | overdue"

sorting:

- date

- priority

group: true

```
---
# 👯‍♀️ Meetings

## Stand-up
- <% tp.file.cursor() %>
---
# 📝 Notes

---
### Notes created today
```dataview
List FROM "" WHERE file.cday = date("<%tp.date.now('YYYY-MM-DD')%>") SORT file.ctime asc
```

### Notes modified today
```dataview
List FROM "" WHERE file.mday = date("<%tp.date.now('YYYY-MM-DD')%>") AND file.cday != date("<%tp.date.now('YYYY-MM-DD')%>") SORT file.mtime asc
```
