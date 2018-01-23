# viz_json

Data visualization in JSON format

## What is viz_json?

It's a way to organize data visualization in JSON format. Developers typically store data visualization inside JavaScript, HTML, CSS files. This project explores another option: Store data visualization in JSON format.

## Why use JSON for data visualization?

- Portability: If data visualization is stored in JSON format, we can just send each other the text to load data visualization. It can be integrated into any codebase, platform.
- Reusability: We can mix individual data visualizations into dashboard, swap them faster.

## Drawbacks

JSON format does come with a few drawbacks. It's hard to directly edit JavaScript, CSS, HTML. An editor like vida.io (https://vida.io) can help. Other suggestions? Please send me an email: dnprock@gmail.com.

## Format

Here's my format proposal:

```javascript
  var doc_json = {
    "javascript": "",
    "stylesheet": "",
    "html": "",
    "data": "",
  }
```

Here's an example code for loading this data visualization:

```javascript
  window.config = {};
  window.data = doc_json.data;

  var properties = doc_json.properties;

  properties.forEach(function(p) {
    window.config[p.name] = p.value;
  });

  $('#canvas').append($(doc_json.html));

  // load CSS
  var css = $('<style>' + doc_json.stylesheet + '</style>');
  $('body').append(css);

  var script = $('<script type="text/javascript">' + doc_json.javascript +'</script>');
  $('body').append(script);
```

## Example

Clone this repository and open index.html in browser.

## Suggestions

Please send me an email: dnprock@gmail.com.
