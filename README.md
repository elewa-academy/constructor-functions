## Constructor Functions

Important for reading mozilla documentation, but not the best practice for your own apps

Why avoid them?  because it's special syntax that hides what's really happening, and using 'new' makes your code less futur-proof. 

Constructing constructors.  When you use the new keyword in js this is how it really works.  it's got nothing to do with classes or the new keyword in other language.  these examples build from simple funciton to a constructor function:  


_What JS says is happening_:
  ```js
  function constructor(_own_prop) {
      // implicitly creates new object and sets __proto__
      // sets "this" to the new object
      this.own_prop = _own_prop;
      // implicitly returns the new object
  };
  var constructor.prototype.inherited_prop = 'yeee';
  var new_instance_3 = new constructor('yaaa');
  ```

_What's really happening_: 
  ```js
  function pseudo_constructor(_own_prop) {
      var new_obj = Object.create(factory_2.prototype);
      new_obj.own_prop = _own_prop;
      return new_obj;
  };
  var pseudo_constructor.prototype.inherited_prop =  'yeee';
  var new_instance_2 = pseudo_constructor('yaaa');
  ```



Constructors do not change prototypical inheritance, they're just a native implementation of a convenient design pattern.  Once an object has been created from a constructor you can always change it's \_\_proto\_\_ unlike instances in classical languages like ruby or python.  

___

### resources

* [great diagram](https://sangupta007.wordpress.com/2017/02/12/inheritance-tree-in-javascript/)
* [strange pseud-factory using constructors](https://carldanley.com/js-factory-pattern/)
* [in defence of constructors](http://2ality.com/2013/07/defending-constructors.html)

___
___
### <a href="http://elewa.education/blog" target="_blank"><img src="https://user-images.githubusercontent.com/18554853/34921062-506450ae-f97d-11e7-875f-6feeb26ad72d.png" width="100" height="40"/></a>

