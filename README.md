# media_habitante
#include <iostream>
#include <vector>
#include <cfloat>

using namespace std;

struct habitantes {
    int idade;
    char sexo;
    float remun;
}; 

int main() {
    int idade;
    char sexo;
    double remun;
    vector<habitantes> habitante;
    int count = 0;
    while(cin >> idade >> sexo >> remun) {
        habitante.push_back(habitantes());
        habitante[count].idade = idade;
        habitante[count].sexo = sexo;
        habitante[count].remun = remun;
        count++;
    }

    //letra a
    double soma = 0.0;
    for(int i = 0; i < habitante.size(); i++) {
        soma += habitante[i].remun;
    }
    double media = soma/(count);
    cout << "A media dos salarios e: " << media << endl;

    //letra b
    int maior = 0;
    int menor = 999999;
    for(int i = 0; i < habitante.size(); i++) {
        if(habitante[i].idade > maior) {
            maior = habitante[i].idade;
        }
        if(habitante[i].idade < menor) {
            menor = habitante[i].idade;
        }
    }
    cout << "A maior idade e: " << maior << endl;
    cout << "A menor idade e: " << menor << endl;

    //letra c
    int m_count = 0;
    for(int i = 0; i < habitante.size(); i++) {
        if(habitante[i].sexo == 'F') {
            m_count++;
        }
    } 
    cout << "A quantidade de mulheres na regiao e: " << m_count << endl;

    //letra d
    double menor_rem = DBL_MAX;
    int menor_ind;
    for(int i = 0; i < habitante.size(); i++) {
        if(habitante[i].remun < menor_rem) {
            menor_rem = habitante[i].remun;
            menor_ind = i;
        }
    }
    cout << "A idade da pessoa que possui o menor salario e: " << habitante[menor_ind].idade << " e o sexo e: " << habitante[menor_ind].sexo << endl;

    return 0;
}
