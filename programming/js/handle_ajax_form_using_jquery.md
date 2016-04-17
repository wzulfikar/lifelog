# Handle AJAX Form Using Jquery

This code meant to handle submission of ajax form : eliminating boilerplate code, and for convenient – if you think so :v

### Installation
- bower
- download source code

### Usage
```js
$('form')
  .on('ajax.invite-user.success', function(event, $form, data){
	
  if(data.error && alert(data.error))
    return false;

  if(!data.error)
    // hide modal
    $('.modal').modal('hide');

  });
```

### Spec
Put the *form handler* in – for example, your layout page or your `helper.js` if you've one and put the *hooks* together with your ajax form.

- url of ajax will be form's action
- method of ajax will be form's method
- data of ajax will be form's data, serialized

To let the form handled by this code, it must have attribute `data-ajax-id`. Value of `data-ajax-id` will be name of the event. The name has this pattern:

`ajax.{value-of-data-ajax-id}.{event-name}`. 

So, if a form has attribute `data-ajax-id="invite-user"`, the *form handler* will automatically handle the submission and will trigger these events:
- `ajax.invite-user.beforeSend`
- `ajax.invite-user.success`
- `ajax.invite-user.error`
- `ajax.invite-user.always` 

When the form processing reaches `beforeSend` event, handler will try to find an input or button which has `data-toggle-processing="true"` attribute, disable it and set its text to `Processing request..` to tell the user that the form is currently processing.

If you want to abort a request from inside `beforeSend`, you can call `$form.fn.abort(xhr)` from there.

Except `beforeSend`, all events sends these arguments: `event, $el, data`. For `beforeSend` event, it sends `event, xhr, $el, inputs`. 

The `beforeSend` event has `xhr` arg so that the request can be aborted, and `inputs` arg so that request data can be validated before sending the request.

>the value of `inputs` in `beforeSend` is from `.serializeArray()`

Regardless of the events triggered, you don't need to *hook* all the events. However, you need to *hook* at least `ajax.{ajax-id}.success` and `ajax.{ajax-id}.error` events so your users can receive a good feedback from your ajax form.

### Client Side
#### *Form Handler*
```js
(function($){
// ajax form handler
$('form[data-ajax-id]').on('submit', function(e){

  e.preventDefault();

  $form     = $(this),
  $required = $form.find('[required]'),
  ajaxId    = $form.data('ajax-id'),
  hasEmpty  = false,
  events    = {
    error       : 'ajax.' + ajaxId + '.error',
    success     : 'ajax.' + ajaxId + '.success', 
    always      : 'ajax.' + ajaxId + '.always',
    beforeSend  : 'ajax.' + ajaxId + '.beforeSend',
  };

  // toggle button to indicate processing request
  $toggleProcessing = $form.find('[data-toggle-processing="true"]'),
  originalText      = $toggleProcessing.text();

  // attach custom functions to $form
  $form.fn = {
    redirect:function(url){
      window.location.replace(url);
    },
    processing:{
      show:function(){
        $toggleProcessing
          .text('Processing request..')
          .attr('disabled', 'disabled');
      },
      hide:function(){
        $toggleProcessing
          .text(originalText)
          .removeAttr('disabled');
      },
    },
    alert: {
      success:function(msg){
        alert(msg);
      },
      error:function(msg){
        alert(msg);
      }, 
    }
  };

  // check if value of any required input is empty
  $required.each(function(){
    if(!$(this).val().trim().length){
      $form.fn.alert.error($(this).attr('name') + ' can\'t be empty.');
      $(this).focus();
      hasEmpty = true;
      return;
    }
  });

  // abort if value of any required input is empty
  if(hasEmpty) 
    return;
  
  // here is where we send the form, actually
  $.ajax({
    method:$form.attr('method'),
    url   :$form.attr('action'),
    data  :$form.serialize(),
    beforeSend:function(xhr){
      // trigger beforeSend event,
      // you may hook to this event for data validation.
      // 
      // sample code to abort:
      // xhr.abort();
      // $form.fn.processing.hide();
      
      $form.fn.processing.show();

      var inputs = $form.serializeArray();
      $form.trigger(events.beforeSend, [xhr, $form, inputs]);
    },
    success:function(data, textStatus, jqXHR){
      // trigger success event
      $form.trigger(events.success, [$form, data]);

      $form.fn.processing.hide();
    },
    error:function(jqXHR, textStatus, errorThrown){
      var msg = 'Error ' + jqXHR.status + ' : ' + errorThrown + '.';
      
      $form.fn.alert.error(msg);

      // trigger error event
      $form.trigger(events.error, [$form, jqXHR]);
      $form.fn.processing.hide();
    },
  });
});
}(jQuery));
```

####*The Hooks*

The form object handled by *form handler* code is accessible in all events, using `$form` variable. 

```js
$('form')
  .on('ajax.invite-user.beforeSend', function(event, xhr, $form, inputs){
    // you may validate form inputs here;
  })
  .on('ajax.invite-user.success', function(event, $form, data){
	if(data.error && alert(data.error))
  	return false;
    if(!data.error)
      // hide modal, if the form is in bootstrap modal
      $('.modal').modal('hide');
  })
  .on('ajax.invite-user.error', function(event, $form, data){
    alert('error submitting request');
  });
```

### Server Side
In my use case, the code in the server will return json containing `error` key if there's error. the value of `error` key is the error message. That's why I put

```js
if(data.error && alert(data.error))
      return false;
```

in *the hooks* code.