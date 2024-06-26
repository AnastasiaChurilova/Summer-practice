# Summer-practice
# Летняя практика # Реализация линейной аппроксимации / Implementation of linear approximation (appr) 
∑(сигма) - сумма всех значений в диапазоне ряда	Σ Xn = X1 + X2 + ... + Xп -> сумма всех чисел/sum of all the numbers (sanX) 
#include <iostream> 
#include <vector> 

void appr(const std::vector<float>& x, const std::vector<float>& y) 
{ 
    int n = x.size(); 
    float sanX = 0, sanY = 0, sanXY = 0, sanX2 = 0; 
    for (int i = 0; i < n; ++i) 
    { 
        sanX += x[i]; 
        sanY += y[i]; 
        sanXY += x[i] * y[i]; 
        sanX2 += x[i] * x[i]; 
    } 
    float a = (n * sanXY - sanX * sanY) / (n * sanX2 - sanX * sanX); 
    float b = (sanY - a * sanX) / n; 
    std::cout << " appr : y = " << a << "x + " << b << std::endl; 
} 
int main() 
{ 
    std::vector<float> x = {0,1,2,3,4,5,6,7,8,9,10} , y = {4,10,3,7,8,4,10,10,8,4,8}; 
    appr(x, y); 
    return 0; 
}
