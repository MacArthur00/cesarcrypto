
# Cryptage et Décryptage de Messages

Ce programme C++ permet de crypter et de décrypter à volonté des messages en utilisant une simple substitution alphabétique, c'est le cryptage de César.

## Instructions d'utilisation

1. *Lancement du programme*
    - Compilez le code en utilisant un compilateur C++.
    - Exécutez le programme résultant.

2. *Opérations disponibles*
    - Choisissez entre crypter (1) ou décrypter (2) un message.
    - Entrez le message lorsque vous êtes invité.

3. *Cryptage*
    - Le programme ajoutera un décalage fixe (D) à chaque caractère alphabétique du message.

4. *Décryptage*
    - Le programme effectuera le décalage inverse pour décrypter le message.

5. *Répétition ou Quitter*
    - Choisissez 1 pour quitter le programme, ou tout autre chiffre pour crypter ou décrypter un autre message.

## Remarque
- Les messages cryptés/décryptés conservent la casse d'origine.
- Seuls les caractères alphabétiques sont affectés, les autres restent inchangés.

## Exemple d'utilisation

```cpp
//Voici mon code.

#include <iostream>
using namespace std;

int main()
{
  int decision;
do {       
          const int D = 3;        
          int choix;        
          string message;    
          cout << "Entrez le numéro de l'opération que vous souhaitez effectuer. \n 1. Crypter le message. \n 2. Décrypter le message." << endl;        cin >> choix;        while (choix != 1 && choix != 2) {            cout << "\n Vous devez choisir entre 1 et 2. \n Entrez le numéro de l'opération que vous souhaitez effectuer. \n 1. Crypter le message. \n 2. Décrypter le message." << endl;            cin >> choix;        }        cin.ignore();        string messageEnvoye = "";        if (choix == 1) {            cout << "\n Entrez le message à crypter." << endl;            getline(cin, message);            for (char caractere : message) {                if(caractere >= 'A' && caractere <= 'Z' || caractere >= 'a' && caractere <= 'z') {                    caractere = caractere + D;                    (caractere > 'Z' && caractere < 'a' || caractere > 'z') ? caractere = caractere - 26 : caractere = caractere;                    messageEnvoye = messageEnvoye + caractere;                } else {                    messageEnvoye = messageEnvoye + caractere;                }            }            cout << "Le message crypté est : " << messageEnvoye << "\n" << endl;        } else {            cout << "\n Entrez le message à décrypter." << endl;            getline(cin, message);            for (char caractere : message) {                if(caractere >= 'A' && caractere <= 'Z' || caractere >= 'a' && caractere <= 'z') {                    caractere = caractere - D;                    (caractere < 'A' || caractere > 'Z' && caractere < 'a') ? caractere = caractere + 26 : caractere = caractere;                    messageEnvoye = messageEnvoye + caractere;                } else {                    messageEnvoye = messageEnvoye + caractere;                }            }            cout << "\n Le message décrypté est : " << messageEnvoye << "\n" << endl;        }        cout << "\n        Choisissez 1 si vous voulez quitter le programme et un autre chiffre (différent de 1) si vous crypter ou décrypter un autre message. \n 1. Quitter \n 2. Continuer" << endl;        cin >> decision;    } while (decision != 1);  
    return 0;
}
