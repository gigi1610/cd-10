#include <stdio.h>
#include <stdlib.h>

int main() {
    int *ponteiro;

    ponteiro = (int*) malloc(8 * sizeof(int));
    if(ponteiro == NULL) {
        printf("Erro! Memória não alocada.\n");
        return 0;
    }

    for(int i = 0; i < 8; i++) {
        ponteiro[i] = i;
    }

    ponteiro = (int*) realloc(ponteiro, 12 * sizeof(int));
    if(ponteiro == NULL) {
        printf("Erro! Memória não realocada.\n");
        return 0;
    }

    for(int i = 8; i < 12; i++) {
        ponteiro[i] = i;
    }

    for(int i = 0; i < 12; i++) {
        printf("ponteiro[%d] = %d\n", i, ponteiro[i]);
    }

    free(ponteiro);
    return 0;
}# cd-10
