#Life Log
*https://www.gitbook.com/book/wzulfikar/lifelog*

Sometimes, I want to share things. Workplace, learning process, life as developer, personal experiences, etc. 

Well, actually what I really want is to leave legacy. Because `“You Only Live Once”` 😁


# Java MVC Demo

- create dynamic web project
- create new package named `mvc_demo`
- copy content of `mvc_demo` from this repo to your package `mvc_demo`
- copy `person.jsp` to your `WebContent` directory
- visit `/Person`

### Flow
- [View ➜ Controller] User visit `/Person` & `PersonController` handles the request 
- [Controller ➜ Model] `PersonController` tries to *create* new person object based on `Person` model 
- [Controller ➜ View] `PersonController` send the response to user, passing a `person` object
- [View] `person.jsp` display the response

### Convention
Uses common convention,

- Name of class uses `upper-camel-case` letter
  - class *person* should be `Person`, not `person`.
  - class *old person* should be `OldPerson`, not `oldPerson` or `old_person`
- Instance of class uses `camel-case` letter
- Name of method uses `camel-case` letter
  - method *eat cake* should be `eatCake()`, not `EatCake()` or `eat_cake()`
- Name of controller always suffixed with `Controller`. 
  - Class for person controller should be named `PersonController`
- Model is just plain java class

### Want to code?

If you're interested to code using the approach implemented in this repo, here is the scenario you can try.

>*Say, you want to access `/Student`, pass some parameter and then display info about student based on parameter.*

This is what we need to do above scene:

- **a model for our student object**

  create new file `Student.java` inside `mvc_demo`. the content is:

```java
package mvc_demo;

public class Student {
	private String name;
	private String id;

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

	public String getId() {
		return id;
	}

	public void setId(String id) {
		this.id = id;
	}
}
```

- **a controller for student**
  - create new servlet named `StudentController`, make `BaseController` its superclass and tell it to handle request from `Student` instead of `StudentController`. your class declaration should look like this:
  ```java
  @WebServlet("/Student")
  public class StudentController extends BaseController {
  // ...
  ```
  - modify `doGet` method in `StudentController` to become like this:
```java
protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
      // execute doGet method in parent class
      super.doGet(request, response);
	
      // create new student
      Student student  = new Student();
      student.setId(request.getParameter("id"));
      student.setName(request.getParameter("name"));
	
      // set data for the view
      view.set("student", student);
	
      // render the view
      view.render("/student.jsp");
}
```

- a jsp for the view. in this case, we'll name it `student.jsp`. put this file in your WebContent directory.

  ```html
  <!-- body of student.jsp file -->
  <body>
  You're a student.<br/>
  Your id is ${student.id},<br/>
  And your name is ${ student.name }
  </body>
  ```

- lastly, start the server & see the difference when you access `/Student` and `Student?name=herp&id=1234`