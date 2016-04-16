# Handle AJAX Form Using Jquery

### Spec

This code meant to handle submission of ajax form, eliminating boilerplate code. 

- url of ajax will be form's action
- method of ajax will be form's method
- data of ajax will be form's data, serialized

To let the form handled by this code, it must have attribute `data-ajax-id`. Value of `data-ajax-id` will be name of the event. the name uses this pattern `ajax.{value-of-data-ajax-id}.{event-name}`. 

If a form element has attribute `data-ajax-id="invite-user"`, the handler will take over its submission and will trigger the following events:
- `ajax.invite-user.beforeSend`
- `ajax.invite-user.success`
- `ajax.invite-user.error`
- `ajax.invite-user.always` 

When the form processing reaches `beforeSend` event, handler will try to find an input or button which has `data-toggle-processing="true"` attribute, disable it and set its text to `Processing request..` to tell the user that the form is currently processing.

If you want to abort a request from inside `beforeSend`, you can call `xhr.abort()` from there and then call `$this.fn.hideProcessing()` to hide indicator for processing request.

### Client Side
*handler*
```js
// ajax form handler
$('form[data-ajax-id]').on('submit', function(e){

  e.preventDefault();

  $this     = $(this),
  $required = $(this).find('[required]'),
  hasEmpty  = false,
  ajaxId    = $this.data('ajax-id'),
  events    = {
    error       : 'ajax.' + ajaxId + '.error',
    success     : 'ajax.' + ajaxId + '.success', 
    always      : 'ajax.' + ajaxId + '.always',
    beforeSend  : 'ajax.' + ajaxId + '.beforeSend',
  };

  // toggle button to indicate processing request
  $toggleProcessing = $this.find('[data-toggle-processing="true"]'),
  originalText      = $toggleProcessing.text();

  // attach function to $this
  $this.fn = {
    showProcessing : function(){
      // toggle button to indicate processing request
      $toggleProcessing
        .text('Processing request..')
        .attr('disabled', 'disabled');
    },
    hideProcessing: function(){
      $toggleProcessing
        .text(originalText)
        .removeAttr('disabled');
    },
  };

  // check if value of any required input is empty
  $required.each(function(){
    if(!$(this).val().trim().length){
      alert($(this).attr('name') + ' can\'t be empty.');
      $(this).val('').focus();
      hasEmpty = true;
      return;
    }
  });

  // abort if value of any required input is empty
  if(hasEmpty) 
    return;

  $.ajax({
    method:$this.attr('method'),
    url   :$this.attr('action'),
    data  :$this.serialize(),
    beforeSend:function(xhr){
      // trigger beforeSend event,
      // you may hook to this event for data validation.
      // 
      // sample code to abort:
      // xhr.abort();
      // $el.fn.hideProcessing();
      var inputs = $this.serializeArray();
      $this.trigger(events.beforeSend, [xhr, $this, inputs]);
      $this.fn.showProcessing();
    },
    success:function(data){
      // trigger success event
      $this.trigger(events.success, [$this, data]);
      $this.fn.hideProcessing();
    },
    error:function(data){
      // trigger success event
      $this.trigger(events.error, [$this, data]);
      $this.fn.hideProcessing();
    },
    always:function(data){
      // trigger always event
      $this.trigger(events.always, [$this, data]);
    },
  });
});
```

*triggers*
```js
$('form')
  .on('ajax.invite-user.beforeSend', function(event, xhr, $el, inputs){
    return;
  })
  .on('ajax.invite-user.success', function(event, $el, data){
	if(data.error && alert(data.error))
  	return false;
    if(!data.error)
      // hide modal
      $('.modal').modal('hide');
  })
  .on('ajax.invite-user.error', function(event, $el, data){
    alert('error submitting request');
  });
```

### Server Side
- return json containing `error` key if there's error. value of `error` key is the error message