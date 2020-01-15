# CSS Grid Project Installation

This is a base project displaying mutliple css grid versions, hey if you are curious play around with Craft CMS!

## Install instructions

5. run `composer install`
6. `cp .env.example .env`
7. run `./craft setup/index`
6. run `npm install`
7. run `npm run dev`

   
### Production build
run `npm run build` if you are ready for production, this will minify the javascript and css files.
   
## Starting instructions
If you create a new page on the back-end of craft, whether is a single page or a structure you can start with the code below.
* Example of the filename `pages/_entry.twig`

```twig
{% extends 'layouts/_master' %}

{% block content %}

      {# content comes here #} 

{% endblock %}
```

## Additional information

#### VueJS
* VueJs is already standard in the boilerplate, if you want to make use of it, follow the following steps:
* Inside app.js
```
import Vue from 'vue'

new Vue({
    el: [targetElement]
});
```
* Inside JS folder
    * create components folder
    * create `.vue` files
* In the `.vue` files you can also access the global variables from your scss files, if you want to add or change this go into `webpack.common.js` and configure the `configureCssLoader()`

#### Jquery
* If you want to use Jquery on your project (which i don't recommend), follow the steps below
* All these changes are in the `webpack.common.js`

```javascript
// At the top of the file add the webpack variable
const webpack = require('webpack'); 

// Inside the plugins add the following plugin, 
// Add this below the CopyWebpackPlugin
new webpack.ProvidePlugin({
    $: 'jquery',
    jQuery: 'jquery'
})
```

# css-grid-with-craft
