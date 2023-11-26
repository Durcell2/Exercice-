# Exercice-
#include <iostream>
#include <string>

std ::string chiffrementCesar(const std ::string& message, int decalage) {
    std ::string resultat = "" ;
    for (char lettre : message) {
        if(isalpha(lettre)) {
            char base = (isupper(lettre)) ? 'A' : 'a';
            resultat += static_cast<char>((lettre-base+decalage)%26 +base);
        } else {
            resultat += lettre ;
        }
    }
    return resultat ;
}

int main() {
    std ::string message ;
    int decalage ;
    int choix;
    std::string messageChiffre;
    std::string messageDechiffre;

    std ::cout << "Entrez le message : " ;
    std ::getline(std ::cin, message) ;

    do{
        std ::cout << "1- Chiffrement"   << std::endl   << "2- Dechiffrement"   << std::endl ;
        std ::cout << "Entrez votre choix : " ;
        std ::cin >> choix ;
    }while(choix < 1 || choix > 2);

    do{
        std ::cout << "Entrez le decalage : " ;
        std ::cin >> decalage ;
      }while(decalage < 0 || choix > 25);

    if(choix==1){
        messageChiffre = chiffrementCesar(message, decalage) ;
        std ::cout << "message chiffre : "  << messageChiffre << std ::endl ;
    }else if(choix==2){
        messageDechiffre = chiffrementCesar(message, decalage*-1) ;
        std ::cout << "Message dechiffre : "  << messageDechiffre << std ::endl ;
    }
    return 0 ;
}
