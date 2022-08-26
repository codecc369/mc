# Write an ALP to find largest/smallest number in the given array of 32 bit list

```ASM
	AREA LARGEST, CODE, READONLY
ENTERY
START
	MOV R5,#6 ;
	LDR R1,=Value ;
	LDR R2,[R1],#4;
LOOP
	LDR R4,[R1],#4 ;
	CMP R2,R4 ;
	BHI LOOP1 ;
	MOV R2,R4 ;
LOOP 1
	SUBS R5,R5,#1 ;
	CMP R5, #0 ;
	BNE LOOP ;
	LDR R4,=Result ;
	STR R2,[R4] ;
	NOP
	NOP
	Value 
		DCD 0X44444444;
		DCD 0X22222222;
		DCD 0X33333333;
		DCD 0X88888888;
		DCD 0XAAAAAAAA;
		
		AREA DATA2, DATA, READWRITE
		Result DCD 0X0 ;
		END
		
```