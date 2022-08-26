# Write a program to find sum of first 10 integer number
```ASM
	AREA SUM,CODE,READONLY
ENTRY
	MOV R1,#10 ;move 10 to r1
	MOV R2,#0 ;move 0 to r2
LOOP
	ADD R2,R2,R1 ; Add r2,r1 and store in r2
	SUBS R1,#01 ;substract 1 in r1
	BNE LOOP ; exit loop
BACK B BACK
	END
```

		
[[program 2]]