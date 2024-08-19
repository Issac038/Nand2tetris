Not.hdl

CHIP Not {
    
    IN in;
    OUT out;
    PARTS:
    Nand(a=in ,b=in ,out=out);
}
![Screenshot 2024-08-19 141650](https://github.com/user-attachments/assets/75779d03-c3e3-4033-ae6e-6b86fba11ec8)

Or.hdl

CHIP Or {
    
    IN a, b;
    OUT out;
    PARTS:
    Not(in=a,out=nota);
    Not(in=b,out=notb);
    Nand(a=nota,b=notb,out=out);
}
![Screenshot 2024-08-19 150202](https://github.com/user-attachments/assets/36318566-1ec8-4409-8f91-cfb15ebdbeaa)
