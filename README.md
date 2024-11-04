# DEVOIR-not-
#include <iostream>
using namespace std;
template< class T>
class nombrecomplexe{
private:
    T reel;
    T imaginaire;
public:
    nombrecomplexe():reel(0), imaginaire(0){}
    nombrecomplexe(int R, int I):reel(R), imaginaire(I){}
    nombrecomplexe( nombrecomplexe const& autre):reel(autre.reel), imaginaire(autre.imaginaire){}
void afficher(){
    if(imaginaire >= 0){
    cout<< reel << "+" << imaginaire << "i" <<endl;
    else 
     cout<< reel << "-" << imaginaire << "i" <<endl;
}
nombrecomplexe<T> operator+(const nombrecomplexe<T>& C2){
    return nombrecomplexe<T>(reel+C2.reel, imaginaire+C2.imaginaire)
}
nombrecomplexe<T> operator-(const nombrecomplexe<T>& C2){
    return nombrecomplexe<T> (reel-C2.reel, imaginaire-C2.imaginaire)
}
nombrecomplexe<T> operator-(const nombrecomplexe<T>& C2){
    return nombrecomplexe<T> (reel-C2.reel, imaginaire-C2.imaginaire)
}
nombrecomplexe<T> operator*(const nombrecomplexe<T>& C2){
 return nombrecomplexe<T> (reel * C2.reel - imaginaire * C2.imaginaire,
            reel * C2.imaginaire + imaginaire * C2.reel
)
}


};

int main()
{
    NombreComplexe<int> c1(6, 9); 
    NombreComplexe<int> c2(7, 8); 

    cout << "Nombre complexe c1 : ";
    c1.afficher();

    cout << "Nombre complexe c2 : ";
    c2.afficher();
    

    NombreComplexe<int> c3 = c1 + c2;
    cout << "c1 + c2  ";
    c3.afficher();


    NombreComplexe<int> c4 = c1 - c2;
    cout << "c1 - c2  ";
    c4.afficher();


    NombreComplexe<int> c5 = c1 * c2;
    cout << "c1 * c2  ";
    c5.afficher();
    
    return 0;
}
