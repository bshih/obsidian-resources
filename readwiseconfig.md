# Filename:
```
{{title}} by {{author}}
```

# Page Title
```
# {{ title }}
```
# Page Metadata:
````
#note/refnote #note/readwise

## Metadata
- Summary:: 
- Status:: #x/unprocessed
- Author:: {% if author %}{{author}}{% endif %}
{% if document_tags -%}
- Tags:: #readwise {% for tag in document_tags %}#on/{{tag}} {% endfor %}
{% endif -%}
{% if url -%}
- Source:: {{url}}
{% endif -%}
- Category:: #source/{{category}}

## Links
```dataview
TABLE file.cday AS "Date"
FROM [[<% tp.file.title %>]]
sort date ASCENDING
```
````

# Highlights Header
```
{% if is_new_page %}
## Highlights
{% elif has_new_highlights -%}
## New highlights added [[{{date}}]]
{% endif -%}
```

# Highlight
````
> {{ highlight_text }}{% if highlight_location and highlight_location_url %} ([{{highlight_location}}]({{highlight_location_url}})){% elif highlight_location %} ({{highlight_location}}){% endif %}
{% if highlight_tags -%}
- Tags: {% for tag in highlight_tags %}#on/{{tag}} {% endfor %}
{% endif -%}
{% if highlight_note %}
```ad-note
{{ highlight_note }}
```{% endif %}

````

# YAML frontmatter
```

```
