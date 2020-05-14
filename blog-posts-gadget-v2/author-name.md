# Author name

Name of the profile of the post author.

`data:posts[i].author`

## Default

```html
<!-- Author name -->
<b:if cond='data:post.author'>
  <data:post.author.name/>
</b:if>
```

### Default with fallback

```html
<b:eval expr='data:post.author ? data:post.author.name : "Anonymous"'/>
```

```html
<!-- Author name -->
<b:if cond='data:post.author'>
  <data:post.author.name/>
<b:else/><!-- fallback -->
  Anonymous
</b:if>
```

## Anchors

```html
<!-- Author name -->
<b:if cond='data:post.author'>
  <b:if cond='data:post.author.profileUrl'>
    <a expr:href='data:post.author.profileUrl'>
      <data:post.author.name/>
    </a>
  <b:else/><!-- no profileUrl -->
    <data:post.author.name/>
  </b:if>
</b:if>
```

### Anchors with fallback

```html
<!-- Author name -->
<b:if cond='data:post.author.profileUrl'>
  <a expr:href='data:post.author.profileUrl'>
    <b:eval expr='data:post.author ? data:post.author.name : "Anonymous"'/>
  </a>
<b:else/><!-- no profileUrl -->
  <b:eval expr='data:post.author ? data:post.author.name : "Anonymous"'/>
</b:if>
```

```html
<!-- Author name -->
<b:if cond='data:post.author'>
  <b:if cond='data:post.author.profileUrl'>
    <a expr:href='data:post.author.profileUrl'>
      <data:post.author.name/>
    </a>
  <b:else/><!-- no profileUrl -->
    <data:post.author.name/>
  </b:if>
<b:else/><!-- fallback -->
  Anonymous
</b:if>
```
