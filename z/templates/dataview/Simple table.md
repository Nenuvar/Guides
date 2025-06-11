```dataview
TABLE "insert the columns and their content"
FROM "insert name of target foder or note here"
```

###### Example
```dataview
TABLE Emne as "Subject",file.name as "Class", Dag as "Day"
FROM #code30 
```
This creates a table with all the notes that contain the tag `code30`, with the columns`Subject` derived from the YAML `Emne`, `Files`, `Class` and `Day` (the YAML info "Dag" is renamed to "Day" in the output)