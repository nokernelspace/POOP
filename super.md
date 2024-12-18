# Super

Unlike other OOP languages there are no access modifiers in POOP. This means no ```public```, ```private```, or ```protected```.
Unlike other OOP languages there is no shadowing of fields in children of the same identifier/signature.

This means that POOP can access all the fields/methods of the parent via the ```super``` keyword


Example
```

struct ABC { 
    int a;
    int b;

    void methodA(){
        printf("Hello World\n");
    }


    void methodB(){
        printf("You are now in Method B\n");
    }
}


struct DEF : ABC {
    int a;
    void methodA(){
        /// This node in the callstack does nothing
    }
}


struct GHI : DEF {
    int a;
    void methodA(){
        override;
        super.a = super.super.a + super.super.b;

        // Code goes here... 
        super.super.methodB();
    }
}

int main(){
    GHI test = GHI{};
    test.methodA();
}
```

Output
```
You are now in Method B
```

This design choice is to force developers to think about inheritence when designing programs.