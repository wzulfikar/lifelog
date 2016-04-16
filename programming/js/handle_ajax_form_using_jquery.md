# Handle AJAX Form Using Jquery

This code meant to handle submission of ajax form : eliminating boilerplate code, and for convenient – if you think so :v

### Spec
Put the *handler* in – for example, your layout page or your `helper.js` if you've one and put the *hooks* together with your ajax form.

- url of ajax will be form's action
- method of ajax will be form's method
- data of ajax will be form's data, serialized

To let the form handled by this code, it must have attribute `data-ajax-id`. Value of `data-ajax-id` will be name of the event. The name has this pattern:

`ajax.{value-of-data-ajax-id}.{event-name}`. 

So, if a form has attribute `data-ajax-id="invite-user"`, the *handler* will automatically handle the submission and will trigger these events:
- `ajax.invite-user.beforeSend`
- `ajax.invite-user.success`
- `ajax.invite-user.error`
- `ajax.invite-user.always` 

When the form processing reaches `beforeSend` event, handler will try to find an input or button which has `data-toggle-processing="true"` attribute, disable it and set its text to `Processing request..` to tell the user that the form is currently processing.

If you want to abort a request from inside `beforeSend`, you can call `xhr.abort()` from there and then call `$this.fn.hideProcessing()` to hide indicator for processing request.

Except `beforeSend`, all events sends these arguments: `event, $el, data`. For `beforeSend` event, it sends `event, xhr, $el, inputs`. 

The `beforeSend` event has `xhr` arg so that the request can be aborted, and `inputs` arg so that request data can be validated before sending the request.

>the value of `inputs` in `beforeSend` is from `.serializeArray()`

Regardless of the events triggered, you don't need to hook all the events. However, you need to handle at least `ajax.{ajax-id}.success` and `ajax.{ajax-id}.error` events to give a good feedback for your users.

### Client Side
#### *Handler*
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
  
  // here is where we send the form, actually
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
      // trigger error event
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

####*Hooks*
```js
$('form')
  .on('ajax.invite-user.beforeSend', function(event, xhr, $el, inputs){
    return;
  })
  .on('ajax.invite-user.success', function(event, $el, data){
	if(data.error && alert(data.error))
  	return false;
    if(!data.error)
      // hide modal, if the form is in bootstrap modal
      $('.modal').modal('hide');
  })
  .on('ajax.invite-user.error', function(event, $el, data){
    alert('error submitting request');
  });
```

### Server Side
In my use, the code in the server will return json containing `error` key if there's error. the value of `error` key is the error message. That's why I put

```js
if(data.error && alert(data.error))
      return false;
```

in the *triggers* code.