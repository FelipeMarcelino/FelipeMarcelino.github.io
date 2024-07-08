# Data Class as Code Smell
#python #programming #codesmell

- Code smell is a code that sniff and sometimes can be easily detected
- Data class are classes with some implementation already done
- If you are done a lot of code and reimplementing things, you are doing something wrong.
- Or class has the behavior or methods dealing with it outside it scope we have some way to fix it
	- Data Class as Scaffolding: Class becomes independent, gets its own module and methods
	- Data class as intermediate representation: The data of the class is immutable objects extract from JSON
	  files and need to be pass to between systems. If you need to change, construct your own builders. You can
	  use `dict` and `**` to create this object. In case of change, as mentioned before, other builders.

### References
- Ramalho, 2022, p190-196
