# JS: Set Form Data

```js
function setFormData($el, newVal){
  $el.find('[name]').each(function(){
    var $input = $(this);

    if(newVal[$input.attr('name')])
      $input.val(newVal[$input.attr('name')]).trigger('change');
  });
}
```