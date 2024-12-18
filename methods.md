# Methods

POOP extends C `struct.functions()` and calls them METHOD(s)


In an inheritence hiearchy such as 

```
ABC
 |
 ↓
DEF
```

AND

the METHOD signature (name + return type + argument types) is the same (let's call this ```methodA'``

then the call hierchy of child object's method calls are as follows


```
ABC.methodA()
 ↑
 |
DEF.methodA()
```

if a child object would like to prevent this call stack they can insert the `override` keyword

Example
```
struct DEF : ABC {
    void methodA(){
        override;
        // Code goes here... 
    }
}

```
