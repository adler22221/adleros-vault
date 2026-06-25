---
created: 2022-12-07T23:33
author: human
cDate: <%tp.file.creation_date("YYYYMMDD HH:mm:ss")%> 
lmDate: <% tp.file.last_modified_date("YYYYMMDD HH:mm:ss") %>
---

Timestamp:: [[{{date:YYYYMMDD}}]] {{date:HH:mm:ss}}
Energy:: <% await tp.system.suggester(["Energy Level 10", "Energy Level 9", "Energy Level 8", "Energy Level 7", "Energy Level 6", "Energy Level 5", "Energy Level 4", "Energy Level 3", "Energy Level 2", "Energy Level 1", "Energy Level 0"], [10, 9, 8, 7, 6, 5, 4, 3, 2, 1, 0]) %>
Sensation:: <% await tp.system.suggester(["Sensation Level 10", "Sensation Level 9", "Sensation Level 8", "Sensation Level 7", "Sensation Level 6", "Sensation Level 5", "Sensation Level 4", "Sensation Level 3", "Sensation Level 2", "Sensation Level 1", "Sensation Level 0"], [10, 9, 8, 7, 6, 5, 4, 3, 2, 1, 0]) %>
Mood:: <% await tp.system.suggester(["Mood Level 10", "Mood Level 9", "Mood Level 8", "Mood Level 7", "Mood Level 6", "Mood Level 5", "Mood Level 4", "Mood Level 3", "Mood Level 2", "Mood Level 1", "Mood Level 0"], [10, 9, 8, 7, 6, 5, 4, 3, 2, 1, 0]) %>
Clarity:: <% await tp.system.suggester(["Clarity Level 10", "Clarity Level 9", "Clarity Level 8", "Clarity Level 7", "Clarity Level 6", "Clarity Level 5", "Clarity Level 4", "Clarity Level 3", "Clarity Level 2", "Clarity Level 1", "Clarity Level 0"], [10, 9, 8, 7, 6, 5, 4, 3, 2, 1, 0]) %>
Context:: <% await tp.system.prompt("What is the context of this situation? (e.g., people, project, activity, event, etc.)") %>
Memo:: <% await tp.system.prompt("Anything else to note?") %>