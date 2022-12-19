# 01-MySQL-Entity-Relationsip

ENTITET: 
1- student 
2- profesor
3- predmet
4- katedra

-----------------------------------------------------------------------------------------------------------------

GLAGOL: 
1- odnos izmedju studdenta i predmeta je SLUSA
2- odnos izmedju profesora i predmeta je PREDAJE
3- katedra PRIPADA preddmetu
4- odnos izemdju profesora i katedre je RADI

-----------------------------------------------------------------------------------------------------------------

KARDINALITET:
1- student slusa 1 ili vise predmeta  min 1 a max je n (1, n)
2- predmet slusa jedan ili vise studenata (1, n)

3- nastavnik ne mora da predaje ni jedan predmet a moze da predaje i vise predmeta (0, n)
4- predmet ne mora da predaje ni jedan nastavnik a mogu da ga predaju i vise nastavnika (0, n)

5- katedra mora imati makar jedan predmet a moze ih imati i vise (1, n)
6- svaki predmet pripada jednoj katedri (jedan predmet ne moze da bude na vise katedri) (1, 1)

7- nastavnik MOZE da radi samo na jednoj katedri (0, 1)

-----------------------------------------------------------------------------------------------------------------

ATRIBUTI:
student => 1- broj_index (public_key)
           2- godina_studija
           3-ime prezime
           
nastavnik => 1- sifra (public_key)
             2- ime_prezime
             3- zvanje
             4- plata
             
predmet   => 1- sifra (public_key)            
             2- naziv
             3-broj_casova
             
katedra   => 1- sifra (public_key)            
             2- naziv

asocijativni entitet => u kojem definisemo ocenu i datum polaganja
           

![1](https://user-images.githubusercontent.com/56784702/208450361-8723eeb6-e7ac-48bd-80ea-43ee18ab23f9.png)
![2](https://user-images.githubusercontent.com/56784702/208450726-e5c211dd-f02c-456e-9348-7e5fa4c08254.png)

