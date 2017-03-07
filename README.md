# Madhunj-1SI16CS407_SIT_CSE_OOPLAB
#include<iostream>
#include<cstdlib>
using namespace std;
class intarray
{
	int sz;
	int *arr;
	public:
	intarray(int s)
	{
		sz=s;
		arr=new int[sz];
		
	}
	int operator[](int x)const;
	int& operator[](int x);
	friend ostream& operator<<(ostream& os,const intarray& ia);
	friend istream& operator>>(istream& is, intarray& ia);
	
};
int& intarray::operator[](int x)
{
	cout<<"\n version 2"<<endl;
	if(x<0||x>=sz)
	{
		cout<<"out of range"<<endl;
		exit(0);
	}
	else
	return arr[x];
}
int intarray::operator[](int x)const
{
	cout<<"\n version 2"<<endl;
	if(x<0||x>=sz)
	{
		cout<<"out of range"<<endl;
		exit(0);
	}
	else
	return arr[x];
}
ostream& operator<<(ostream &os,const intarray &ia)
{
	cout<<"\n array contents are:"<<endl;
	for(int j=0;j<ia.sz;j++)
	{
		os<<ia.arr[j];
		if(j!=ia.sz-1)
		os<<",";
	}
	os<<endl;
	return os;
}
istream& operator>>(istream& is,intarray& ia)
{
	cout<<"\n enter"<<ia.sz<<"elements int the array:"<<endl;
	for(int j=0;j<ia.sz;j++)
	is>>ia.arr[j];
	return is;
}
int main()
{
	int size,value;
	int index,i,ivalatindex;
	cout<<"enter array size:\n";
	cin>>size;
	intarray sarr(size);
	cin>>sarr;
	cout<<sarr;
	const intarray newarr(size);
	value=newarr[0];
	cout<<"\n enter an array index";
	cin>>index;
	ivalatindex=sarr[index];
	cout<<"value at index"<<index<<"is"<<ivalatindex<<endl;
	sarr[1]=sarr[2]+1;
	cout<<sarr;
	sarr[-2]=0;
	return 0;
}
