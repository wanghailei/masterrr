# Module



As with class methods, you call a module method by preceding its name with the module’s name and a period, like `ActiveSupport.run_load_hooks(:active_record, Base)`

Module constants are referenced using the module name followed by two colons, which is called the scope resolution operator

A module can’t have instances, because a module isn’t a class. &#x20;

You can `include` a module within a class definition. When this happens, all the module’s instance methods are suddenly available as instance methods in the class as well. This si called mixin.
