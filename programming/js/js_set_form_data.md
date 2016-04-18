# JS: Form Helper

- *requires jquery*

### Set Form Data

```js
function setFormData($el, newVal){
  $el.find('[name]').each(function(){
    var $input = $(this);

    if(newVal[$input.attr('name')])
      $input.val(newVal[$input.attr('name')]).trigger('change');
  });
}
```

### Reset Form
```js
function resetForm($el, resetHidden){
	resetHidden = resetHidden || false;
	$el.find('[name]').each(function(){
		if( $(this).attr('type') != 'hidden' || (resetHidden && $(this).attr('type') == 'hidden') ){
			$(this).val('');
		}
	});
}
```