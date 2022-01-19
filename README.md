#include <iostream>

using namespace std;

int main(){
    int a = 1;
    int b = 1;
    int c = 1;
    while (a !=-1 or b!=-1 or c!=-1) {
        cin >> a >> b >> c;
        cout << "w(" + str(a) + ", " + str(b) + ", " 
        + str(c) + ") = " + str(w(a,b,c)) + "\n";
    }
    
}

int w(a,b,c) {
    if (a<=0 or b<=0 or c<=0)
        return 1;
    if (a>20 or b>20 or c>20)
        return w(20, 20, 20);
    if (a<b and b<c)
        return w(a, b, c-1) + w(a, b-1, c-1) - w(a,b-1, c);
    else
        return w(a-1,b, c) + w(a-1, b-1, c) + 
        w(a-1, b, c-1) - w(a-1, b-1, c-1);
}
