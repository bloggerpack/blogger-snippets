# Page types

Conditional tags for different page types, which allows you to specify a part of your template code on specific types of pages or specific URLs.

## Common

```html
# Homepage
<b:if cond='data:view.isHomepage'>
  <!-- https://example.blogspot.com -->
</b:if>

# Post page
<b:if cond='data:view.isPost'>
  <!-- https://example.blogspot.com/<year>/<month>/<permalink>.html -->
</b:if>

# Static page
<b:if cond='data:view.isPage'>
  <!-- https://example.blogspot.com/p/<permalink>.html -->
</b:if>

# Search (label) page
<b:if cond='data:view.search.label'>
  <!-- 1. https://example.blogspot.com/search/label/<label-name> -->
  <!-- 2. https://example.blogspot.com/search?label=<label-name> -->
</b:if>

# Search (query) page
<b:if cond='data:view.search.query'>
  <!-- https://example.blogspot.com/search?q=<query> -->
</b:if>

# Search (default) page
<b:if cond='data:view.search and !data:view.search.label and !data:view.search.query'>
  <!-- https://example.blogspot.com/search -->
</b:if>

# Archive page
<b:if cond='data:view.isArchive'>
  <!-- 1. https://example.blogspot.com/<year> -->
  <!-- 2. https://example.blogspot.com/<year>/<month> -->
  <!-- 3. https://example.blogspot.com/<year>_<month>_<day>_archive.html -->
</b:if>

# Error page
<b:if cond='data:view.isError'>
  <!-- https://example.blogspot.com/<404> -->
</b:if>
```

```html
# Preview page
<b:if cond='data:view.isPreview'>
  <!-- Preview page -->
</b:if>

# Layout mode
<b:if cond='data:view.isLayoutMode'>
  <!-- https://www.blogger.com/blog/layout/<blogID> -->
</b:if>
```

## Specific URLs

```html
# Specific post page
<b:if cond='data:view.url == "https://example.blogspot.com/1945/08/wow.html"'>
  <!-- https://example.blogspot.com/1945/08/wow.html -->
</b:if>

# Specific static page
<b:if cond='data:view.url == "https://example.blogspot.com/p/wow.html"'>
  <!-- https://example.blogspot.com/p/wow.html -->
</b:if>

# Specific search (label) page
<b:if cond='data:view.search.label == "WOW"'>
  <!-- 1. https://example.blogspot.com/search/label/WOW -->
  <!-- 2. https://example.blogspot.com/search?label=WOW -->
</b:if>

# Specific search (query) page
<b:if cond='data:view.search.query == "wow"'>
  <!-- https://example.blogspot.com/search?q=wow -->
</b:if>
```
