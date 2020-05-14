# Featured image

The featured image for the post.

`data:posts[i].featuredImage`

**img src options**

- `800` is size
- `16:9` is aspect ratio
- calculation
  - width = size
    - width = `800`
  - height = (size * ratio height) / ratio width
    - height = (`800` * `9`) / `16` = `450`

## Default

```html
<!-- Featured image -->
<b:with value='800' var='size'>
<b:with value='"16:9"' var='ratio'>
  <b:if cond='data:post.featuredImage'>
    <b:if cond='data:post.featuredImage.isYoutube'>
      <img>
        <!-- class --><b:class name='class-name'/>
        <!-- src --><b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, data:size, data:ratio) : data:post.featuredImage.youtubeMaxResDefaultUrl' name='src'/>
        <!-- alt --><b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
        <b:attr name='b:whitespace' value='remove'/>
      </img>
    <b:else/>
      <img>
        <!-- class --><b:class name='class-name'/>
        <!-- src --><b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, data:size, data:ratio) : data:post.featuredImage' name='src'/>
        <!-- alt --><b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
        <b:attr name='b:whitespace' value='remove'/>
      </img>
    </b:if>
  </b:if>
</b:with>
</b:with>
```

### Default with fallback

```html
<!-- Featured image -->
<b:with value='800' var='size'>
<b:with value='"16:9"' var='ratio'>
  <b:if cond='data:post.featuredImage'>
    <b:if cond='data:post.featuredImage.isYoutube'>
      <img>
        <!-- class --><b:class name='class-name'/>
        <!-- src --><b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, data:size, data:ratio) : data:post.featuredImage.youtubeMaxResDefaultUrl' name='src'/>
        <!-- alt --><b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
        <b:attr name='b:whitespace' value='remove'/>
      </img>
    <b:else/>
      <img>
        <!-- class --><b:class name='class-name'/>
        <!-- src --><b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, data:size, data:ratio) : data:post.featuredImage' name='src'/>
        <!-- alt --><b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
        <b:attr name='b:whitespace' value='remove'/>
      </img>
    </b:if>
  <b:else/><!-- fallback -->
    <img>
      <!-- class --><b:class name='class-name'/>
      <!-- src --><b:attr expr:value='resizeImage("https://lh3.googleusercontent.com/kBzrgG0CUVwpWe8oT8iPxL8HhKQdNVj1AX5BR2Y0Q_zoSpxHGPRtcysgTJsb8ZEsYmbWoNm-nEOyjBc03w=w1920-h1080-rw-no", data:size, data:ratio)' name='src'/>
      <!-- alt --><b:attr expr:value='data:messages.image' name='alt'/>
      <b:attr name='b:whitespace' value='remove'/>
    </img>
  </b:if>
</b:with>
</b:with>
```

## Responsive images

```html
<!-- Featured image -->
<b:with value='800' var='size'>
<b:with value='"16:9"' var='ratio'>
  <b:if cond='data:post.featuredImage'>
    <b:if cond='data:post.featuredImage.isYoutube'>
      <img>
        <!-- class --><b:class name='class-name'/>
        <!-- src --><b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, data:size, data:ratio) : data:post.featuredImage.youtubeMaxResDefaultUrl' name='src'/>
        <!-- srcset --><b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, [200,400,800,1200,1600], data:ratio) : data:post.featuredImage.youtubeMaxResDefaultUrl' name='srcset'/>
        <!-- sizes --><b:attr name='sizes' value='100vw'/>
        <!-- alt --><b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
        <b:attr name='b:whitespace' value='remove'/>
      </img>
    <b:else/>
      <img>
        <!-- class --><b:class name='class-name'/>
        <!-- src --><b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, data:size, data:ratio) : data:post.featuredImage' name='src'/>
        <!-- srcset --><b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, [200,400,800,1200,1600], data:ratio) : data:post.featuredImage' name='srcset'/>
        <!-- sizes --><b:attr name='sizes' value='100vw'/>
        <!-- alt --><b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
        <b:attr name='b:whitespace' value='remove'/>
      </img>
    </b:if>
  </b:if>
</b:with>
</b:with>
```

