#include<iostream>
using namespace std;

class BankDeposit{
    int principal;
    int years;
    float InterestRate;
    float ReturnValue;
    public:
       BankDeposit(){} //Default Constructor
       BankDeposit(int p, int y, float r);
       BankDeposit(int p, int y, int r);
       void show();
};
BankDeposit :: BankDeposit(int p, int y, float r)
{
    principal = p;
    years = y;
    InterestRate = r;
    ReturnValue = principal;
    for (int i = 0; i < y; i++)
    {
        ReturnValue = ReturnValue * (1+r);
    }
}    
BankDeposit :: BankDeposit(int p, int y, int r)
{
    principal = p;
    years = y;
    InterestRate = float(r)/100;
    ReturnValue = principal;
    for (int i = 0; i < y; i++)
    {
        ReturnValue = ReturnValue * (1+r);
    }    
}

void BankDeposit :: show()
{
    cout<<endl<<"Principal amount was: "<<principal<<endl<<"Return value after "<<years<<" years is "<<ReturnValue<<endl;
}
int main()
{
    BankDeposit bd1;
    int p,y;
    float r;
    int R;
    cout<<"Enter the value of p y and r:\n";
    cin>>p>>y>>r;
    bd1 = BankDeposit(p, y, r);
    bd1.show();
    return 0;
}
