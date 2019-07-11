## How to customize shopify theme

1. Goto https://myshopname.myshopify.com/admin/themes
2. Click on [...]
3. Edit HTML/CSS



## How to Edit Shopify home page
Use index.liquid

```javascript```
{{ content_for_index }} [1]
```javascript```
[1] Customize theme for default sections


```javascript```
{% section 'your-section-area' %} *[2]
```
[2] create section under the "Setions" folder






## How to add CSS and JS file in Shopify
```html
{{ 'stylized.css' | asset_url | stylesheet_tag }}
  
<script src="{{ 'kodeized.js' | asset_url }}"></script>
```





## How filter product in shopify

```javascript```
{% for collection in collections %}
    
    <!--a href="{{ collection.url }}">More {{ collection_title }} &rsaquo;</a-->
    {% for product in collection.products limit:5 %}
      {% assign grid_item_width = 'large--one-fifth medium--one-half' %}
  
     {% if product.type == 'myproducttypename' %}
 	   
      <div class="product-box col-md-2">
        <h2>{{ product.type | handle }}</h2>      
        
        <a href="{{ product.url | within: collection }}">{{ product.title }}</a>
        {{ product.price | money }} 
        {% unless product.available %}<br><strong>sold out</strong>{% endunless %}
        <a href="{{ product.url | within: collection }}">
          <img src="{{ product.featured_image.src | img_url: 'large' }}" alt="{{ product.featured_image.alt | escape }}">
        </a>
      </div>
  
  {% else %}
  	NOT FOUNDED
  {% endif %}
  
  {% endfor %}
  
{% endfor %}
```

#### Display product type

```javascript```
	{{ product.type | handle }}
```

NOTE: must use in ```for``` loop.