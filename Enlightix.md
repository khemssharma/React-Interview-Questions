# Make it run here: https://www.programiz.com/cpp-programming/online-compiler/ 
## Reverse A String
```
#include <iostream>
using namespace std;
int main() {
    string str;
    string reversed = "";
    cout << "Enter a string: \n";
    getline(cin, str);
    for (int i = str.length() - 1; i >= 0;  i--){
        reversed += str[i];
    }
    cout << reversed << endl;

    return 0;
}
```

## Check Palindrom

```
#include <iostream>
#include <cctype>
using namespace std;

bool isPalindrom(string str){
    int start = 0, end = str.length() -1;
    while (start < end){
        if (tolower(str[start++]) != tolower(str[end--])){
            return false;
        }
    }
    return true;
}

int main() {
    string str;
    cout << "Enter a string to check for palindrom: \n";
    getline(cin, str);
    if (isPalindrom(str)){
        cout << "It is a palindrom";
    }else cout<< "It is not a palindrom";
}
```
## Program to find the largest number in the array
```
#include <iostream>
using namespace std;

int main() {
    int n;
    int arr[n];
    cout << "Enter the number of elements in the array: ";
    cin >> n;
    cout << "Input the numbers: ";
    for (int i = 0; i < n; i++){
        cin >> arr[i];
    }
    int largest = arr[0];
    for (int i= 1; i < n; i++){
        if (arr[i] > largest){
            largest = arr[i];
        }
    }
    cout << "Largest element is: " << largest;
}
```
