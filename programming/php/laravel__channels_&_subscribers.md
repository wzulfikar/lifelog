# Laravel : Channels & Subscribers

```php
<?php

namespace App\Models;

use Closure;

class Channel extends BaseModel
{
	public function subscriptions()
	{
	  return $this->hasMany(Subscription::class);
	}

	public function getSubscribersAttribute()
	{
		return User::whereIn('id', $this->subscriptions->lists('user_id'))
							 ->get();
	}

    public function broadcast(Closure $func)
    {
      return $func($this->subscribers, $this);
    }
}
```

```php
<?php

namespace App\Models;

class Subscription extends BaseModel
{
	public function channel()
	{
	  return $this->belongsTo(Channel::class);
	}	

	public function user()
	{
	  return $this->belongsTo(User::class);
	}
}

```

```php
trait Subscriber
{
  public function subscriptions()
  {
    return $this->hasMany(Subscription::class);
  }

  public function getSubscribedChannelsAttribute()
	{
	  return Channel::whereIn('id', $this->subscriptions->lists('channel_id'))
	  					 		->get();
	}

	public function subscribe(Channel $channel)
	{
		$subscription             = new Subscription;
		$subscription->user_id    = $this->id;
		$subscription->channel_id = $channel->id;

	  if($subscription->save()){
	  	return true;
	  }

	  return false;
	}
    
    public function unsubscribe(Channel $channel)
	{
	  $subscriptions = $this->subscriptions->where('channel_id', $channel->id)->first();
	  return $subscriptions->delete();
	}
    
    public function subscribedTo(Channel $channel)
	{
	  return $this->subscriptions->where('channel_id', $channel->id)->first();
	}
}
```

```php
// broadcasting message to subscribers
$channel = Channel::first();
$channel->broadcast(function($subscribers) use ($command, $arg){
  foreach ($subscribers as $key => $subscriber) {
    $msg    = "Hi " . $subscriber->name . "!";
    $messenger->sendTo($subscriber->chatId, $msg); 
  }
});
```

```php
// subscribing channel
// User model must use Subscriber trait
$channel = Channel::first();
auth()->user()->subscribe($channel);
```