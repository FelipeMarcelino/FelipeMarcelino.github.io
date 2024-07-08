# self.__init__ and hash tables
#python #efficiency #programming #language

- A class is store in hash table
- Instance variables and classes variables shared small space on the memory

> [!tip] Performance
> Avoid create attribute outside of method `self.__init__` because a new hash table is necessary.
> It make the program to use almost 10%-20% less memory
