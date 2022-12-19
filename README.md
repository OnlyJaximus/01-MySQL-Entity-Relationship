# 01-MySQL-Entity-Relationship

https://app.diagrams.net/    ctrl+u = underscore (primary key)

ENTITET: <br />

1- student  <br/>
2- profesor <br/>
3- predmet <br/>
4- katedra <br/>

-----------------------------------------------------------------------------------------------------------------

GLAGOL: <br/>

1- odnos izmedju studdenta i predmeta je SLUSA <br/>
2- odnos izmedju profesora i predmeta je PREDAJE <br/>
3- katedra PRIPADA preddmetu <br/>
4- odnos izemdju profesora i katedre je RADI <br/>

-----------------------------------------------------------------------------------------------------------------
 
KARDINALITET: <br/>
1- student slusa 1 ili vise predmeta  min 1 a max je n (1, n) <br/>

2- predmet slusa jedan ili vise studenata (1, n) <br/>

3- nastavnik ne mora da predaje ni jedan predmet a moze da predaje i vise predmeta (0, n) <br/>
4- predmet ne mora da predaje ni jedan nastavnik a mogu da ga predaju i vise nastavnika (0, n) <br/>

5- katedra mora imati makar jedan predmet a moze ih imati i vise (1, n) <br/>
6- svaki predmet pripada jednoj katedri (jedan predmet ne moze da bude na vise katedri) (1, 1) <br/>

7- nastavnik MOZE da radi samo na jednoj katedri (0, 1) <br/>

-----------------------------------------------------------------------------------------------------------------

ATRIBUTI: <br/>
student => 1- broj_index (primary key) br/>
           2- godina_studija <br/>
           3-ime prezime <br/>
           
nastavnik => 1- sifra (primary key) <br/>
             2- ime_prezime <br/>
             3- zvanje <br/>
             4- plata <br/>
             
predmet   => 1- sifra (primary key)   <br/>         
             2- naziv <br/>
             3-broj_casova <br/>
             
katedra   => 1- sifra (primary key)     <br/>        
             2- naziv <br/>

asocijativni entitet => u kojem definisemo ocenu i datum polaganja <br/>
           

![1](https://user-images.githubusercontent.com/56784702/208450361-8723eeb6-e7ac-48bd-80ea-43ee18ab23f9.png)
![2](https://user-images.githubusercontent.com/56784702/208450726-e5c211dd-f02c-456e-9348-7e5fa4c08254.png)

