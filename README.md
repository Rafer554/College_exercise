#include <stdio.h>
#include <locale.h>

int main() {
    setlocale(LC_ALL, "portuguese");

    int coluna;
    int linha;
    float vetor[3]; 
    int i;
    int j;

    printf("\nInforme a quantidade de linhas: ");
    scanf("%d", &linha);
    printf("Informe a quantidade de colunas: ");
    scanf("%d", &coluna);

    printf("Digite seu vetor para multiplicação:\n");
    for (i = 0; i < 3; i++) { 
        scanf("%f", &vetor[i]);
    }

    float matriz[linha][coluna];

    for (i = 0; i < linha; i++) {
        for (j = 0; j < coluna; j++) {
            printf("Insira o valor da linha %d e coluna %d da matriz: ", i + 1, j + 1);
            scanf("%f", &matriz[i][j]);
        }
    }

    printf("\nMatriz gerada:\n");
    for (i = 0; i < linha; i++) {
        for (j = 0; j < coluna; j++) {
            printf("%6.2f ", matriz[i][j]);
        }
        printf("\n");
    }

    printf("\nProduto da multiplicação pelo vetor:\n");
    for (i = 0; i < linha; i++) {
        for (j = 0; j < coluna; j++) {
            matriz[i][j] *= vetor[j];
            printf("%6.2f ", matriz[i][j]);
        }
        printf("\n");
    }

    return 0;
}
