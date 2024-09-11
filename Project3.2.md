
Ram512.hdl

CHIP RAM512 {

    IN in[16], load, address[9];
    OUT out[16];
    PARTS:
    DMux8Way(in=load,sel=address[6..8],a=load0,b=load1,c=load2,d=load3,e=load4,f=load5,g=load6,h=load7);
    RAM64(in=in,load=load0,address=address[0..5],out=out0);
    RAM64(in=in,load=load1,address=address[0..5],out=out1);
    RAM64(in=in,load=load2,address=address[0..5],out=out2);
    RAM64(in=in,load=load3,address=address[0..5],out=out3);
    RAM64(in=in,load=load4,address=address[0..5],out=out4);
    RAM64(in=in,load=load5,address=address[0..5],out=out5);
    RAM64(in=in,load=load6,address=address[0..5],out=out6);
    RAM64(in=in,load=load7,address=address[0..5],out=out7);
    Mux8Way16(a=out0,b=out1,c=out2,d=out3,e=out4,f=out5,g=out6,h=out7,sel=address[6..8],out=out);
}

![image](https://github.com/user-attachments/assets/a0223d84-d26d-4888-8c26-833a25e6cce4)

Ram4k.hdl

CHIP RAM4K {

    IN in[16], load, address[12];
    OUT out[16];
    PARTS:
    DMux8Way(in=load,sel=address[9..11],a=load0,b=load1,c=load2,d=load3,e=load4,f=load5,g=load6,h=load7);
    RAM512(in=in,load=load0,address=address[0..8],out=out0);
    RAM512(in=in,load=load1,address=address[0..8],out=out1);
    RAM512(in=in,load=load2,address=address[0..8],out=out2);
    RAM512(in=in,load=load3,address=address[0..8],out=out3);
    RAM512(in=in,load=load4,address=address[0..8],out=out4);
    RAM512(in=in,load=load5,address=address[0..8],out=out5);
    RAM512(in=in,load=load6,address=address[0..8],out=out6);
    RAM512(in=in,load=load7,address=address[0..8],out=out7);
    Mux8Way16(a=out0,b=out1,c=out2,d=out3,e=out4,f=out5,g=out6,h=out7,sel=address[9..11],out=out);
}

![image](https://github.com/user-attachments/assets/c6940a5b-b19d-4dd5-b480-cc778cd54c4f)

Ram16k.hdl

CHIP RAM16K {

    IN in[16], load, address[14];
    OUT out[16];
    PARTS:
    DMux4Way(in=load,sel=address[12..13],a=load0,b=load1,c=load2,d=load3);
    RAM4K(in=in,load=load0,address=address[0..11],out=out0);
    RAM4K(in=in,load=load1,address=address[0..11],out=out1);
    RAM4K(in=in,load=load2,address=address[0..11],out=out2);
    RAM4K(in=in,load=load3,address=address[0..11],out=out3);
    Mux4Way16(a=out0,b=out1,c=out2,d=out3,sel=address[12..13],out=out);
}

![image](https://github.com/user-attachments/assets/7af74ec1-6e3e-40c9-bb34-4f730d95c317)

Pc.hdl

CHIP PC {

    IN in[16],load,inc,reset;
    OUT out[16];
    PARTS:
    Inc16(in=out5,out=out1);
    Mux16(a=out5,b=out1,sel=inc,out=out2);
    Mux16(a=out2,b=in,sel=load,out=out3);
    Mux16(a=out3,b=false,sel=reset,out=out4);
    Register(in=out4,load=true,out=out5,out=out);

}

![image](https://github.com/user-attachments/assets/a5418d53-c9d0-4432-b803-b3686b2cef48)




