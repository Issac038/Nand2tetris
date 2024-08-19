And.hdl

CHIP And {

    IN a, b;
    OUT out;
    PARTS:
    Nand (a=a, b=b, out=anandb);
    Nand (a=anandb, b=anandb, out=out);
}
![image](https://github.com/user-attachments/assets/6e260825-c565-4c35-9f4c-8e551ac313aa)

Xor.hdl

CHIP Xor {
    
    IN a, b;
    OUT out;
    PARTS:
    Not(in=a,out=nota);
    Not(in=b,out=notb);
    And(a=nota,b=b,out=t1);
    And(a=a,b=notb,out=t2);
    Or(a=t1,b=t2,out=out);
}
![Screenshot 2024-08-19 151852](https://github.com/user-attachments/assets/6a7df820-fb6a-4728-a6fb-2c9c8ff3d131)
