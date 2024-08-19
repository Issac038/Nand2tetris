HalfAdder

CHIP HalfAdder {

    IN a, b;    // 1-bit inputs
    OUT sum,    // Right bit of a + b 
        carry;  // Left bit of a + b
    PARTS:
    And(a=a,b=b,out=carry);
    Xor(a=a,b=b,out=sum);
}
![image](https://github.com/user-attachments/assets/a1036ead-192b-4c6d-be75-6292a7fddd50)

FullAdder

CHIP FullAdder {

    IN a, b, c;  // 1-bit inputs
    OUT sum,     // Right bit of a + b + c
        carry;   // Left bit of a + b + c
    PARTS:
    HalfAdder(a=a,b=b,sum=sum1,carry=carry1);
    HalfAdder(a=c,b=sum1,sum=sum,carry=carry2);
    Or(a=carry1,b=carry2,out=carry);
}
![image](https://github.com/user-attachments/assets/d5444893-c010-4ee1-ae1b-1f0df143ded0)
