# Caso 2 — Binary propio: buffer overflow simple (laboratorio)

## 1. Objetivo
Crear y explotar (en laboratorio) un binario vulnerable para practicar todo el flujo: build → fuzz → debug → reverse → PoC controlado.

## 2. Código fuente (archivo `code/vuln.c`)
```c
#include <stdio.h>
#include <string.h>

void vuln(char *input) {
    char buffer[64];
    strcpy(buffer, input); // vulnerable to overflow
    printf("Procesado: %s\n", buffer);
}

int main(int argc, char **argv) {
    if (argc < 2) {
        printf("Uso: %s <input>\n", argv[0]);
        return 1;
    }
    vuln(argv[1]);
    return 0;
}
