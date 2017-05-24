## How to customize shopify theme

1. Goto https://myshopname.myshopify.com/admin/themes
2. Click on [...]
3. Edit HTML/CSS



## How to Edit Shopify home page
Use index.liquid

{{ content_for_index }} [1]

{% section 'your-section-area' %} *[2]

[1] Customize theme for default sections
[2] create section under the "Setions" folder


## How to add CSS and JS file in Shopify
```
{{ 'stylized.css' | asset_url | stylesheet_tag }}
  
<script src="{{ 'kodeized.js' | asset_url }}"></script>
```