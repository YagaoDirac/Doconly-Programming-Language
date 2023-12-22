Basic conceptions

I assume all users have at least some basic idea of programming language. 

1, How the source code is compiled.(can be ignored safely.)

In doconly, the source code is first trans-compiled into cpp code, and then, everything is the same as normal cpp code. The compiler keeps track of the corresponding relationship between doconly code and cpp code, and maps everything from the debug system of cpp, back into original doconly code. If, if any compiler is implemented. But according to the specification, there's no compiler.

Doconly code contains 2 phases, compile command and executing code. The compile command helps control the behavior of IDE, and compiler. The executing code is to be converted and stored in a binary executable file.
Except for controlling the compiling behavior, compile command also deal with the behavior of automatic completion/input hint, and changes the default language feature.



2, Type system.(can be ignored safely.)

The type system consists of 2 layers, the struct and memory model.
Some quick examples:
a:int32 = 0 //the struct of a is int32, the memory model is left value.
b:some_struct = () //the struct of b is some_struct, the memory model is unique_ptr.
show_type(a) // int/left value.
show_type(b) // some_struct/unique_ptr
show_type(42) // int32/instant value
show_type(cc.to_instant_value(a)) // int32/instant value. cc means compile command.
c:some_struct/share_ptr = () //the struct of c is some_struct, the memory model is share_ptr.
show_type(c) // some_struct/share_ptr



3, Customized structure, and behavior bonding.(can be ignored safely.)






