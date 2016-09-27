#include <iostream>
#include <math.h>
using namespace std;
/* run this program using the console pauser or add your own getch, system("pause") or input loop */

class rectangulo {
	
	double x1, x2, x3, x4, y1, y2, y3, y4;
	double alto11, alto22, ancho11, ancho22;
	
	public:
		
		rectangulo (double &a, double &b, double c, double &d, double &e, double &f, double &g, double &h){
			
			x1 = a;
			y1 = b;
			x2 = c;
			y2 = d;
			x3 = e;
			y3 = f;
			x4 = g;
			y4 = h;
		}
		
		double ancho1 (){
			
			if (x2 > x1){
				
				double ancho = sqrt((x2-x1)*(x2-x1));
				return ancho;
			}
			else if (x2 < x1){
				
				double ancho = sqrt((x1-x2)*(x1-x2));
				return ancho;
			}
		}
		
		double ancho2 (){
			
			if (x4 > x3){
				
				double ancho2 = sqrt((x4-x3)*(x4-x3));
				return ancho2;
			}
			else if (x4 < x3){
				
				double ancho2 = sqrt((x3-x4)*(x3-x4));
				return ancho2;
			}
		}
		
		double altura1 (){
			
			if (y2 > y1){
				
				double alto1 = sqrt((y2-y1)*(y2-y1));
				return alto1;
			}
			else if (y2 < y1){
				
				double alto1 = sqrt((y1-y2)*(y1-y2));
				return alto1;
			}
		}
		
		double altura2 (){
			if (y4 > y3){
				
				double alto2 = sqrt((y4-y3)*(y4-y3));
				return alto2;
			}
			else if (y4 < y3){
				
				double alto2 = sqrt((y3-y4)*(y3-y4));
				return alto2;
			}
		}
				
		double area1 (){
						
			double at1, an1;
			this->altura1();
			at1 = altura1();
			this->ancho1();
			an1 = ancho1();
			double area11 = at1 * an1;
			return area11;
		}
				
		double area2 (){

			double at2, an2;
			this->altura2();
			at2 = altura2();
			this->ancho2();
			an2 = ancho2();
			double area22 = at2 * an2;
			return area22;
		}
			
		double perimetro1 (){
			
			double at1, an1;
			this->altura1();
			at1 = altura1();
			this->ancho1();
			an1 = ancho1();
			double perimetro11 = (at1 + an1)*2;
			return perimetro11;
		}
		
		double perimetro2 (){
			
			double at2, an2;
			this->altura2();
			at2 = altura2();
			this->ancho2();
			an2 = ancho2();
			double perimetro22 = (at2 + an2)*2;
			return perimetro22;
		}
		
		string str (){
			
			return "Los rectangulos tienen por coordenadas (" << to_string(x1) << ", " << to_string(y1) << "), (" << to_string(x2) << ", " << to_string(y2) << "), (" << to_string(x3) << ", " << to_string(y3) << ") y (" << to_string(x4) << ", " << to_string(y4) << ")" << endl;
		}
		
};


int main(int argc, char** argv) {
	
	double a = 0, b = 0, c = 0, d = 0, e = 0, f = 0, g = 0, h = 0;
	while ((a == c && b == d) || (e == g && f == h)){
		
		cout << "Ingrese los valores de los 4 puntos:" << endl << endl;
		cout << "Punto x1:  ";
		cin >> a;
		cout << endl << "Punto y1:  ";
		cin >> b;
		cout << endl << "Punto x2:  ";
		cin >> c;
		cout << endl << "Punto y2:  ";
		cin >> d;
		cout << endl << "Punto x3:  ";
		cin >> e;
		cout << endl << "Punto y3:  ";
		cin >> f;
		cout << endl << "Punto x4:  ";
		cin >> g;
		cout << endl << "Punto y4:  ";
		cin >> h;
		if (a == c && b == d){
			
			cout << "Sus valores de las dos primeras coordenadas no representan un rectangulo sino un punto, ingrese nuevos valores." << endl;
			continue;
		}
		else if (e == g && f == h){
			
			cout << "Sus valores de las dos ultimas coordenadas no representan un rectangulo sino un punto, ingrese nuevos valores." << endl;
			continue;
		}
		else {
			
			break;
		}
		
		
	}
	
	rectangulo t(a, b, c, d, e, f, g, h);
	
	cout << t.str() << endl;
	cout << "El ancho de los rectangulos 1 y 2 respectivamente son:  " << t.ancho1() << " y " << t.ancho2() << endl;
	cout << "El alto de los restangulos 1 y 2 respectivamente son:  " << t.altura1() << " y " << t.altura2() << endl;
	cout << "El area de los rectangulos 1 y 2, respectivamente, son:  " << t.area1() << " y " << t.area2() << endl;
	cout << "El perimetro de los rectangulos 1 y 2, respectivamente, son:  " << t.perimetro1() << " y " << t.perimetro2() << endl;
	
	
	
	
	
	
	
	
	system("pause");
	return 0;
}