### Responsive images with fallback

```html
<!-- Featured image -->
<b:with value='800' var='size'>
<b:with value='"16:9"' var='ratio'>
  <b:if cond='data:post.featuredImage'>
    <b:if cond='data:post.featuredImage.isYoutube'>
      <img>
        <!-- class --><b:class name='class-name'/>
        <!-- src --><b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, data:size, data:ratio) : data:post.featuredImage.youtubeMaxResDefaultUrl' name='src'/>
        <!-- srcset --><b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, [200,400,800,1200,1600], data:ratio) : data:post.featuredImage.youtubeMaxResDefaultUrl' name='srcset'/>
        <!-- sizes --><b:attr name='sizes' value='100vw'/>
        <!-- alt --><b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
        <b:attr name='b:whitespace' value='remove'/>
      </img>
    <b:else/>
      <img>
        <!-- class --><b:class name='class-name'/>
        <!-- src --><b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, data:size, data:ratio) : data:post.featuredImage' name='src'/>
        <!-- srcset --><b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, [200,400,800,1200,1600], data:ratio) : data:post.featuredImage' name='srcset'/>
        <!-- sizes --><b:attr name='sizes' value='100vw'/>
        <!-- alt --><b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
        <b:attr name='b:whitespace' value='remove'/>
      </img>
    </b:if>
  <b:else/><!-- fallback -->
    <img>
      <!-- class --><b:class name='class-name'/>
      <!-- src --><b:attr expr:value='resizeImage("https://lh3.googleusercontent.com/kBzrgG0CUVwpWe8oT8iPxL8HhKQdNVj1AX5BR2Y0Q_zoSpxHGPRtcysgTJsb8ZEsYmbWoNm-nEOyjBc03w=w1920-h1080-rw-no", data:size, data:ratio)' name='src'/>
      <!-- srcset --><b:attr expr:value='resizeImage("https://lh3.googleusercontent.com/kBzrgG0CUVwpWe8oT8iPxL8HhKQdNVj1AX5BR2Y0Q_zoSpxHGPRtcysgTJsb8ZEsYmbWoNm-nEOyjBc03w=w1920-h1080-rw-no", [200,400,800,1200,1600], data:ratio)' name='srcset'/>
      <!-- sizes --><b:attr name='sizes' value='100vw'/>
      <!-- alt --><b:attr expr:value='data:messages.image' name='alt'/>
      <b:attr name='b:whitespace' value='remove'/>
    </img>
  </b:if>
</b:with>
</b:with>
```

## Anchors

```html
<!-- Featured image -->
<b:with value='800' var='size'>
<b:with value='"16:9"' var='ratio'>
  <b:if cond='data:post.featuredImage'>
    <b:if cond='data:post.featuredImage.isYoutube'>
      <a expr:href='data:post.link ?: data:post.url'>
        <b:attr name='b:whitespace' value='remove'/>
        <img>
          <!-- class --><b:class name='class-name'/>
          <!-- src --><b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, data:size, data:ratio) : data:post.featuredImage.youtubeMaxResDefaultUrl' name='src'/>
          <!-- alt --><b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
          <b:attr name='b:whitespace' value='remove'/>
        </img>
      </a>
    <b:else/>
      <a expr:href='data:post.link ?: data:post.url'>
        <b:attr name='b:whitespace' value='remove'/>
        <img>
          <!-- class --><b:class name='class-name'/>
          <!-- src --><b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, data:size, data:ratio) : data:post.featuredImage' name='src'/>
          <!-- alt --><b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
          <b:attr name='b:whitespace' value='remove'/>
        </img>
      </a>
    </b:if>
  </b:if>
</b:with>
</b:with>
```

### Anchors with fallback

