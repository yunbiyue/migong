#include<stdio.h>
int a,b[10][10],min=0,x[10][10],num=0,l=0;
void lujin(int m,int n)
{
	if(m==a-2 && n==a-2) 
	{
		if(l==0)
		{
			min=num;
		}
		if(num<min) 
		{
			min=num;
		}
		l++;
		return;
	}
	
	if(b[m][n]==0 && x[m][n]==0)
	{
		num++;
		x[m][n]=1; 
		lujin(m+1,n);
		 
		x[m][n]=0;
		num--;
	}
	if(b[m][n]==0 && x[m][n]==0)
	{
	    num++;
		x[m][n]=1;
		lujin(m-1,n); 
		x[m][n]=0;
		num--;
	}
	if(b[m][n]==0 && x[m][n]==0)
	{
	    num++;
		x[m][n]=1; 
		lujin(m,n+1);
		x[m][n]=0;
		num--;
	}
	if(b[m][n]==0 && x[m][n]==0)
	{
	    num++;
		x[m][n]=1;
		lujin(m,n-1);
		x[m][n]=0;
		num--;
	}
}
int main()
{
	scanf("%d",&a);
	for(int c=0;c<a;c++)
	{
		for(int d=0;d<a;d++)
		{
			scanf("%d",&b[c][d]);
		}
	}
	lujin(1,1);
	if(min)
	printf("%d",min);
	else
	printf("No solution");
	
	
}
