[[AllNotes]]

---

```dataview
table aliases as Description
where status!="Inbox" and !file.day
limit 5
```

```dataview
table aliases as Description
where status="Inbox"
limit 5
```
