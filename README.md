//KUTUPHANE YONETIM SISTEMI//
#include<stdio.h>
#include<stdlib.h>
#include<string.h>

struct library{
  char book_name[20];
  char author[20];//yazar
  int pages;//sayfa sayisi
  float price;//satis fiyati
};
int main() {
  struct library lib[100];
  int input=0;
  int i=0;
  int j;


  while(input!=5) {
    printf("\n\nKUTUPHANE YONETIM SISTEMI\n\n");
    printf("1.Kitap bilgisini ekleyin\n");
    printf("2.Kitap bilgisini gosterin\n");
    printf("3.Yazara ait kitaplari listeleyin\n");
    printf("4.Kutuphanedeki toplam kitap sayisini goster\n");
    printf("5.Cikis");

    printf("\nLutfen seciminizi yapin");
    scanf("%d",&input);


    switch(input){

      case1:
      if (i<100) {
        printf("Kitap adi girin");
        scanf("%s",lib[i].book_name);
        printf("Kitap yazarini girin =");
        scanf("%s",lib[i].author);
        printf("Kitap sayfa sayisini girin");
        scanf("%d",&lib[i].pages);
        printf("Kitabin satis fiyatini girin");
        scanf("%f",&lib[i].price);
        i++;
      }
      else {
        printf("Kutuphane dolu. Kitap elenemez");
      }
      break;

      case 2:
        if (i==0) {
          printf("Kutuphanede kitap yok.\n");
        }else {
          for(j=0;j<i;j++){
            printf("%d.kitabim:\n",j+1);
            printf("Kitap ismi:%s\n",lib[j].book_name);
            printf("Kitap yazari :%s\n",lib[j].author);
            printf("Kitap sayfasi:%d\n",lib[j].pages);
            printf("Kitap fiyati:%f\n",lib[j].price);
            printf("\n");
          }
        }
      break;
      case 3:{
        char author[20];
        int found=0;
        printf("Yazari girin");
        scanf("%s",author);
      for(j=0;j<i;j++){
        if(strcmp(author,lib[j].author)==0){
          printf("%s yazarina ait kitaplar :\n",lib[j].author);
          printf("Kitap ismi %s :\n",lib[j].book_name);
          printf("Kitabin yazari %s :\n",lib[j].author);
          printf("Kitabin sayfa sayisi %d :\n",lib[j].pages);
          printf("Kitabin fiyati :%f\n",lib[j].price);
          printf("\n");
          found=1;
        }
      }
      if(!found) {
        printf("Yazara ait kitap bulunamadi\n");
      }
        break;
      }
      case 4:
        printf("\nToplam kitap sayisi:%d",i);
      break;
      case 5:
        exit(0);
    }
  }
  return 0;
}

