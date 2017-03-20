# Pocket
> Wed, 15 Mar 2017 at 12:45:45 MYT

- pick up on how they think about problems
- There’s simply no real substitute for physical presence.
- Better to spend 15 focused, responsive minutes than 30 utterly distracted ones.
- "But I can tell you that I’m even more tightly bonded with her now, and that’s not because of some orchestrated, contrived effort to plumb her emotions. It’s because I was present. It’s because I was there."

# What's next in computing
> by Chris Dixon and Learn, medium.com
Feb 21, 2016

—
- historically, about every 10 to 15 years — major new cycles begin that completely reshape the computing landscape.
- Each product era can be divided into two phases: 1) the gestation phase, when the new platform is first introduced but is expensive, incomplete, and/or difficult to use, 2) the growth phase, when a new product comes along that solves those problems, kicking off a period of exponential growth.
- “The business plans of the next 10,000 startups are easy to forecast: Take X and add AI. This is a big deal, and now it’s here.” — Kevin Kelly
- AI systems get better as more data is collected, which means it’s possible to create a virtuous flywheel of data network effects (more users → more data → better products → more users)
- Deep learning software tools have gotten so good that a solo programmer was able to make a semi-autonomous car

# Laravel
- The system timezone setting in the app.php config file sets the ***PHP session timezone*** on each page load.
- to set mysql timezone, add `timezone` key for your db connection inside `config/database.php`

# SHA-1
> http://www.theverge.com/2017/2/23/14712118/google-sha1-collision-broken-web-encryption-shattered

- SHA-1 is a hashing function, which produces a digital fingerprint from a given file
- the hash is particularly important for login systems, which need to verify that a password is correct without exposing the password itself

## What's collision?
A collision is what happens when a hashing function breaks, and two files produce the same hash. That could allow an attacker to smuggle in a malicious file because it shares its hash with a legitimate file.

In practical terms, a broken hash function could be used to break HTTPS, the encryption system that now protects more than half the web.

Cryptographers have been predicting a collision like this for years, making ever more specific predictions about how you’d produce one and how much computing power it would take.

# JS: Classes & Prototypal Inheritance
> Wed, 15 Mar 2017 at 13:46:31 MYT
> https://t.co/O4Wp5MQBDK

- Unlike most other languages, JavaScript’s object system is based on prototypes, not classes.
- Classes as you may know them from languages like Java don’t technically exist in JavaScript
- In JavaScript, class inheritance is implemented on top of prototypal inheritance
- class inheritance causes many well known problems in OO design:
    1. The tight coupling problem
    2. The fragile base class problem
    3. Inflexible hierarchy problem
    4. The duplication by necessity problem
    5. The Gorilla/banana problem

> **The Gorilla/banana problem:**
> What you wanted was a banana, but what you got was a gorilla holding the banana, and the entire jungle.

To avoid problems causes by class inheritance:

> “Favor object composition over class inheritance.”~ The Gang of Four

- When you inherit from a class, you get everything, even if you don’t want it.
- ***Concatenative inheritance:*** The process of inheriting features directly from one object to another by copying the source objects properties. In JavaScript, source prototypes are commonly referred to as ***mixins***.
- ***Functional inheritance:*** In JavaScript, any function can create an object. When that function is not a constructor (or `class`), it’s called a factory function. 
- Factory functions: functions which exist to create object instances

> *Common issue with class inheritance:*
> Class `A` and `B` contain unrelated features needed by both `C` & `D`. `D` is a new use case, and needs slightly different behavior in `A`’s init code than `C` needs. 
> 
> So the newbie dev goes and tweaks `A`’s init code. `C` breaks because it depends on the existing behavior, and `D` starts working.

“…the problem with object-oriented languages is they’ve got all this implicit environment that they carry around with them. You wanted a banana but what you got was a gorilla holding the banana and the entire jungle.” ~ Joe Armstrong — “Coders at Work”

# The Single Biggest Mistake Programmers Make Every Day
> by Eric Elliott, medium.com | Nov 5, 2015
> https://medium.com/javascript-scene/the-single-biggest-mistake-programmers-make-every-day-62366b432308

- A pure function does not mutate anything outside itself. A pure function does not produce side effects. Given the same inputs, a pure function will always return the same output.
- "I believe the single biggest mistake that every programmer makes from time to time is overcomplicating things." – Eric Elliot
- The best way to make things easy is to keep your code simple, as in Do One Thing (DOT)
- An advice often attributed to Kent Beck, author of “Test Driven Development By Example”:
  - Make it work
  - Make it right
  - Make it fast
- "During the unit tests, I decide what I mean by “make it work”. What are the minimum requirements that the solution needs to satisfy?" – Eric Elliot
- In agile development, we strive to implement the minimum effective amount of process to enable high velocity development.
- ***Start small and iterate:*** Write a test. Make it pass. Refactor. Make it work. Make it right. Make it fast. One step at a time. Keep taking those steps until the job is done.
- The essence of a function is to take some data as input and produce some data as output, eg. `foo(...inputs) => output`
- In JavaScript, ***arrays and objects are passed by reference***, so if you mutate array or object parameters, it doesn’t just affect the variable inside the function. It also affects any other function that uses a reference to the same variable.
- In programming lingo, the mutation of `a` is referred to as a side-effect.
- Side effects are not obviously visible, so when they cause a bug, it can potentially be hard to trace

---
> http://www.bbc.com/news/technology-38755584

- "Today you cannot talk about ransomware without mentioning Bitcoin because that's what made this evolution come," said Anton.
- Now, many groups writing ransomware run it as a service. 

> "They will give you the software with your affiliate ID so if you spread it they will know that it's from you and you will get a payout," he said. "You will get 70% and they will get the 30% out of each payment."

---

Programmatically access Google Spreadsheet: https://www.twilio.com/blog/2017/03/google-spreadsheets-and-php.html
