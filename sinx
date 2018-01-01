/*
Enda O'Connell
17768231

Objective: Recreate the sin function in c and attempt to solve the error over time problem for double precision numbers.

This code works for values between 0 and 35 radians however past that the rounding error becomes a problem and gives incorrect 
values.

*/

#include <stdio.h>
#include <math.h>

double sin_(double x);

int main(void)
{
	double x;
	printf("Enter number to sin:");
	scanf("%lf", &x);
	double ans = sin_(x);
	double actual_sin = sin(x);
	printf("Sin found using my formula: %lf \n", ans);
	printf("Sin found using math function: %lf \n", actual_sin);
	double difference = ans - actual_sin;
	printf("Difference between the two: %lf", difference);
}

double sin_(double x)
{
	int i = 1, j = 1, q = 3;
	double final = 0, l = x ;
	
	/*
	The while loop with the j creates all the positive terms all the way up until j is greater than
	1000 and adds these to a double called final
	*/
	while(j<100)
	{
		double factorial = 1;
		for(i=1; i<=j; i++)
		{
			factorial *= i; 
		}
		
		double positive_terms = (pow(l, j))/factorial;
		//printf(".%lf \n", positive_terms);
		final +=  positive_terms;
		j = j + 4; 
			
	}
	
	/*
	The while loop with the q creates all the negative terms all the way up until q is greater than
	1000 and takes these away from final.
	*/
	
	while(q<100)
	{
		double factorial = 1;
		for(i=1; i<=q; i++)
		{
			factorial *= i; 
			
		}
		
		double negative_terms = (pow(l, q))/factorial;
		//printf("#%lf \n", negative_terms);
		final -=  negative_terms;
		q = q + 4; 	
	}
	return final; //final is all the positive terms with all the negative terms taken away
}
