# coding
//c++ program for operations on complex numbers
//to accept 2 no in beginning
#include<iostream>
using namespace std;
class complex
{
	float real,img;
	public:
	complex()
		{
			real=0;
			img=0;
		}
void getdata()
	{
		cout<<"\n Enter the real and imaginary part of the complex number \n:";
		cin>>real>>img;
	}
void display()
	{
		cout<<"\n"<<real<<"+"<<img<<"i";
	}
complex operator +(complex c1)
	{
		complex c3;
		c3.real=real+c1.real;
		c3.img=img+c1.img;
		return c3;
	}
complex operator -(complex c1)
	{
		complex c3;
		c3.real=real-c1.real;
		c3.img=img-c1.img;
		return c3;
	}
complex operator *(complex c1)
	{
		complex c3;
		c3.real=real*c1.real-img*c1.img;
		c3.img=real*c1.img+img*c1.real;
		return c3;
	}
complex operator /(complex c1)
	{
		complex c3;
		float temp;
		temp=c1.real*c1.real-c1.img*c1.img;
		c1.img=c1.img*(-1);
		c3.real=real*c1.real-img*c1.img;
		c3.img=real*c1.img+img*c1.real;
		c3.real=c3.real/temp;
		c3.img=c3.img/temp;
		return c3;
	}
};
int main()
	{
		int m;
		char n;
		complex c1,c2,c3,c4,c5,c6;
		c1.getdata();
		c2.getdata();
		cout<<"\n Given two complex numbers:";
		c1.display();
		c2.display();
		do
		{
			cout<<"\n MENU:\n1.ADDITION\n2.SUBTRACTION\n3.MULTIPLICATION\n4.DIVISION\nchoice=";
			cin>>m;
			switch(m)
			{
			case 1:cout<<"\n\nADDITION:\n:";
			c3=c1+c2;
			c3.display();
			break;

			case 2:cout<<"\n\nSUBTRACTION:\n:";
			c4=c1-c2;
			c4.display();
			break;

			case 3:cout<<"\n\nMULTIPLICATION:\n:";
			c5=c1*c2;
			c5.display();
			break;

			case 4:cout<<"\n\nDIVISION:\n:";
			c6=c1/c2;
			c6.display();
			break;
			}
			cout<<"\n DO YOU WANT TO CONTINUE-y/n:";
			cin>>n;
		}
			while (n=='y');
}
