# Author photo

Photo of the profile of the post author.

`data:posts[i].author.authorPhoto`

**img src options**

- `128` is size
- `1:1` is aspect ratio
- calculation
  - width = size
    - width = `128`
  - height = (size * ratio height) / ratio width
    - height = (`128` * `1`) / `1` = `128`

## Default

```html
<!-- Author photo -->
<b:with value='128' var='size'>
<b:with value='"1:1"' var='ratio'>
  <b:if cond='data:post.author and data:post.author.authorPhoto'>
    <img>
      <!-- class --><b:class name='class-name'/>
      <!-- src --><b:attr expr:value='data:post.author.authorPhoto.image.isResizable ? resizeImage(data:post.author.authorPhoto.image, data:size, data:ratio) : data:post.author.authorPhoto.image' name='src'/>
      <!-- alt --><b:attr expr:value='data:post.author.name' name='alt'/>
      <b:attr name='b:whitespace' value='remove'/>
    </img>
  </b:if>
</b:with>
</b:with>
```

### Default with fallback

```html
<!-- Author photo -->
<b:with value='128' var='size'>
<b:with value='"1:1"' var='ratio'>
  <b:if cond='data:post.author and data:post.author.authorPhoto'>
    <img>
      <!-- class --><b:class name='class-name'/>
      <!-- src --><b:attr expr:value='data:post.author.authorPhoto.image.isResizable ? resizeImage(data:post.author.authorPhoto.image, data:size, data:ratio) : data:post.author.authorPhoto.image' name='src'/>
      <!-- alt --><b:attr expr:value='data:post.author.name' name='alt'/>
      <b:attr name='b:whitespace' value='remove'/>
    </img>
  <b:else/><!-- fallback -->
    <img>
      <!-- class --><b:class name='class-name'/>
      <!-- src --><b:attr name='src' value='https://via.placeholder.com/128x128/777/eee?text=No+Image'/>
      <!-- alt --><b:attr expr:value='data:messages.image' name='alt'/>
      <b:attr name='b:whitespace' value='remove'/>
    </img>
  </b:if>
</b:with>
</b:with>
```

## Anchors

```html
<!-- Author photo -->
<b:with value='128' var='size'>
<b:with value='"1:1"' var='ratio'>
  <b:if cond='data:post.author and data:post.author.authorPhoto'>
    <b:tag cond='data:post.author.profileUrl' expr:href='data:post.author.profileUrl' name='a'>
      <b:attr cond='data:post.author.profileUrl' name='b:whitespace' value='remove'/>
      <img>
        <!-- class --><b:class name='class-name'/>
        <!-- src --><b:attr expr:value='data:post.author.authorPhoto.image.isResizable ? resizeImage(data:post.author.authorPhoto.image, data:size, data:ratio) : data:post.author.authorPhoto.image' name='src'/>
        <!-- alt --><b:attr expr:value='data:post.author.name' name='alt'/>
        <b:attr name='b:whitespace' value='remove'/>
      </img>
    </b:tag>
  </b:if>
</b:with>
</b:with>
```

### Anchors with fallback

```html
<!-- Author photo -->
<b:with value='128' var='size'>
<b:with value='"1:1"' var='ratio'>
  <b:if cond='data:post.author and data:post.author.authorPhoto'>
    <b:tag cond='data:post.author.profileUrl' expr:href='data:post.author.profileUrl' name='a'>
      <b:attr cond='data:post.author.profileUrl' name='b:whitespace' value='remove'/>
      <img>
        <!-- class --><b:class name='class-name'/>
        <!-- src --><b:attr expr:value='data:post.author.authorPhoto.image.isResizable ? resizeImage(data:post.author.authorPhoto.image, data:size, data:ratio) : data:post.author.authorPhoto.image' name='src'/>
        <!-- alt --><b:attr expr:value='data:post.author.name' name='alt'/>
        <b:attr name='b:whitespace' value='remove'/>
      </img>
    </b:tag>
  <b:else/><!-- fallback -->
    <b:tag cond='data:post.author.profileUrl' expr:href='data:post.author.profileUrl' name='a'>
      <b:attr cond='data:post.author.profileUrl' name='b:whitespace' value='remove'/>
      <img>
        <!-- class --><b:class name='class-name'/>
        <!-- src --><b:attr name='src' value='https://via.placeholder.com/128x128/777/eee?text=No+Image'/>
        <!-- alt --><b:attr expr:value='data:messages.image' name='alt'/>
        <b:attr name='b:whitespace' value='remove'/>
      </img>
    </b:tag>
  </b:if>
</b:with>
</b:with>
```
