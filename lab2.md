2\. Napisać i uruchomić program w C, który wczytuje liczbę naturalną n i drukuje wartość sumy kwadratów

    12 + 22 + 32 + . . . + n2 
    
    ```
         #include<stdio.h>
      int main () {
       int n;
       int i;
       int wynik=0;
      
        scanf("%d", &n);
        printf("n=%d \n", n );
     for (i = 1; i <= n; i++){
		        wynik=wynik+(i*i);
            printf("%d i= %d \n",i, wynik );
	     
	   } 
     return 0;
     }  
     
     ```
