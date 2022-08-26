# Write an ALP to add an array of 16 bit number and store 32 bit result in internal ram
```ASM
		AREA CODEADD, CODE , READONLY
	ENTRY
		MOV R5,#6 ;
		MOV R0,#0 ;
		LDR R1, =value ;
	LOOP
		LDRH R3,[R1],#02 ;
		ADD R0,R0,R3 ;
		SUBS R5, R5, #1 ;
		BNE LOOP ;
		LDR R4, =Result ;
		STR R0,[R4] ;
	JMP B JMP
	value DCW 0X1111,0X2222,0X3333,0XAAAA,0XBBBB,0XCCCC;
		AREA DATA2,DATA,READWRITE
	Result DCD 0X0
		END
```
[[program 2]]
[[Program 4]]