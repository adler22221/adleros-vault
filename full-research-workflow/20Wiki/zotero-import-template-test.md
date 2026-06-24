---
citekey: {{citekey}}
test_field: template_loaded
---
# {{title}}

Authors raw: {{creators | dump}}

Date raw: {{date}}

Abstract present: {{abstractNote | length > 0}}

Annotation count: {{annotations | length}}

First annotation: {% if annotations.length > 0 %}{{annotations[0].annotatedText}}{% else %}none{% endif %}
