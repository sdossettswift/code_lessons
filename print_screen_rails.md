Printing the Screen in Rails

### GOALS
Add a print button to rails app to allow user to print the active page. 

## Add A Link to A Separate Stylesheet
```html
stylesheet_link_tag('default', :media => :screen)
stylesheet_link_tag('print', :media => :print
```
## Customize Print Stylesheet
- serif fonts easier to read when printed
- limit images
- remove ads
- hide navigation bar, etc. 
- be mindful of color 
- include URLs for links 

```
a: after {content: '[' attr(href)']'}
```

## Add a Link 
```
<%= link_to "Print", '#', onclick: "printpage()"%>
```
### application.js
```js
function printpage() {
  window.print()
}
```
