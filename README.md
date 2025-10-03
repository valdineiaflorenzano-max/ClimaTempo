# ClimaTempo
O clima é o padrão das condições atmosféricas de uma região ao longo do tempo. Ele envolve temperatura, umidade, pressão, ventos e precipitação, influenciando a vida das pessoas, animais e plantas.


#include <stdio.h>
#include <stdio.h>
#include <stdio.h>
#include<stdio.h>  // Biblioteca padrão de entrada/saída

// ----------------- TEMPERATURA (7 dias) -----------------
int main() {
    float temp[7];    // Vetor para armazenar temperaturas da semana
    float soma = 0, media;   // Variáveis para soma e média
    int i;

    // Entrada de dados (temperaturas dos 7 dias) 
    for (i = 0; i < 7; i++) {
        printf("Digite a temperatura do dia %d: ", i+1);
        scanf("%f", &temp[i]);
        soma += temp[i];
    }
   
    // Cálculo da média semanal
    media = soma / 7;
  
    // Saída: mostra temperaturas e a média
    printf("\nTemperaturas da semana:\n");
    for (i = 0; i < 7; i++){
        printf("Dia %d: %.1f°C\n", i+1, temp[i]);
    }
    printf("\nTemperatura media da semana: %.2f°C\n", media);
    
    // ----------------- VENTO (5 dias * 3 turnos) -----------------
    float vento[5][3]; // 5 dias * 3 turnos (manhã, tarde, , noite)  // Matriz: 5 dias * 3 turnos
    int dia, turno;
    char *turnos[3] = {"manhã", "tarde", "noite"}; // Nomes dos turnos
    
    // Entrada de dados: velocidades do vento
    printf("digite a velocidade do vento (km/h:\n");
    for (dia = 0; dia < 5; dia++) {
        printf("\n--- dia %d ---\n" , dia +1);
        for (turno = 0; turno < 3; turno++) {
            printf("%s: ", turnos[turno]);
            scanf("%f", &vento[dia][turno]);
        }
    }       
            
            // Saída: tabela do vento
            printf("\ntabela de vento:\n");
                for(dia = 0; dia < 5; dia++) {
                    printf("Dia %d ->", dia + 1);
                    for (turno = 0; turno < 3; turno++){
                    printf("%s: %.1f ", turnos[turno], vento[dia][turno]);
                }
                printf("\n"); 
            } 

    // ----------------- CHUVA (4 bairros * 12 meses) -----------------       
    float chuva[4][12]; // 4 bairros * 12 meses   // Matriz: 4 bairros * 12 meses
    int bairro, mes;    // índices

    // Entrada de dados
    for (bairro = 0; bairro < 4; bairro++) {
        printf("\n--- Bairro %d ---\n", bairro + 1);
        for (mes = 0; mes < 12; mes++) {
            printf("Digite a chuva do mês %d: ", mes + 1);
            scanf("%f", &chuva[bairro][mes]);
        }
    }

    // Saída (resumo)
    printf("\n--- Resumo das chuvas ---\n");
    for (bairro = 0; bairro < 4; bairro++) {
        float soma = 0;
        for (mes = 0; mes < 12; mes++) {
            soma += chuva[bairro][mes];
        }
        printf("Bairro %d - Total anual: %.2f mm | Média mensal: %.2f mm\n",
            
            bairro + 1, soma, soma / 12);
    }

    return 0;

}
