Analytics.js
============

Google analytics event tracking module with support for both classic and universal analytics code.

### Requirements
Requires jQuery to be loaded in the page.
Requires the async version of the Google Analytics to be loaded in the page. See the tracking code quickstart for more infomation:
https://developers.google.com/analytics/devguides/collection/gajs/

### Install
git clone https://github.com/lodalo/Analytics.js.git analytics

### Basic setup

Just add a data-analytics attribute to a container containing links you want to track. Every link in that container will be tracked using the default category (uri), default action (click), and default label (href).

```html
<div data-analytics>
  <ul>
    <li><a href='/'>Home</a></li>
    <li><a href='/about-us/'>About us</a></li>
    <li><a href='/contact-us/'>Contact us</a></li>
  </ul>
</div>
```

Initialise GA once jQuery is ready.

```javascript
$(document).ready(function() {
    GA.init();
});
```

### Custom tracking

For more targeted tracking you can specify a category, action or value by populating the data-analytics attribute with pipe separated values.

E.g. Use custom category, custom action and a custom label
```html
<a data-analytics='Top navigation|Link click|Homepage link' href='/'>Home</a>
```

E.g. Use custom label only
```html
<a data-analytics='||Homepage link' href='/'>Home</a>
```

E.g. Use custom action only
```html
<a data-analytics='|Slide Next' href='#'>Next</a>
```

E.g. User custom category and custom value only
```html
<a data-analytics='UI Elements||Show data' href='#'>Show</a>
```

E.g. Custom track a group of elements with custom category and action
```html
<div data-analytics='Top navigation|Link click'>
  <ul>
    <li><a href='/'>Home</a></li>
    <li><a href='/about-us/'>About us</a></li>
    <li><a href='/contact-us/'>Contact us</a></li>
  </ul>
</div>
```

### Tracking dynamically

You can track within a JavaScript file by calling the track method:

```javascript
GA.track(label, category, action); // Specify a label, category and action.
GA.track(label); // Specify only a label - will use default category and action.
GA.track(label, category, action, value); // Specify a label, category, action and value.
```




