# Laravel Nested Query in Eloquent

```php
$challenge = $this->challenges()
        ->where('open', true)
        ->where(function($q) use ($user_id, $opponent_id) {
            $q->where(function($query) use ($opponent_id, $user_id){
                    $query->where('player_1', $user_id)
                          ->where('player_2', $opponent_id);
                })
              ->orWhere(function($query) use ($opponent_id, $user_id) {
                    $query->where('player_1', $opponent_id)
                          ->where('player_2', $user_id);
                });
            })
        ->first();
```