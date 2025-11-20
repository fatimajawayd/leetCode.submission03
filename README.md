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
