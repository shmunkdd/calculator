#include "stack.h"
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#define MAX_NUM_DIGITS 255

int isInteger(char* valString){
   if (!strcmp(valString,"0")) return 1;
   if (atoi(valString)==0) return 0;
   return 1;
}
int main(){
        arrayStack_t stack;
        initStack(&stack, 10);
        char character[MAX_NUM_DIGITS];
        printf("Calculator Input: ");
        scanf("%s", character);
        while(character[0]!='q'){
                if(isInteger(character)==1){
                        push(&stack, atoi(character));
                }
                else if (character [0]=='+'|| character[0]=='-'|| character[0]=='*' || character[0]=='/'){
                        int numero1,numero2;
                        if (pop(&stack,&numero1)==0){
                                printf("Empty Stack\n");
                        }
                        else if(pop(&stack, &numero2)==0){
                                printf("Not enough arguments\n");
                                push(&stack, numero1);
                        }
                        else if(character[0]=='+'){
                                push(&stack,numero2+numero1);
                                printf("%d\n", numero2+numero1);
                        }
                        else if(character[0]=='-'){
                                push(&stack,numero1-numero2);
                                printf("%d\n",numero1-numero2);
                        }

                        else if(character[0]=='*'){
                                push(&stack,numero2*numero1);
                                printf("%d\n",numero2*numero1);
                        }
                        else if(character[0]=='/'){
                                if(numero2==0){
                                        printf("ERROR: Division by 0 \n");
                                        int value;
                                        while(pop(&stack,&value)){
                                                continue;
                                        }
                                }
                                else{
                                        push(&stack,numero1/numero2);
                                        printf("%d\n", numero1/numero2);
                                }
                        }
                }
                else{
                        printf("ERROR: Invalid Input\n");
                }
                scanf("%s", character);
        }
