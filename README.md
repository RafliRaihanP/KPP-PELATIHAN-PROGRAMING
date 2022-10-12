// NAMA		:Rafli Raihan Pramudya
// NRP		:5025221266
// Jurusan	:Teknik Informatika

#include <iostream>
#include <cmath>
using namespace std;

#define GRAVITASI 10 //10 m/s^2
#define START_PENGUKURAN 1 //pengukuran dimulai dari 1 meter
#define SUDUT 45 //sudut elevasi tembakan

int mencari_V0(int x1, int x2){
    x1 -= x2;
      return x1;
}

int speed_dgn_loss(int x1){      
    int x2;
    if (x1 >= 1 && x1 <= 10){
        x2 = 1;
    }

    else if (x1 >= 11 && x1 <= 20){
        x2 = 3;
    }

    else if (x1 >= 21 && x1 <= 30){
        x2 = 5;
    }
    return x2;
}

int main() {
    int x1;
    float jarak;
    float KecepatanTangensial;
      cin >> x1;
    jarak = (pow(mencari_V0(x1,speed_dgn_loss(x1)),2)* sin(SUDUT*3.14159*2/180) / GRAVITASI) - START_PENGUKURAN;
    jarak = round(jarak);
    KecepatanTangensial = sqrt(jarak * GRAVITASI / sin(SUDUT*3.14159*2/180)) + speed_dgn_loss(x1);
      cout << jarak << " " << KecepatanTangensial << endl;
    return 0;
}
