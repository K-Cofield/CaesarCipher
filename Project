#include <stdio.h>
#include <string.h>

void Caesar_Encrypt(char *data, int key);
// Encryption function
void Caesar_Encrypt(char *data, int key) {
    for (int i = 0; data[i] != '\0'; ++i) {
        char c = data[i];
        if ('a' <= c && c <= 'z') {
            data[i] = (c - 'a' + key) % 26 + 'a';
        } else if ('A' <= c && c <= 'Z')
            data[i] = (c - 'A' + key) % 26 + 'A';

    }
}
//Decryption function
void Caesar_Decrypt(char *data, int key) {
    for (int i = 0; data[i] != '\0'; ++i) {
        char c = data[i];
        if ('a' <= c && c <= 'z') {
            data[i] = (c - 'a' - key + 26) % 26 + 'a';
        } else if ('A' <= c && c <= 'Z') {
            data[i] = (c - 'A' - key + 26) % 26 + 'A';
        }
    }
}

void Caesar_Decrypt(char *data, int key);

void writeToFile(char *filename, char *u, char *p, char *ip) {
    FILE *fp = fopen(filename, "w");
    fprintf(fp, "%s\n%s\n%s\n", u, p, ip);
    fclose(fp);
}

void readFromFile(char *filename, char *u, char *p, char *ip) {
    FILE *fp = fopen(filename, "r");
    fscanf(fp, "%s\n%s\n%s\n", u, p, ip);
    fclose(fp);
}

int main() {
    int caesar_key = 3;

    char username[50], password[50], ipv4[20];
    char encrypted_username[50], encrypted_password[50], encrypted_ipv4[20];

    while (1) {
        char choice;

        printf("Do you want to (E)ncrypt or (D)ecrypt? Press (Q) to Quit.\n");
        scanf(" %c", &choice);

        if (choice == 'E') {
            printf("Enter email: ");
            scanf("%s", username);

            printf("Enter password: ");
            scanf("%s", password);

            printf("Enter IPv4: ");
            scanf("%s", ipv4);

            strcpy(encrypted_username, username);
            strcpy(encrypted_password, password);
            strcpy(encrypted_ipv4, ipv4);

            Caesar_Encrypt(encrypted_username, caesar_key);
            Caesar_Encrypt(encrypted_password, caesar_key);
            Caesar_Encrypt(encrypted_ipv4, caesar_key);

            // Print encrypted data
            printf("Encrypted data:\nEmail: %s\nPassword: %s\nIPv4: %s\n",
                   encrypted_username, encrypted_password, encrypted_ipv4);

            writeToFile("encryptedData.txt", encrypted_username, encrypted_password, encrypted_ipv4);
        } else if (choice == 'D') {
            readFromFile("encryptedData.txt", encrypted_username, encrypted_password, encrypted_ipv4);

            Caesar_Decrypt(encrypted_username, caesar_key);
            Caesar_Decrypt(encrypted_password, caesar_key);
            Caesar_Decrypt(encrypted_ipv4, caesar_key);

            printf("Decrypted data:\nEmail: %s\nPassword: %s\nIPv4: %s\n",
                   encrypted_username, encrypted_password, encrypted_ipv4);
        } else if (choice == 'Q') {
            break;
        }
    }

    return 0;
}
