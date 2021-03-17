# FUNCTIONS-1-UNIT3
CAROLINA TORRES ARJONA
DATA 1A.

# F1-1

  #include <stdio.h>
  #include <string.h>

  /*create a function that receives a string 
  and print the inverted string, remember that
  to print an element i you can
  use printf("%c",string[i]); */
  char S[30];

  void INVERT(char x[])
  {
    char inv[30];
    int i, ll,c;
    c=0;

   ll=strlen(x);
   for(i=ll-1;i>=0;i--)
    {
      inv[c]=x[i];
      c=c+1;
    }
    printf("%s",inv);
  }

  int main() {

   fgets(S,30,stdin);
   INVERT(S);

   return 0;
  }
  
# F1-2

  #include <stdio.h>
  #include<string.h>
  /*create a function that returns 0 if both have the same length and 1 if is different.
  */
  int SAMEORNOT(char x[], char y[])
  {
    int i, N1, N2;
    N1=strlen(x); //strlen da la longitud de la palabra
    N2=strlen(y);
    if(N1==N2)
    i=0;
    else
    i=1;

   return i;
  }

  int main() {
    char W[30], w[30];
    int s;
    printf("INSERT WORD 1\n");
    fgets(W,30,stdin);
    printf("\nINSERT WORD 2\n");
    fgets(w,30,stdin);
    s=SAMEORNOT(W,w);
    printf("\n  SI ES 1 Ó 0\nDIFERENTE LONGITUD: 1\nIGUAL LONGITUD:     0\n");
    printf("\nLAS PALABRAS TIENEN %i",s);
    return 0;
  }

# F1-3

  #include <stdio.h>
  #include <string.h>
  #define MAX 30

  char S1[MAX], S2[MAX];
  /*create a function that returns 0 if both strings 
  have the same elements, and when there's a different 
  element. returns the first different char... an 
  example: "var1X" and "var1Y", returns "X"*/

  //USANDO 2 FUNCIONES Y LA MAIN!!!!!!!!!
  //FUNCION PARA CCOMPARAR LONGU¡ITUD
  int sameornotelements(char x[MAX],char y[MAX])
  {
  int nx, ny, sone;

  nx=strlen(x);
  ny=strlen(y);

  if(nx==ny)
  sone=0;
  else
  {
  sone=1;
  printf("DO NOT HAVE THE SAME LENGHT");
  }//TERMINA FUNCION QUE DA PARAMETRO DE LONGITUD
  return sone;
  }

  //FUNCION PARA DETERMINAR LA DIFERENCIA
  void differentchar(char x[MAX], char y[MAX])
  {
    int determin, str, i, breakk, aversisi;
    str=strlen(x);
    determin=sameornotelements(x,y);
    if(determin==0)
    {
      for(i=0;i<=str;i++)
      {
  aversisi=0;//SI SE MANTIENE EL VALOR EN 0 AL FINAL DE LA FUNCION ES QUE SI ES LA MISMA PALABRA
        if(x[i]!=y[i])
        {
          breakk=i;
          aversisi=1;//CONTADOR QUE DICE QUE NO ES LA MISMA PALABRA
           printf("THIS IS THE FIRST DIFFERENT ELEMENT: %c",x[breakk]);
          break;
        }
      }
      if(aversisi==0)
      printf("0");
    }//CONDICION PARA SABER SI ES LA MISMA PALABRA

   //if(aversisi==0)
   //printf("0");

  //TERMINA FUNCION DE DIFERENCIA
  }

  int main()
   {

   printf("INSERT FIRST STRING\n");
   fgets(S1,MAX,stdin);

   printf("INSERT SECOND STRING\n");
   fgets(S2,MAX,stdin);
   differentchar(S1,S2);
   return 0;
   }



# F1-4

  #include <stdio.h>
  #include <string.h>
  #define MAX 30


  // PALINDROMO 
  char S[MAX];

  int INVERT(char x[MAX])
  {
    int mylen, i, ol;
    ol=0;
    mylen = strlen(x)-1;
  for(i=mylen-1;i>=0;i--)//VA REVIRTIENDO LA PALABRA
    {

      if(x[i]!=x[mylen-i-1])//COMPARA LOS CARACTERES
      {
      ol=ol+1;
       break;//CON UNO QUE ENCUENTRE DIFERENTE DEJA DE COMPARAR
      }
      else 
      {
      ol=ol+0;//LA SUMA DA 0 CUANDO NO HAY NINGUNA DIFERENCIA
      }
    }
    return ol;
  }


  int main() {

  int resultado;

  fgets(S,MAX,stdin);
  resultado=INVERT(S);//LLAMO LA FUNCION METIENDOLA EN UNA VARIABLE DE ETSA FUNCION
  if(resultado!=0)
  {
    printf("0 NO ES PALINDROMO");
  }
  else
    printf("1 SI ES PALINDROMO");
  return 0;
  }

# F1-5
