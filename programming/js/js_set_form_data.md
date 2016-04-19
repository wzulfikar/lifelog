# JS: Form Helper

- *jquery is required*

```js
(function($){
$.fn.formHelper = function($form) {
  
  this.reset = function(resetHidden) {
    resetHidden = resetHidden || false;
    if (resetHidden)
      $form.find('[name]').val('').trigger('change');
    else
      $form.find('[type!="hidden"][name]').val('').trigger('change');
    
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
  
  return $form;
};
  
}(jQuery));

var person1 = $.fn.formHelper($('[action="test"]'));

person1.reset();
```