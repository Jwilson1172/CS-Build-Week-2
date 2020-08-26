# SQL CHALLENGES
## higher than 75 marks
### Query the Name of any student in STUDENTS who:
- scored higher than 75 Marks.
- each name ending in the same last three characters
- secondary sort them by ascending ID.

### Query:
```sql
SELECT NAME
FROM STUDENTS
WHERE MARKS > 75
ORDER BY RIGHT(NAME, 3), ID ASC;
```

