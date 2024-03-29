Assume you oversee a small library and would like to develop a program that looks up books using their ISBNs. A list of books with their corresponding ISBN digits is in front of you. After the librarian inputs an ISBN, your software will look through the list to locate the relevant book.  The book's title and other details will be shown if the book is located. A notice stating that the book is not available in the library will appear if it cannot be located.
#include <iostream>
using namespace std;
class Books{
	public:
		long double isbn[20],isbnss;
		int i,n;
		string bookname[20],author[20];
		Books(){
			cout<<"Are you ready to enter the world of bizzare library";
			cout<<"\nEnter the ISBN number along with the book name and author name";
			cout<<"\nPlease enter the number of books whose data you want to enter: ";
			cin>>n;
			cout<<"\nEnter ISBN number: ";
			for(i=1;i<=n;i++){
				cin>>isbn[i];
			}
			cout<<"\nEnter author name: ";
			for(i=0;i<=n;i++){
				getline(cin,author[i]);
			}
		}
		void names(){
			cout<<"\nEnter book name: ";
			for(i=1;i<=n;i++){
				getline(cin,bookname[i]);
			}
		}
		void search(){
		    cout<<"Enter the book's ISBN number whose details you want to search: ";
		    cin>>isbnss;
		    int flag=0;
		    for(i=1;i<=n;i++){
		    	if(isbnss==isbn[i]){
		    		cout<<"\nBookname is: "<<bookname[i];
		    		cout<<"\nAuthor name is: "<<author[i];
		    		cout<<"\nISBN number is: "<<isbn[i];
		    		flag++;
				}

			}
			if(flag==0){
					cout<<"\nThe ISBN number might be wrong or the book might not be available";
			}
	}
};
int main(){
	int choice;
	Books ob;
	ob.names();
	while(choice<=1){
	      cout<<"Enter what you want to do:\n 1 for searching any book \n 2 for exit";
	    cin>>choice;
	    if(choice==1){
		   ob.search();
	    }
	else{
		cout<<"\nOk byeee";
	}
}
}
