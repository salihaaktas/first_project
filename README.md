\\ first_project

#include <stdio.h>
#include <string.h>

#define MAX_USERNAME_LENGTH 50
#define MAX_PASSWORD_LENGTH 50

// Sabit kullanıcı adı ve şifre
#define CORRECT_USERNAME "admin"
#define CORRECT_PASSWORD "1234"

// Fonksiyon prototipi
int girisYap(char *username, char *password);

int main() {
    char username[MAX_USERNAME_LENGTH];
    char password[MAX_PASSWORD_LENGTH];

    printf("Kullanıcı Adı: ");
    fgets(username, MAX_USERNAME_LENGTH, stdin);
    username[strcspn(username, "\n")] = '\0'; 
    
    printf("Şifre: ");
    fgets(password, MAX_PASSWORD_LENGTH, stdin);
    password[strcspn(password, "\n")] = '\0'; 

    if (girisYap(username, password)) {
        printf("Giriş başarılı! Hoş geldiniz.\n");
    } else {
        printf("Giriş başarısız! Kullanıcı adı veya şifre yanlış.\n");
    }

    return 0;
}

// Kullanıcı adı ve şifre doğrulama fonksiyonu
int girisYap(char *username, char *password) {
    // Kullanıcı adı ve şifreyi karşılaştır
    if (strcmp(username, CORRECT_USERNAME) == 0 && strcmp(password, CORRECT_PASSWORD) == 0) {
        return 1; 
    } else {
        return 0;  
    }
}
