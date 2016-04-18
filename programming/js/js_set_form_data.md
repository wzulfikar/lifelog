# JS: Form Helper

- *jquery is required*

```js
var FormHelper = function($form) {
  this.form = function(){
    return $form;
  };
  
  this.reset = function(resetHidden) {
    resetHidden = resetHidden || false;
    if (resetHidden)
      $('[name]').val('').trigger('change');
    else
      $('[type!="hidden"][name]').val('').trigger('change');
    
    return $form;
  }

  this.set = function(values) {
    $form.find('[name]').each(function() {
      var $input = $(this);

      if (values[$input.attr('name')])
        $input.val(values[$input.attr('name')]).trigger('change');
    });
    
    return $form;
  };
};
```