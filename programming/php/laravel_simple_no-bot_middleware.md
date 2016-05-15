# Laravel Simple No-Bot Middleware

this is how i failed my one-time login link, bcause my lack of knowledge in handling bot mechanism. my current solution is to use no-bot middleware, something like this:

```php
public function handle($request, Closure $next)
{
  if(stripos($_SERVER['HTTP_USER_AGENT'], 'bot') !== false){
    abort(406, 'bot not allowed');
  }

  return $next($request);
}
```