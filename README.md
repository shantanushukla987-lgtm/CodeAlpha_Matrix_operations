#include <stdio.h>

void addMatrix(int a[10][10], int b[10][10], int r, int c) {
    int i, j;
    printf("\nMatrix Addition:\n");
    for(i=0;i<r;i++) {
        for(j=0;j<c;j++)
            printf("%d ", a[i][j] + b[i][j]);
        printf("\n");
    }
}

void multiplyMatrix(int a[10][10], int b[10][10], int r, int c) {
    int i, j, k, mul[10][10]={0};

    for(i=0;i<r;i++)
        for(j=0;j<c;j++)
            for(k=0;k<c;k++)
                mul[i][j] += a[i][k] * b[k][j];

    printf("\nMatrix Multiplication:\n");
    for(i=0;i<r;i++) {
        for(j=0;j<c;j++)
            printf("%d ", mul[i][j]);
        printf("\n");
    }
}

void transposeMatrix(int a[10][10], int r, int c) {
    int i, j;
    printf("\nTranspose of Matrix:\n");
    for(i=0;i<c;i++) {
        for(j=0;j<r;j++)
            printf("%d ", a[j][i]);
        printf("\n");
    }
}

int main() {
    int a[10][10], b[10][10], r, c, i, j;

    printf("Enter rows and columns: ");
    scanf("%d %d", &r, &c);

    printf("Enter Matrix A:\n");
    for(i=0;i<r;i++)
        for(j=0;j<c;j++)
            scanf("%d", &a[i][j]);

    printf("Enter Matrix B:\n");
    for(i=0;i<r;i++)
        for(j=0;j<c;j++)
            scanf("%d", &b[i][j]);

    addMatrix(a, b, r, c);
    multiplyMatrix(a, b, r, c);
    transposeMatrix(a, r, c);

    return 0;
}
