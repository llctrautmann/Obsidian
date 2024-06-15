---
modified: 2024-06-15
date:
  - 15-06-2024
vss: <% tp.system.prompt("Please enter a value") %>
mood: <% await tp.system.suggester(["1 (bad)", "2","3","4","5","6","7 (good)"], ["1", "2","3","4","5","6","7"]) %>
stress: <% await tp.system.suggester(["1 (bad)", "2","3","4","5","6","7 (good)"], ["1", "2","3","4","5","6","7"]) %>
---


// Prompt
<% tp.system.prompt("Please enter a value") %>
// Prompt with default value
<% tp.system.prompt("What is your mood today?", "happy") %>
// Multiline prompt
<% tp.system.prompt("What is your mood today?", null, false, true) %>



