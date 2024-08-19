Mux.hdl

CHIP Mux {

    IN a, b, sel;
    OUT out;
    PARTS:
    Not(in=sel,out=notsel);
    And(a=a,b=notsel,out=anotsel);
    And(a=b,b=sel,out=bsel);
    Or(a=anotsel,b=bsel,out=out);
}
![image](https://github.com/user-attachments/assets/329b2206-96e1-41bd-a947-9d44cb707a87)

DMux.hdl

CHIP DMux {

    IN in, sel;
    OUT a, b;
    PARTS:
    And(a=in,b=sel,out=b);
    Not(in=sel,out=notsel);
    And(a=in,b=notsel,out=a);
}
![image](https://github.com/user-attachments/assets/5bf0cf17-2371-4487-ac08-6d23798b0def)

