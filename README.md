#include <stdio.h>
 
#define MAX_LINE_LENGTH 1000
 
int main() {
    FILE    *textfile;
    char    ch;
    char f='a';
    int i;
    textfile = fopen("myrecord4.txt", "r");
    if(textfile == NULL)
        return 1;
     
    while((ch = fgetc(textfile))!=EOF) {
        putchar(ch);
        for(i=0;ch!='\0';i++) {

        switch(f) {
        case 'a': if(ch==' ' || ch=='\n' || ch=='\t') f='a';
        else if(ch=='/'){ f='b'; 
		case 'b': if(ch=='*') f='z';
		else if(ch=='/') f='x';}
        else if(ch=='(') f='c';
        else if(ch==')') f='d';
        else if(ch=='+') f='e';
        else if(ch=='-') f='h';
        else if(ch=='*') f='g';
        else if(ch==':'){ f='i';case 'i': if(ch=='=') f='l';}
        
        else if(ch=='.') {
		f='k'; case 'k': if (ch=='0'||ch=='1'||ch=='2'||ch=='3'||ch=='4'||ch=='5'||ch=='6'||ch=='7'||ch=='8'||ch=='9'){
			
		 f='y';case 'y': if (ch=='0'||ch=='1'||ch=='2'||ch=='3'||ch=='4'||ch=='5'||ch=='6'||ch=='7'||ch=='8'||ch=='9') f='y';}}
        
        break;
        }
     }
    }
    if(f=='b' || f=='c' || f=='d' || f=='e' || f=='h' || f=='g' ||  f=='l' || f=='y' )
       printf("\nString is accepted");
    else printf("\nString is not accepted");
    fclose(textfile);
    return 0;
}
