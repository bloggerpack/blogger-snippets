# Labels

Labels of the post.

`data:posts[i].labels`

**Link options**

- `12` is maximum number of posts in label page

## Default

```html
<!-- Labels -->
<b:if cond='data:post.labels'>
  <b:loop index='i' values='data:post.labels' var='label'>
    <a expr:href='params(data:label.url, { max-results: "12" })'><data:label.name/></a>
  </b:loop>
</b:if>
```

### Default with fallback

```html
<!-- Labels -->
<b:if cond='data:post.labels'>
  <b:loop index='i' values='data:post.labels' var='label'>
    <a expr:href='params(data:label.url, { max-results: "12" })'><data:label.name/></a>
  </b:loop>
<b:else/><!-- fallback -->
  Unlabelled
</b:if>
```

## Comma

```html
<!-- Labels -->
<b:if cond='data:post.labels'>
  <b:loop index='i' values='data:post.labels' var='label'>
    <a expr:href='params(data:label.url, { max-results: "12" })'><data:label.name/></a><b:if cond='data:i != (data:post.labels.size - 1)'>,</b:if>
  </b:loop>
</b:if>
```

### Comma with fallback

```html
<!-- Labels -->
<b:if cond='data:post.labels'>
  <b:loop index='i' values='data:post.labels' var='label'>
    <a expr:href='params(data:label.url, { max-results: "12" })'><data:label.name/></a><b:if cond='data:i != (data:post.labels.size - 1)'>,</b:if>
  </b:loop>
<b:else/><!-- fallback -->
  Unlabelled
</b:if>
```
