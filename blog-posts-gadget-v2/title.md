# Title

Title of the post.

`data:posts[i].title`

## Default

```html
<!-- Title -->
<b:if cond='data:post.title'>
  <data:post.title/>
</b:if>
```

### Default with fallback

```html
<!-- Title -->
<b:eval expr='data:post.title ? data:post.title : data:messages.noTitle'/>
```

```html
<!-- Title -->
<b:if cond='data:post.title'>
  <data:post.title/>
<b:else/><!-- fallback -->
  <data:messages.noTitle/>
</b:if>
```

## Anchors

```html
<!-- Title -->
<b:if cond='data:post.title'>
  <a expr:href='data:post.link ?: data:post.url'>
    <data:post.title/>
  </a>
</b:if>
```

### Anchors with fallback

```html
<!-- Title -->
<a expr:href='data:post.link ?: data:post.url'>
  <b:eval expr='data:post.title ? data:post.title : data:messages.noTitle'/>
</a>
```

```html
<!-- Title -->
<b:if cond='data:post.title'>
  <a expr:href='data:post.link ?: data:post.url'>
    <data:post.title/>
  </a>
<b:else/><!-- fallback -->
  <a expr:href='data:post.link ?: data:post.url'>
    <data:messages.noTitle/>
  </a>
</b:if>
```
