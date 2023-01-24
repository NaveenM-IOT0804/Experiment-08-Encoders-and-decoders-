# Experiment-08- Encoders-and-decoders 
### AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
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
```
Step 1: Open Quartus II and select new project and choose the file location.
Step 2: Module Declaration. Module should have the file name.
Step 3: Input-Output Delecaration.
Step 4: Use assign to define the functionality of logic circuits.
Step 5: At the end give endmodule.
Step 6:Run the program and choose RTL viewer to get RTL realization.
```
### PROGRAM 
```
/*
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: Naveen .M
RegisterNumber:  22000748
*/
Encoder:

module expen(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
output a,b,c;
input d0,d1,d2,d3,d4,d5,d6,d7;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule

Decoder:

module decode(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
output d0,d1,d2,d3,d4,d5,d6,d7;
input a,b,c;
assign d0 = (~a&~b&~c);
assign d1 = (~a&~b&c);
assign d2 = (~a&b&~c);
assign d3 = (~a&b&c);
assign d4 = (a&~b&~c);
assign d5 = (a&~b&c);
assign d6 = (a&b&~c);
assign d7 = (a&b&c);
endmodule
```


### RTL LOGIC  

Encoder:

![encode](https://user-images.githubusercontent.com/117974950/214296234-761478b9-805e-49b1-a49b-89c43149912e.png)

Decoder:

![decode](https://user-images.githubusercontent.com/117974950/214296308-97edad47-926f-460c-b4d1-12b17364e7fa.png)



### TIMING DIGRAMS  

Encoder:

![enwave](https://user-images.githubusercontent.com/117974950/214297008-df701432-d2aa-481e-a03c-a21d42b68b7d.png)

Decoder:

![decwave](https://user-images.githubusercontent.com/117974950/214297129-1b2a695e-7898-4b58-8b15-fa559e497ebc.png)

### TRUTH TABLE 

Encoder:

![entt](https://user-images.githubusercontent.com/117974950/214297202-7d555106-c029-4d61-ab6f-a45f516ae10d.png)


Decoder:

![dectt](https://user-images.githubusercontent.com/117974950/214298845-bf0406cc-f4ae-4a13-9a29-0fcc4f3470f8.png)

### RESULTS 
8 to 3 Encoder and 3to8 Decoder has been implemented by using verilog and its outputs are validated.
