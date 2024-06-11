#include <iostream>
#include <fstream>
#include <string>
using namespace std;
class sign_up
{
	public:
	string name;
	string nameL;
	string email;
	int password;
	void display()
	{
		cout<<"           SIGN UP        " <<endl 
	          <<"   { Enter First  Name"<<endl
	          <<"     Enter Second Name"<<endl
	          <<"     Enter Email       "<<endl
	          <<"     Enter password  } "<<endl<<endl;
		cout<<" Enter First  Name = ";
		cin>>name;
	    cout<<" Enter Second Name = ";
	    cin>>nameL;
	    cout<<" Enter Email       =";
	    cin>>email;
	    cout<<" Enter password    =";
	    cin>>password;
		cout<<endl;
	    cout<<"   **("<<name<<" "<<nameL<<")   your accout is created sucessfully **"<<endl<<endl;
		ofstream file("b.txt");
    file <<"NAME     ="<<name<<" "<<nameL<<"\n";
    file <<"Email    ="<<email<<"\n";
	file <<"Password ="<<password<<"\n";
    file.close();
	}
};
class login:public sign_up
{
    public:
	int password2;
	string email2;
	void log()
	{
		cout<<"   Login "<<endl;
		cout<<"Enter the Email =";
		cin>>email2;
		cout<<"Enter the Password=";
		cin>>password2;
		match();
		
	}
   	void match()
	{
		if((password==password2)&&(email==email2))
		{
			cout<<endl;
			cout<<"**  "<<name<<" "<<nameL<<" is login Successfully **"<<endl;
			
		}
		else 
		{
			cout<<"** Invalid login Email & name **"<<endl;
		}
	}
};
class option:public login
{
	public:
		int n;
		void enter()
		{ 
			      cout<<"** Enter number 1 to create account & 2 for Login **"<<endl;
			cout<<"Enter number please= ";
			cin>>n;
			swith();	
	    }
		
		
          void swith()
		  {
        	
		    	switch(n)
		    	{
			    	case 1:
			    		{
			     			sign_up::display();
			     			enter();
				    		break;
				    	}
				        case 2:
				         	{
				         		login::log();
				         		break;
					     	}
					         	default :
					         	{
					    	    	cout<<"invalid Key"<<endl;
					    	    	break;
					        	}
			
	       	    }
	        }   
};
class Game:public option
{
     public:
		int num;
			void display(){
				if(password==password2){
				cout<<"    **Simple Game to gess the number between 0 to 100 **"<<endl;
				func();
				}
			}
			void func(){
				for(int i=1;i<=71;i++)
				{
				    i=num;
				cout<<"Enter the number ="<<endl;
				cin>>num;
				if((num>0)&&(num<20)){
					cout<<"Incorrect number "<<endl;
					cout<<" very loo number"<<endl;
					
				}
				if((num>20)&&(num<50)){
					cout<<"Incorrect number "<<endl;
					cout<<" loo number"<<endl;
					
				}
				if((num>50)&&(num<=70)){
					cout<<"Incorrect number "<<endl;
					cout<<" lage lage aa putt"<<endl;
				}
				if((num>70)&&(num<72)){
					cout<<"Badu Bade jeet Gae"<<endl;
					cout<<"Mubarkan"<<endl;
				}
				if((num>71)&&(num<=100)){
					cout<<"AE AE Age Tap gea"<<endl;
					
				}
				else{
					cout<<"enter valed number"<<endl;
				}
				
			
			    }
				
			}
};
int main(){
	
	Game h;
	h.enter();
	h.display();
	return 0;
}

