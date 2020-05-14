# Sharing

The share buttons for the post.

`data:posts[i].shareUrl`

## Default

```html
<!-- Sharing -->
<a expr:href='params(data:post.shareUrl, { target: "twitter" })' target='_blank'>
  Twitter
</a>
<a expr:href='params(data:post.shareUrl, { target: "facebook" })' target='_blank'>
  Facebook
</a>
<a expr:href='params(data:post.shareUrl, { target: "pinterest" })' target='_blank'>
  Pinterest
</a>
<a expr:href='params(data:post.shareUrl, { target: "email" })' target='_blank'>
  Email
</a>
<a expr:href='params(data:post.shareUrl, { target: "blog" })' target='_blank'>
  BlogThis!
</a>
```

## Dropdown example

```html
<!-- Sharing -->
<div class='dropdown'>
  <a aria-expanded='false' aria-haspopup='true' class='dropdown-toggle' data-toggle='dropdown' expr:title='data:messages.share' href='#'>
    <data:messages.share/>
  </a>
  <div class='dropdown-menu'>
    <a class='dropdown-item' expr:href='params(data:post.shareUrl, { target: "twitter" })' target='_blank'>
      Twitter
    </a>
    <a class='dropdown-item' expr:href='params(data:post.shareUrl, { target: "facebook" })' target='_blank'>
      Facebook
    </a>
    <a class='dropdown-item' expr:href='params(data:post.shareUrl, { target: "pinterest" })' target='_blank'>
      Pinterest
    </a>
    <a class='dropdown-item' expr:href='params(data:post.shareUrl, { target: "email" })' target='_blank'>
      Email
    </a>
    <a class='dropdown-item' expr:href='params(data:post.shareUrl, { target: "blog" })' target='_blank'>
      BlogThis!
    </a>
  </div>
</div>
```
