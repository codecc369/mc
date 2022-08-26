```

#include <LPC21XX.h>
unsigned int delay,j;
unsigned int Switchcount=0; 
unsigned int Disp[16]={0x003F0000, 0x00060000, 0x005B0000, 0x004F0000, 0x00660000,0x006D0000,
					   0x007D0000, 0x00070000, 0x007F0000, 0x006F0000, 0x00770000,0x007C0000,
					   0x00390000, 0x005E0000, 0x00790000, 0x00710000 };

int main (void)
{
	PINSEL0 = 0x00000000;   
	PINSEL1 = 0x00000000;
	IO0DIR  = 0x00FF0000;
	IO1DIR  = 0x00000000;
	
	while(1)
	{
		IO0CLR = 0x00FF0000;		 	// clear the data lines to 7-segment displays
		IO0SET = Disp[Switchcount];	   	// get the 7-segment display value from the array
		
		 for(j=0;j<20;j++)
			for(delay=0;delay<30000;delay++);	 // 1s delay   		
	
				Switchcount++;
				if(Switchcount == 0x10)	// 0 to F has been displayed  go back to 0
			    {
				   Switchcount = 0;
				   IO0CLR  =	0x00FF0000;				
			    }
			
	}
}
```
