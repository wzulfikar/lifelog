# Programming

Most of the stuff here is basically my personal approach, which might not be best practice for you. Sometimes it just code snippets. 

Anyway, I'm open to any idea, suggestion or comment 😉

https://www.vividcortex.com/blog/2014/01/15/two-go-memory-leaks/

https://blog.rubylearning.com/best-practices-for-a-new-go-developer-8660384302fc#.q3yzzxiur

https://talks.golang.org/2013/bestpractices.slide#2

http://talks.golang.org/2014/go4gophers.slide#6

http://talks.golang.org/2012/splash.article

in golang, interface is instantiable

tour about interface: https://tour.golang.org/methods/10

http://stackoverflow.com/questions/11634809/twitter-bootstrap-focus-on-textarea-inside-a-modal-on-click

```go
// from https://tour.golang.org/methods/10
package main

import "fmt"

type I interface {
	M()
}

type T struct {
	S string
}

// This method means type T implements the interface I,
// but we don't need to explicitly declare that it does so.
func (t T) M() {
	fmt.Println(t.S)
}

func main() {
	var i I = T{"hello"}
	i.M()
}
```

```php
/**
 * Takes at least 2 arguments: truth test & output if the test passed.
 * If the args more than 2, the last arg will be the output if truth tests failed,
 * and the before-last arg will be the output if all truth tests passed.
 * 
 * @return mixed
 */
function coalesce(){
	$numArgs = func_num_args();
	if($numArgs < 2)
		throw new \Exception('insufficient args, should be at least 2 instead of 1');

	if( $numArgs < 3)
		return func_get_args()[0] ? func_get_args()[1] : null;

	$args   = func_get_args();
	$output_false = array_pop($args);
	$output_true  = array_pop($args);
	
	foreach ($args as $truth) {
		if(!$truth) return $output_false;
	}

	return $output_true;
}
```

```php
/**
 * generate random str consists of 
 * name of color, 4 digits int and a character.
 *
 * eg. bronze1459!, silver9627?, gold7062$, lemon4824!
 * 
 * @return string
 */
function random_str()
{
  $colors = [ 
    'blue', 'bronze', 'brown', 'cream', 'cyan', 'gold', 'green', 'lemon', 'lime', 'magenta', 'maroon', 'orange', 'pink', 'purple', 'rose', 'rust', 'silver', 'violet', 'white' 
  ];

  $chars = ['!', '?', '$', '*'];

  $color = $colors[random_int(0, count($colors) - 1)];
  $digit = random_int(1000, 9999);
  $char  = $chars[random_int(0, count($chars) - 1)];
  
  return $color . $digit . $char;
}
```