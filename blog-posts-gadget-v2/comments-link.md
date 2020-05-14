# Comments link

Link to the comments on the post.

`data:posts[i].commentsUrl`

## Default

```html
<!-- Comments link -->
<b:if cond='data:post.allowComments'>
  <a expr:href='data:post.commentsUrl'>
    <data:messages.comments/>
  </a>
</b:if>
```

### Default with fallback

```html
<!-- Comments link -->
<b:if cond='data:post.allowComments'>
  <a expr:href='data:post.commentsUrl'>
    <data:messages.comments/>
  </a>
<b:else/><!-- fallback -->
  Comments are disabled
</b:if>
```

## Number of comments

Only working if using Blogger's default comments system.

```html
<!-- Comments link -->
<b:if cond='data:post.allowComments'>
  <a expr:href='data:post.commentsUrl'>
    <b:message name='messages.numberOfComments'>
      <b:param expr:value='data:post.numberOfComments' name='numComments'/>
    </b:message>
  </a>
</b:if>
```

### Number of comments with fallback

```html
<!-- Comments link -->
<b:if cond='data:post.allowComments'>
  <a expr:href='data:post.commentsUrl'>
    <b:message name='messages.numberOfComments'>
      <b:param expr:value='data:post.numberOfComments' name='numComments'/>
    </b:message>
  </a>
<b:else/><!-- fallback -->
  Comments are disabled
</b:if>
```
