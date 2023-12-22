Doconly programming language



0, whom are this project for

This project is only for discussion on good and bad features of programming language.
If you are new to programming language, leave now. This project only wastes your time. You are welcome to read anything here, but you would probably get nothing in return.
If you are making a programming language, maybe you can find something interesting here.
If you are here only for fun, and you love programming, maybe I should make a discord server?



1, why are Dononly like languages probably the future of programming language

1.1, What is Doconly

Doconly is a programming language. I started it as a useless and "only for fun" project. But after a while I found it much more important than I firstly expected. I firstly use it to express my thoughts on designing of programming language, but now, I believe it's time to treat it seriously.

1.2, What happened in these years, what is the top problem that slows us from improving programming languages

In the past 40 years(or longer), people around the world invented a lot programming languages. The basic pattern is, new lang are inspired by old lang. People modified the old langs, added or removed something for it, and made a new one.
The problem is, before a point, the language is too unfinished, it's hard to get people's attention, so it's not very possible to get suggestions and correct the design before got too wrong. After the point, a lot features are already implemented, it's already too late for the project to absord ideas or correct the design, at least it's too late to correct the most important designs.
This pattern happened to all the languages.
In recently few years, new proagramming language projects chose to open source more, and prerelease earlier, so they can get suggestions as early as possible, but I personally believe it's still too late.
I'm professional in making programming lang. I'm not very sure about the conclusion, but according to my intuition, it's the compiler that denies the time when a project can prerelease to the public. What if we don't have to wait for the compiler? I think only designing and documentation are left. 
So, is it possible to prerelease a programming lang project with only a half done design and the half done documentation? If this is the way, we can start absorbing suggestions from the beginning. When we decide to do any change, the cost is very low. Since the changes don't have to be implemented into the compiler, the project can iterates much faster than all the traditional projects.
This is the reason, now it's an important test.

1.3, About the name?

Doconly = Doc + only, which means there's not compiler for this language.
(This is the original decision, before I realise this project can be very important.)

1.4, Why(a bit repeating. can be ignored safely)

Recently years, people all over the world have made and are making a lot programming languages. Such works is very costly, and iterates very slowly, though it's much faster than many years ago.
I recommend a cheap way to test out our ideas of programming language design. Theoritically, if we can make mistakes in a cheap way, and iterate faster, we can expect a much better result.
Generally, compiler and a completed documentation are the 2 unavoidable costly parts when make a programming language. If we can only make a simplified documentation, and iterate it, before we really spend a lot time and resource to make the compiler, we can expect a better result.



2, criterions

According to my experience of programming, I would like to list some most important ability of a programming language:
as little guess work as possible!!!
automatical completion / input hint
type system(at least static typed)
duck type or inhiritance?

Theory is a bit different from the direct experience.
I want the language to cost AS LITTLE, produce AS MUCH. In other words, it should be as easy to learn as possible, and as useful as other languages.

(can be ignored safely.)
To achieve this, this language follows the criterions below:
)Default setting only works in its scope. All default can be changed in code. This also helps the language iterate. Any team can specify their own white list for features directly in code.
)As few syntax system as possible.
)Automatical completion/input hint as a feature. Full control on this feature with code.
)Full control of compile time.
)Everything can be searched directly in searching engines, or get enough help with input hint. Users don't have to know their names, including the names of the features.
)No hidden black magic, unless I have no choise. If the black magic is introduced, it's directly in the documentation.
)Every non A-Za-z0-9_ operation has a A-Za-z0-9_ alias name.(eg. a[0] is the same as a.__index(0))
)Static 2 layer type system. The first type is either built-in type(supported directly by hardware, or too classic we just must have it, like boolean), the second layer is Memory model. So users can also convert type on memory models(for instance: left value get converted into instant value). (I also post similar idea in hsutter/cppfront. HSutter replied he considered this before but he suggest not to have it. So if you don't like this idea, just ignore it. It's doc only, we don't have a way to test it.)
)Structure composition as default. Member functions are manually bonded to each structure. The inhiritance way is implemented by compile time command(check out in documentation after). So you get both.
)Static typed as default. Dynamic typed style activated with code. 



3, what NOT to expect in this project(can be ignored safely.)

Since I have only very limited idea about how to make a real programming language, and this project doesn't target at some runnable binary executable, I will NOT take good care about the performance. But if I know any performance issue, I'll try my best to make it correct.
Anyway, because I didn't test the performance and can only assume the result, here's the list of assuption:
)I assume the compiler trans-compile the source code of Doconly into cpp, just like cppfront does. If anything is already named in cpp, I'll use the name.
)unique_ptr is faster, duck type is better, so I'll use them as default. You can specify a new default in code, but you don't have to, because there's no compiler.
)A linter. Or maybe this is also important enough, but not for now.
)All the good features only good for a very special area are not set as default. I may add some of them in the language, maybe not.



4, before you post any suggestion

Basically, everyone prefers some special syntax. Just like the project of cppfront, maybe I accept some of such suggestions, but don't expect anything to happen. If anything brings too much learning cost but only helps a bit, I just don't accept it. Sorry for that.





