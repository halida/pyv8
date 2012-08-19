PyV8 is a python wrapper for Google V8 engine, it act as a bridge between the Python and JavaScript objects, and support to hosting Google's v8 engine in a python script.

```python
>>> import PyV8
>>> ctxt = PyV8.JSContext()          # create a context with an implicit global object
>>> ctxt.enter()                     # enter the context (also support with statement)
>>> ctxt.eval("1+2")                 # evalute the javascript expression
3                                    # return a native python int
>>> class Global(PyV8.JSClass):      # define a compatible javascript class
...   def hello(self):               # define a method
...     print "Hello World"    
...
>>> ctxt2 = PyV8.JSContext(Global()) # create another context with the global object
>>> ctxt2.enter()                    
>>> ctxt2.eval("hello()")            # call the global object from javascript
Hello World                          # the output from python script
```

Please check the [unit tests](https://github.com/flier/pyv8/blob/master/PyV8.py) for more detail.

Please check the [change history](http://code.google.com/p/pyv8/wiki/ChangeHistory) for the lastest v0.9 version.

ps: [lkcl](http://www.advogato.org/person/lkcl/) has finished [a similar binding example](http://www.advogato.org/article/985.html).
