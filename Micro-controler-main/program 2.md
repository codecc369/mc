# Write an ALP to calculate factorial of a number 
```ASM
		AREA FACT, CODE , READONLY
	ENTRY 
		MOV R1,#7 ;
		MOV R1,R0 ;
	FACT0
		SUBS R1,R1,#1 ;
		CMP R1,#1 ;
		BEQ STOP ;
		MUL R3,R0,R1 ;
		MOV R0, R3 ;
		BNE FACT ;
	STOP
		NOP
	BACK B BACK
		END
```
[[program 1]]
[[program 3]]