```html
<!-- Featured image -->
<b:with value='800' var='size'>
<b:with value='"16:9"' var='ratio'>
  <b:if cond='data:post.featuredImage'>
    <b:if cond='data:post.featuredImage.isYoutube'>
      <a expr:href='data:post.link ?: data:post.url'>
        <b:attr name='b:whitespace' value='remove'/>
        <img>
          <!-- class --><b:class name='class-name'/>
          <!-- src --><b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, data:size, data:ratio) : data:post.featuredImage.youtubeMaxResDefaultUrl' name='src'/>
          <!-- alt --><b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
          <b:attr name='b:whitespace' value='remove'/>
        </img>
      </a>
    <b:else/>
      <a expr:href='data:post.link ?: data:post.url'>
        <b:attr name='b:whitespace' value='remove'/>
        <img>
          <!-- class --><b:class name='class-name'/>
          <!-- src --><b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, data:size, data:ratio) : data:post.featuredImage' name='src'/>
          <!-- alt --><b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
          <b:attr name='b:whitespace' value='remove'/>
        </img>
      </a>
    </b:if>
  <b:else/><!-- fallback -->
    <a expr:href='data:post.link ?: data:post.url'>
      <b:attr name='b:whitespace' value='remove'/>
      <img>
        <!-- class --><b:class name='class-name'/>
        <!-- src --><b:attr expr:value='resizeImage("https://lh3.googleusercontent.com/kBzrgG0CUVwpWe8oT8iPxL8HhKQdNVj1AX5BR2Y0Q_zoSpxHGPRtcysgTJsb8ZEsYmbWoNm-nEOyjBc03w=w1920-h1080-rw-no", data:size, data:ratio)' name='src'/>
        <!-- alt --><b:attr expr:value='data:messages.image' name='alt'/>
        <b:attr name='b:whitespace' value='remove'/>
      </img>
    </a>
  </b:if>
</b:with>
</b:with>
```

### Anchors with responsive images

```html
<!-- Featured image -->
<b:with value='800' var='size'>
<b:with value='"16:9"' var='ratio'>
  <b:if cond='data:post.featuredImage'>
    <b:if cond='data:post.featuredImage.isYoutube'>
      <a expr:href='data:post.link ?: data:post.url'>
        <b:attr name='b:whitespace' value='remove'/>
        <img>
          <!-- class --><b:class name='class-name'/>
          <!-- src --><b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, data:size, data:ratio) : data:post.featuredImage.youtubeMaxResDefaultUrl' name='src'/>
          <!-- srcset --><b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, [200,400,800,1200,1600], data:ratio) : data:post.featuredImage.youtubeMaxResDefaultUrl' name='srcset'/>
          <!-- sizes --><b:attr name='sizes' value='100vw'/>
          <!-- alt --><b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
          <b:attr name='b:whitespace' value='remove'/>
        </img>
      </a>
    <b:else/>
      <a expr:href='data:post.link ?: data:post.url'>
        <b:attr name='b:whitespace' value='remove'/>
        <img>
          <!-- class --><b:class name='class-name'/>
          <!-- src --><b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, data:size, data:ratio) : data:post.featuredImage' name='src'/>
          <!-- srcset --><b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, [200,400,800,1200,1600], data:ratio) : data:post.featuredImage' name='srcset'/>
          <!-- sizes --><b:attr name='sizes' value='100vw'/>
          <!-- alt --><b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
          <b:attr name='b:whitespace' value='remove'/>
        </img>
      </a>
    </b:if>
  </b:if>
</b:with>
</b:with>
```

### Anchors with responsive images and fallback

