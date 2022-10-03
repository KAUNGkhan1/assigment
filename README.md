#include "iostream"
using namespace std;

class Store{
public:
    int locate=0;
    string username[100];
    string upassword[100];

    Store(){
        cout<<"Welcome to our Store sir!"<<endl;

    }

    int reGister();
    int login();
    int mainMenu();
    int allInfo();



};

int Store::reGister() {
    string name;
    string password;
    string password2;
    cout<<"This is from registration"<<endl;
    cout<<"Enter your name to register:";
    cin>>name;
    cout<<"Enter your password to register:";
    cin>>password;
    cout<<"Confirm password to register:";
    cin>>password2;


    if(password == password2){

        username[locate] = name ;
        upassword[locate] = password;


        cout<<"Registration Success!"<<endl;
        locate++;
        allInfo();
    }

}

int Store::login() {
    string lusername;
    string lpassword;
    cout<<"This is from Login"<<endl;
    cout<<"Enter username to login:";
    cin>>lusername;
    cout<<"Enter pass to login for"<<lusername;
    cin>>lpassword;


    for(int i=0; i<=locate ; i++){
        if(lusername == username[i] && lpassword== upassword[i]){
            cout<<"Login Success"<<endl;
        }
    }

    return 100;

}

int Store::mainMenu(){
    int option=10;
    while (true){
        cout<<"Press 1 to Register;"<<endl;
        cout<<"Press 2 to Login"<<endl;
        cout<<"Press 3 to Quit"<<endl;
        cin>>option;
        if(option == 1){
            reGister();
        } else if(option =2){
            int status=login();
            if(status == 100){
                cout<<"Please try again"<<endl;
            }
        } else{
            cout<<"See U , bye!"<<endl;
            return 0;
        }
    }
}

int Store::allInfo() {
    cout<<"Username"<<endl;
    for(int i=0; i<=locate ; i++){
        cout<<"   "<<username[i]<<endl;
    }

    cout<<"Password"<<endl;
    for(int i=0; i<=locate ; i++){
        cout<<"   "<<upassword[i]<<endl;
    }
}

int main(){

    Store _obj;
    int ex=_obj.mainMenu();
    if(ex == 0){
        exit(1);
    }
}

