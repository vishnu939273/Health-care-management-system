#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_PATIENTS 100

struct Patient{
   char name[100];
   int age;
   char gender;
   char condition[200];
};

struct Patient patients[MAX_PATIENTS];
int numPatients = 0;

void clearScreen() {
   system("clear || cls");
}

void addPatient() {
  clearScreen();
   if (numPatients < MAX_PATIENTS) {
      printf("enter patient name:");
      scanf("%s", patients[numPatients].name);

      printf("enter patient age: ");
      scanf("%d",&patients[numPatients].age);

      getchar();
      printf("enter patient gender (M/F): ");
      patients[numPatients].gender = getchar();

      getchar();
      printf("enter patient condition: ");
      fgets(patients[numPatients].condition, sizeof(patients[numPatients].condition),stdin);
      patients[numPatients].condition[strcspn(patients[numPatients].condition, "\n")]='\0';
      numPatients++;
      printf("patient added sucessfully!\n");
      }
      else{
         printf("Maximum number of patients reached. \n");
      }
      getchar();
      }
void listPatients() {
    clearScreen();
    if (numPatients == 0) {
        printf("no patients avilable. \n");
        getchar();
        return;
    }
    printf("List of patients:\n");
    for (int i = 0; i<numPatients; i++){
        printf("%d. Name: %s | Gender: %c | Condition: %s\n",i+1,patients[i].age, patients[i].gender,patients[i].conditon);
        }
        getchar;
    }
