# Let's code to interface. But why?

interface php
http://pastebin.ca/2088573

loosely coupling code
http://stackoverflow.com/questions/383947/what-does-it-mean-to-program-to-an-interface

class Horse {

}

class Human {

}

class Table {

}

interface CanEat{
    function eat();
}


$horse = new Horse();

$human = new Human();

function eat(){

}

Horse, human and table are concrete classes here.


Basically, interface is a contract. Abstract class.

Using abstract class == easily swappable.