```html
<!-- Featured image -->
<b:with value='800' var='size'>
<b:with value='"16:9"' var='ratio'>
  <b:if cond='data:post.featuredImage'>
    <b:if cond='data:post.featuredImage.isYoutube'>
      <a expr:href='data:post.link ?: data:post.url'>
        <b:attr name='b:whitespace' value='remove'/>
        <img>
          <!-- class --><b:class name='class-name'/>
          <!-- src --><b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, data:size, data:ratio) : data:post.featuredImage.youtubeMaxResDefaultUrl' name='src'/>
          <!-- srcset --><b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, [200,400,800,1200,1600], data:ratio) : data:post.featuredImage.youtubeMaxResDefaultUrl' name='srcset'/>
          <!-- sizes --><b:attr name='sizes' value='100vw'/>
          <!-- alt --><b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
          <b:attr name='b:whitespace' value='remove'/>
        </img>
      </a>
    <b:else/>
      <a expr:href='data:post.link ?: data:post.url'>
        <b:attr name='b:whitespace' value='remove'/>
        <img>
          <!-- class --><b:class name='class-name'/>
          <!-- src --><b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, data:size, data:ratio) : data:post.featuredImage' name='src'/>
          <!-- srcset --><b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, [200,400,800,1200,1600], data:ratio) : data:post.featuredImage' name='srcset'/>
          <!-- sizes --><b:attr name='sizes' value='100vw'/>
          <!-- alt --><b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
          <b:attr name='b:whitespace' value='remove'/>
        </img>
      </a>
    </b:if>
  <b:else/><!-- fallback -->
    <a expr:href='data:post.link ?: data:post.url'>
      <b:attr name='b:whitespace' value='remove'/>
      <img>
        <!-- class --><b:class name='class-name'/>
        <!-- src --><b:attr expr:value='resizeImage("https://lh3.googleusercontent.com/kBzrgG0CUVwpWe8oT8iPxL8HhKQdNVj1AX5BR2Y0Q_zoSpxHGPRtcysgTJsb8ZEsYmbWoNm-nEOyjBc03w=w1920-h1080-rw-no", data:size, data:ratio)' name='src'/>
        <!-- srcset --><b:attr expr:value='resizeImage("https://lh3.googleusercontent.com/kBzrgG0CUVwpWe8oT8iPxL8HhKQdNVj1AX5BR2Y0Q_zoSpxHGPRtcysgTJsb8ZEsYmbWoNm-nEOyjBc03w=w1920-h1080-rw-no", [200,400,800,1200,1600], data:ratio)' name='srcset'/>
        <!-- sizes --><b:attr name='sizes' value='100vw'/>
        <!-- alt --><b:attr expr:value='data:messages.image' name='alt'/>
        <b:attr name='b:whitespace' value='remove'/>
      </img>
    </a>
  </b:if>
</b:with>
</b:with>
```

## CSS background-image

```html
<!-- Featured image -->
<b:with value='800' var='size'>
<b:with value='"16:9"' var='ratio'>
  <b:if cond='data:post.featuredImage'>
    <div class='class-name'><!-- target -->
      <b:if cond='data:post.featuredImage.isYoutube'>
        <!-- style --><b:attr expr:value='"background-image: url(" + (data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, data:size, data:ratio) : data:post.featuredImage.youtubeMaxResDefaultUrl) + ");"' name='style'/>
      <b:else/>
        <!-- style --><b:attr expr:value='"background-image: url(" + (data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, data:size, data:ratio) : data:post.featuredImage) + ");"' name='style'/>
      </b:if>
    </div>
  </b:if>
</b:with>
</b:with>
```

### CSS background-image with fallback

```html
<!-- Featured image -->
<b:with value='800' var='size'>
<b:with value='"16:9"' var='ratio'>
  <div class='class-name'><!-- target -->
    <b:if cond='data:post.featuredImage'>
      <b:if cond='data:post.featuredImage.isYoutube'>
        <!-- style --><b:attr expr:value='"background-image: url(" + (data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, data:size, data:ratio) : data:post.featuredImage.youtubeMaxResDefaultUrl) + ");"' name='style'/>
      <b:else/>
        <!-- style --><b:attr expr:value='"background-image: url(" + (data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, data:size, data:ratio) : data:post.featuredImage) + ");"' name='style'/>
      </b:if>
    <b:else/><!-- fallback -->
      <!-- style --><b:attr expr:value='"background-image: url(" + resizeImage("https://lh3.googleusercontent.com/kBzrgG0CUVwpWe8oT8iPxL8HhKQdNVj1AX5BR2Y0Q_zoSpxHGPRtcysgTJsb8ZEsYmbWoNm-nEOyjBc03w=w1920-h1080-rw-no", data:size, data:ratio) + ");"' name='style'/>
    </b:if>
  </div>
</b:with>
</b:with>
```
