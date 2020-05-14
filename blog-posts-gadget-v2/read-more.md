# Read more

Link to the full post.

```html
<!-- Read more -->
<b:if cond='data:post.hasJumpLink'>
  <a expr:href='fragment(data:post.url, "more")'>
    <b:attr expr:value='data:post.title ? data:post.title : ""' name='title'/>
    <data:blog.jumpLinkMessage/>
  </a>
<b:else/>
  <b:if cond='data:post.snippets'>
    <a expr:href='data:post.url' role='button'>
      <b:attr expr:value='data:post.title ? data:post.title : ""' name='title'/>
      <data:messages.keepReading/>
    </a>
  </b:if>
</b:if>
```
