#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct employee {
    char name[50];
    int age;
    char position[50];
    int doj_day, doj_month, doj_year;
};

int namecmp(const void *a, const void *b) {
    struct employee *e1 = (struct employee *) a;
    struct employee *e2 = (struct employee *) b;
    return strcmp(e1->name, e2->name);
}

int datecmp(const void *a, const void *b) {
    struct employee *e1 = (struct employee *) a;
    struct employee *e2 = (struct employee *) b;
    if (e1->doj_year != e2->doj_year) {
        return e1->doj_year - e2->doj_year;
    } else if (e1->doj_month != e2->doj_month) {
        return e1->doj_month - e2->doj_month;
    } else {
        return e1->doj_day - e2->doj_day;
    }
}

int main() {
    int n, i;
    printf("Enter the number of employees: ");
    scanf("%d", &n);
    struct employee employees[n];
    for (i = 0; i < n; i++) {
        printf("Enter details of employee %d:\n", i + 1);
        printf("Name: ");
        scanf("%s", employees[i].name);
        printf("Age: ");
        scanf("%d", &employees[i].age);
        printf("Position: ");
        scanf("%s", employees[i].position);
        printf("Date of joining (dd/mm/yyyy): ");
        scanf("%d/%d/%d", &employees[i].doj_day, &employees[i].doj_month, &employees[i].doj_year);
    }
    qsort(employees, n, sizeof(struct employee), namecmp);
    printf("\nEmployee List sorted by name:\n\n");
    for (i = 0; i < n; i++) {
        printf("Name: %s\n", employees[i].name);
        printf("Age: %d\n", employees[i].age);
        printf("Position: %s\n", employees[i].position);
        printf("Date of Joining: %d/%d/%d\n\n", employees[i].doj_day, employees[i].doj_month, employees[i].doj_year);
    }
    qsort(employees, n, sizeof(struct employee), datecmp);
    printf("\nEmployee List sorted by date of joining:\n\n");
    for (i = 0; i < n; i++) {
        printf("Name: %s\n", employees[i].name);
        printf("Age: %d\n", employees[i].age);
        printf("Position: %s\n", employees[i].position);
        printf("Date of Joining: %d/%d/%d\n\n", employees[i].doj_day, employees[i].doj_month, employees[i].doj_year);
    }
    return 0;
}
