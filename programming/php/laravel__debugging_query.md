# Laravel : Debugging Query

    \DB::enableQueryLog();
    
    // do the query
    $calItems = CalItem::whereRaw(...)->get();

    $queries = \DB::getQueryLog();
    $last_query = end($queries);
    
    // see the query
    dd($last_query);