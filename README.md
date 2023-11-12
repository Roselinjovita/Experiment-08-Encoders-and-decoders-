# Experiment 08  Encoders and decoders 
### AIM: 
To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:
– PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED: 
Quartus prime

### THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 

### Procedure
 1. Open Quartus II and select new project and choose the file location.
  
 2. Module Declaration. Module should have the file name.

   
 3. Input-Output Delecaration.

   4.Use assign to define the functionality of logic circuits.

   5.At the end give endmodule.

   6.Run the program and choose RTL viewer to get RTL realization



### PROGRAM

Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.

Developed by: S.Roselin mary jovita

RegisterNumber:  212222230122

```
ENCODER

module encode(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
output a,b,c;
input d0,d1,d2,d3,d4,d5,d6,d7;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule
```
```
DECODER

module dec (a0,a1,a2,y0,y1,y2,y3,y4,y5,y6,y7);
input a0,a1,a2;
output y0,y1,y2,y3,y4,y5,y6,y7;
wire a0bar,a1bar,a2bar;
not(a0bar,a0);
not(a1bar,a1);
not(a2bar,a2);
and(y0,a0bar,a1bar,a2bar);
and(y1,a0,a1bar,a2bar);
and(y2,a0bar,a1,a2bar);
and(y3,a0,a1,a2bar);
and(y4,a0bar,a1bar,a2);
and(y5,a0,a1bar,a2);
and(y6,a0bar,a1,a2);
and(y7,a0,a1,a2);
endmodule
```

### RTL LOGIC 

ENCODER

![282292546-8bc8b02f-90d5-42ea-bcb7-fbfa1c438cf5](https://github.com/Roselinjovita/Experiment-08-Encoders-and-decoders-/assets/119104296/bb728229-6fd4-4fa3-aa31-36cf24ff9035)

DECODER

![282292559-f6613d79-c979-4f4b-8fd5-abdf3341fbaf](https://github.com/Roselinjovita/Experiment-08-Encoders-and-decoders-/assets/119104296/c689e12b-33d6-407a-aeb7-7c702e499689)


### OUTPUT WAVEFORM  

ENCODER

![282292655-c6f2c806-ff5a-45eb-b3d6-b6bb2bfd62ae](https://github.com/Roselinjovita/Experiment-08-Encoders-and-decoders-/assets/119104296/c2345429-43c4-4bbc-ae37-95c573188046)


DECODER

![282292676-c41bd2c5-5cf3-4fda-9d9b-d09244fac972](https://github.com/Roselinjovita/Experiment-08-Encoders-and-decoders-/assets/119104296/a748fbe5-548f-4e4c-b644-78d6733989bb)


### TRUTH TABLE 

ENCODER

![282292578-9b0fa08f-c5b0-425b-a44a-db436c3f6c2d](https://github.com/Roselinjovita/Experiment-08-Encoders-and-decoders-/assets/119104296/d7b1905f-2c8c-42cc-bb76-192610242479)


DECODER

![282292609-1550a5ff-a811-4333-8986-7a50641ba607](https://github.com/Roselinjovita/Experiment-08-Encoders-and-decoders-/assets/119104296/d32ec718-fa7a-4e4e-b831-119e07793388)




### RESULTS 

Thus, 8 to 3 Encoder and 3 to 8 Decoder is implemented using verilog and its outputs is validated .
