Keywords( or literally, keyChar)

Doconly only has 7 keywords. Each of them is a single English character. They are:
e, s, f, h, c, v, b.
The meaning:
e for environment settings
s for shortcut
f for function
h for help from ide
c for compiler command
v for variable.
b for branch

Any expressions start with either a keyword, a variable(including function), some way to start a comment, or one of these operators:
Address operators: * &, the same as in cpp, same as v.deref and v.getaddr
Unary operators:- ~,
- for negetive. same as v.negetive or v.arith.neg
~ for bitwise not. same as v.bit_not
{ curly braces, when start a scope.

Notice, all the 7 keywords works the same as variables. They share the same syntax of a.b or a.b()

(Agreement: by a "name", I mean anything A-Za-z0-9_)
Between 2 names, only the following are possible:
. (a.b or a.b())
( (a.b() or function_name())
{ (something{something else}, but it's basically an individual scope.)
[ (same as .__index(), only a sugar)
: (only for some_array[start:end:stride]. Maybe I should replace this with something else.)



The following part is examples, enjoy.



eg 1, defining variables.

v.def("a")(int32/left_value)//I know it's too long for defining a variable
v a int32//The short version. They are the same.
//if you call h.show_type(v), it's a keyword namespace.
//if you call h.show_type(v.def("a")), it's keyword v.def half done object
v str = //comment as string literal
h.print(str)//comment as string literal
h.print(str[0])//c
v.recycle(str)//The end of str
v.recycle(a)//The end of a



eg 2, environment.

e.def("__DEBUG__")
e.ifdef("__DEBUG__")
e.else
e.endif
e.import(std, std) or e.import("std", "std") e.import("std").as("std")//which means, import std as std



eg 3, branch.

b.for// I'm not sure about b.for{v int i=0}{i<10}{i++}{ loop body }
b.unroll(3)//
b.while
//Now multiple example:
b.if a>1{
  b.likely//or simply omit this line
  h.print("a>1")
}
b.else{
  b.unlikely//or simply omit this line
  h.print("a<=1")
}

if a<1{}else{} 
is the same as 
b.if(a<1){}
b.else{}

if.s(value1, condition, value2)//s means short. I stole this from python.



eg 4, compiler command.

c.set_default_syntax.dynamic_type()
c.mem_align_push(4)
c.mem_align_pop

c.struct.def("some_class"){}
c some_class{}

c.struct.def("some_class"){
  v a int32
  f.def("get_a")()(int32){
    return a
  }
  v b int32
  v c int32
}
c.struct.get("some_class").get_var("a").set_const().remove_from_hint()
c.struct.get("some_class").get_var("b").hint_promoted()
c.struct.get("some_class").get_var("c").hint_demoted()

c.var("struct_list") = c.struct.get_all()
c.show_type("struct_list")//Idk now.
b.foreach(key, value).in(struct_list){
  b.if(key == "some_class"){
    b.foreach(name, _).in(value.get_all_members()){
      print(name)
    }
  }
}



eg 5, function.

f.def("one_more_func")()(){
  print("from one more func")
}
//is the same as
f one_more_func()(){
  print("from one more func")
}
c.struct.get("some_class").add_f("one_more_func")//this function is added into some_class, with a hidden some_class/inout as the first param.

f.s("short_func")(a_number int32)->a_number*a_number



eg 6, help.

h.gen_ctor_set("for_this_struct")//then, right click on this line, select "do compiler command"
//then you get:
c.struct.def("for_this_struct"){
  f.ctor.default(){...}
  f.ctor.from_param(){...}
  f.ctor.from_left_value(from for_this_struct/inout){...}
  f.ctor.from_instant_value(from for_this_struct/in){...}
  f.op_overload("=").from_left_value(from for_this_struct/inout)(out for_this_struct ){... return *this}
  f.op_overload("=").from_instant_value(from for_this_struct/in){... return *this}
  f.dtor(){}
}

h.gen_op_overload.arithment("for_this_struct")//then, right click on this line, select "do compiler command"
//then you get:
c.struct.def("for_this_struct"){
  f.op_overload("+")(rhs for_this_struct/const)(out for_this_struct){... return *this}
  f.op_overload("+=")(rhs for_this_struct/const)(){...}
  f.op_overload("-")(rhs for_this_struct/inout)(out for_this_struct){... return *this}
  f.op_overload("-=")(rhs for_this_struct/const)(){...} 
  and a lot other arithment function here.
}



eg 7, short? I forget...

s.t (1,1.,"str") is a tuple, memory model is instant value.
s.l (1,2,3,4,5) is a vector, memory model is instant value.
s.d for dict?



eg 8, extra checks.

if condition1{
  if condition2{
  }
}//condition1
//by doing this, you get extra check from ide. When you nest scopes a lot, this is useful.






