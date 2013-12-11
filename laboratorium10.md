Zadanie1. W poniższym zadaniu (oznaczonym komentarzem) usunąć rekursję zastępując ją pętlą: 

PRZYKŁAD 1. (największy wspólny dzielnik dwóch liczb naturalnych)


```
/*
#include<stdio.h>
#include<stdlib.h>

// Oblicza najwiekszy wspolny dzielnik przy zalozeniu, ze
//   n >= 0  i  k >= 0  oraz
//   n+k > 0  czyli argumenty nie sa jednoczesnie rowne zeru

int  nwd (int n, int k) {
  if (n<0  ||  k<0  ||  n+k == 0) {
    printf ("\n  Argumenty maja byc nieujemne");
    printf ("\n  i nie jednoczesnie zerowe\n\n");
    exit(1);
  }
  else
    if (n<k)  return nwd(k,n);
    else
      if (k==0)  return n;
      else  return nwd(k, n%k);
}

int main () {
  int a, b;
  printf("Podaj dwie liczby naturalne: ");
  scanf("%i", &a); scanf("%i", &b);
  printf("\n  nwd(%i, %i) == %i\n\n", a, b, nwd(a,b));
  return 0;
}
*/

```

ROZWIĄZANIE:

```

#include<stdio.h>
#include<stdlib.h>

// Oblicza najwiekszy wspolny dzielnik przy zalozeniu, ze
//   n >= 0  i  k >= 0  oraz
//   n+k > 0  czyli argumenty nie sa jednoczesnie rowne zeru

int  nwd (int n, int k) {
  int i;
  if (n<0  ||  k<0  ||  n+k == 0) {

		
    
    printf ("\n  Argumenty maja byc nieujemne");
    printf ("\n  i nie jednoczesnie zerowe\n\n");
    exit(1);
  }
  else
  
  
   if (n<k) { 
   while(n!=0) {
	   i=n;
	   n=k%n;
	   k=i;
     } 
   return k;
 }
   else{
	   while(k!=0){
		   i=k;
		   k=n%k;
		   n=i;
		   }
         return n;
	 }
   
}

int main () {
  int a, b;
  printf("Podaj dwie liczby naturalne: ");
  scanf("%i", &a); scanf("%i", &b);
  printf("\n  nwd(%i, %i) == %i\n\n", a, b, nwd(a,b));
  return 0;
}

```


PRZYKŁAD 2. (rozkład liczby naturalnej na czynniki pierwsze)

```


/*

#include<stdio.h>
#include<stdlib.h>

#define DUZO 1000

int  k, cz[DUZO];

void  czynn (int n, int dzielnik) {
  if (n % dzielnik == 0) {
    cz[k] = dzielnik;  k = k+1;  czynn(n/dzielnik, dzielnik);
  }
  else
    if (dzielnik < n)  czynn(n, dzielnik+1);
}

int main () {
  int  n, i;
  printf("Podaj liczbe naturalna wieksza niz 1: "); scanf("%i", &n);
  while (n <= 1) {
    printf("Podaj liczbe naturalna wieksza niz 1: "); scanf("%i", &n);
  }
  k = 0;
  czynn(n, 2);
  printf("\n  Czynniki pierwsze liczby %i:\n  ", n);
  for (i=0; i<k; i=i+1)  printf("  %i", cz[i]);
  printf("\n\n");
  return 0;
}

*/

```

ROZWIĄZANIE:

```

#include<stdio.h>
#include<stdlib.h>

#define DUZO 1000

int  k, cz[DUZO];

void  czynn (int n, int dzielnik) { 
	dzielnik=1;
	while(dzielnik<n){
 
 dzielnik=dzielnik+1;
  
  
  while(n % dzielnik == 0) {
    cz[k] = dzielnik;  
    k = k+1;
      n=n/dzielnik;
  }
}
 
}

int main () {
  int  n, i;
  printf("Podaj liczbe naturalna wieksza niz 1: "); scanf("%i", &n);
  while (n <= 1) {
    printf("Podaj liczbe naturalna wieksza niz 1: "); scanf("%i", &n);
  }
  k = 0;
  czynn(n, 2);
  printf("\n  Czynniki pierwsze liczby %i:\n  ", n);
  for (i=0; i<k; i=i+1)  printf("  %i", cz[i]);
  printf("\n\n");
  return 0;
}


```




Rozwiazanie do zadania 2. (napisane na tablicy)

```
void petla1(double ciag1[],double ciag2[],double ciag[], int i1, int i2, int i) {
if(i1<n1 && i2<n2)
if(ciag1[i1]<ciag1[i1]) {
ciag[i]=ciag1[i1]; petla1(ciag1,ciag2,ciag,i1+1, i2, i+1);
}
else{
ciag[i]=ciag2[i2];petla1(ciag1,ciag2,ciag,i1,i2+1,i+1)
}
}petla1(ciag1,ciag2,ciag,0,0,0);

