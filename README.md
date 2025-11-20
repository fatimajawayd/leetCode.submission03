# leetCode.submission03

## PROBELM:01
### REVERSING ONLY VOWELS IN A STRING

```c
#include <stdio.h>
#include <string.h>

char* reverseVowels(char* s) {
    int i=0;
    int j = strlen(s) - 1;
    while(i<j){
        while(i<j && !(s[i]=='a'||s[i]=='e'||s[i]=='i'||s[i]=='o'||s[i]=='u'|| s[i]=='A'||s[i]=='E'||s[i]=='I'||s[i]=='O'||s[i]=='U')){
            i++;
        }
        while(i<j && !(s[j]=='a'||s[j]=='e'||s[j]=='i'||s[j]=='o'||s[j]=='u'||s[j]=='A'||s[j]=='E'||s[j]=='I'||s[j]=='O'||s[j]=='U')){
            j--;
        }
        char temp = s[i];
        s[i] = s[j];
        s[j] = temp;
        i++;
        j--;
    }     
    return s;
}     

int main(void){
    char s[50];
    printf("Enter the string: ");
    scanf("%s", s);
    char* result = reverseVowels(s);
    printf("Reversed string: %s\n", result);
    return 0;
}
```

## PROBELM:02
### RETURN THE FIRST PALINDROMIC WORD IN THE STRING

```c
#include <stdio.h>
#include <string.h>

char* firstPalindrome(char* words[], int wordsSize){
    for(int z=0; z<wordsSize; z++){
        int i=0;
        int j= strlen(words[z])-1;
        int p =1;

        while(i<j){
            if(words[z][i]!=words[z][j]){
                p = 0;
                break;
            }
            i++; j--;
        }
        if(p==1){
            return words[z];
        }
    }
    return "";
}

int main(){
    char* words[] = {"abc","car","racecar","cool"};
    int wordsSize = 5;
    char* result = firstPalindrome(words, wordsSize);
    printf("%s\n", result);
}
```

## PROBLEM:03
### 90 DEGREE (CLOCKWISE ROTATION)

```c
#include <stdio.h>
#include <string.h>

void rotate(int** matrix, int matrixSize, int* matrixColSize) {
    for(int i =0; i<matrixSize; i++){
        for(int j=i+1; j<matrixSize; j++){
            int temp = matrix[i][j];
            matrix[i][j] = matrix[j][i];
            matrix[j][i] = temp;
        }
    }

    for(int i =0; i<matrixSize; i++){
        for(int j=0; j<matrixSize/2; j++){
            int temp = matrix[i][j];
            matrix[i][j] = matrix[i][matrixSize-1-j];
            matrix[i][matrixSize-1-j] = temp;
        }
    }
    for (int i = 0; i < matrixSize; i++) {
        for (int j = 0; j < matrixSize; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }
}

int main(){
    int matrix[3][3] = {{1,2,3},{4,5,6},{7,8,9}};
    int* matrixPtr[3] = {matrix[0], matrix[1], matrix[2]};
    int matrixColSize[3] = {3, 3, 3};
    
    rotate(matrixPtr, 3, matrixColSize);
    return 0;
}

```
