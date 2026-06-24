---
aliases: []
type: literature
project: master-thesis
topic: [{% for tag in tags %}{{tag.tag}}{% if not loop.last %}, {% endif %}{% endfor %}]
status: ai-draft
citation-status: citable
source-notes: [{{citekey}}]
summary: "{{title}}"
citekey: {{citekey}}
authors: "{% for creator in creators %}{{creator.firstName}} {{creator.lastName}}{% if not loop.last %}, {% endif %}{% endfor %}"
year: {{date | truncate(4, true, "")}}
doi: "{{DOI}}"
---

# {{title}}

**Authors:** {% for creator in creators %}{{creator.firstName}} {{creator.lastName}}{% if not loop.last %}, {% endif %}{% endfor %}
**Year:** {{date | truncate(4, true, "")}}
**Citekey:** `{{citekey}}`
**Publication:** {% if publicationTitle %}{{publicationTitle}}{% elif bookTitle %}{{bookTitle}}{% elif publisher %}{{publisher}}{% endif %}
{% if DOI %}**DOI:** {{DOI}}{% endif %}

---

## Abstract

{{abstractNote}}

---

## Annotations

{% for annotation in annotations -%}
{% if annotation.annotatedText %}
> {{annotation.annotatedText}}{% if annotation.page %} (p. {{annotation.page}}){% endif %}

{% if annotation.comment %}**Note:** {{annotation.comment}}{% endif %}

{% endif %}
{%- endfor %}

---

## Zotero Notes

{% for note in notes %}{{note.note}}{% if not loop.last %}

---

{% endif %}{% endfor %}

---

*Imported via Zotero Integration · status: ai-draft · promote to human-review after author reads*
