# ATM
#include<iostream>
#include<stdlib.h>
#include<string.h>
using namespace std;
class ATM{
    private:
    string name;
    int acc_number;
    int amount=0;
    int tot_bal=0;
    char type_of_account[20];
    
    /* public members or member function*/
    public:
    void person_data(){
        cout<<"Enter Name"<<endl;
        cin.ignore();// ignore will ignore the new line if entered in the name as input
        getline(cin,name);
        cout<<"Enter account number"<<endl;
        cin>>acc_number;
        cout<<"Enter type of account "<<endl;
        cin>>type_of_account;
        cout<<"Enter Balance"<<endl;
        cin>>tot_bal;
    }
    void display_data(){
        cout<<"Name :"<<name<<endl;
        cout<<"Account Number :"<<acc_number<<endl;
        cout<<"Account Type: "<<type_of_account<<endl;
        cout<<"Toal Balance :"<<tot_bal<<endl;
        
    }
    void deposit_amount(){
        cout<<"Enter amount to be deposited"<<endl;
        cin>>amount;
        
    }
    void withdraw(){
        int withdraw_amount=0,bal_available=0;
        cout<<"Enter amount to be withdrawn in multiples of 500 only:"<<endl;
        cin>>withdraw_amount;
        if(withdraw_amount<=tot_bal){
		
        tot_bal=tot_bal-withdraw_amount;
        cout<<"Available Balance is :"<<tot_bal<<endl;
    }
    else{
    	cout<<"You does not have sufficient value"<<endl;
	}
    }
    void Balance_enquiry(){
        tot_bal+=amount;
        cout<<"Total Balance is :"<<tot_bal<<endl;
        amount=0;
    }
    
};

// main function
int main(){
    ATM A;
    bool ans=true;
    int ch;
    while(ans){
        cout<<"-------------------------------------------------WELCOME---------------------------------------------------"<<endl;
        cout<<"\n"<<endl;
        cout<<"Enter your choice to perform the operation"<<endl;
        cout<<"1. Enter Name,Account number, Account type: "<<endl;
        cout<<"2. details of account holder"<<endl;
        cout<<"3. Deposit Money"<<endl;
        cout<<"4. Balance enquiry "<<endl;
        cout<<"5. withdrwal details"<<endl;
        cout<<"6. exit "<<endl;
        cin>>ch;
        switch(ch){
            case 1:
            A.person_data();
            break;
            case 2:
            A.display_data();
            break;
            case 3:
            A.deposit_amount();
            break;
            case 4:
            A.Balance_enquiry();
            break;
            case 5:
            A.withdraw();
            break;
            case 6:
            	exit(0);
            	break;
            default:
			cout<<"Invalid choice"<<endl;	
        }   
    }
    
} 
