# 01-MySQL-Entity-Relationship & Relational model

https://app.diagrams.net/    ctrl+u = underscore (primary key)

-----------------------------------------   Entity-Relationship  --------------------------------------------------------- <br/>
                                          DIJAGRAM ODNOSA ENTITETA 

ENTITET: <br />

1- student  <br/>
2- profesor <br/>
3- predmet <br/>
4- katedra <br/>



GLAGOL: <br/>

1- odnos izmedju studdenta i predmeta je SLUSA <br/>
2- odnos izmedju profesora i predmeta je PREDAJE <br/>
3- katedra PRIPADA preddmetu <br/>
4- odnos izemdju profesora i katedre je RADI <br/>


KARDINALITET: <br/>
1- student slusa 1 ili vise predmeta  min 1 a max je n (1, n) <br/>

2- predmet slusa jedan ili vise studenata (1, n) <br/>

3- nastavnik ne mora da predaje ni jedan predmet a moze da predaje i vise predmeta (0, n) <br/>
4- predmet ne mora da predaje ni jedan nastavnik a mogu da ga predaju i vise nastavnika (0, n) <br/>

5- katedra mora imati makar jedan predmet a moze ih imati i vise (1, n) <br/>
6- svaki predmet pripada jednoj katedri (jedan predmet ne moze da bude na vise katedri) (1, 1) <br/>

7- nastavnik MOZE da radi samo na jednoj katedri (0, 1) <br/>


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

           
----------------------------------------------- Relational Model  ------------------------------------------------------------------ <br/>
Kod relacionih modela, primarni kljuc je uvek ID. <br/>
      ODNOS STUDENT I PREDMET  
* Odnos izmedju studenta i predmeta (gledamo max kardinalitet n:n), onda znaci da ide medju tabela izmedju njih. <br/>
* Njihova veza ima 2 atributa veze a to su datum_polaganja i ocena i zato se kreira medju tablea student_predmet. <br/>

       ODNOS PREDMET i KATEDRA  
* Odnos izmedju predmet i katedre (gledamo max kardinalitet 1:n). Kada imamo 1 prema vise, u tabeli predmet se stavlja katedra_id jer katedra moze da ih ima vise. <br/>
* U ovom slucaju 1:n gledamo onaj koji je 1, u ovom slucaju to je predmet, on ce imati strani kljuc onaj koji je n, u ovom slucaju katedra.<br/>
* Zato se u tabeli predmet dodaje jos atribut katedra_id    <br/>

     ODNOS PROFESOR i KATEDRA   <br/>
* Odnos izmedju profesor i katedre (gledamo max kardinalitet 1:n). To znaci, unutar profesor imacemo strani kljuc na katedru a to je katedra_id. <br/>
 
    ODNOS PROFESOR i PREDMET   <br/>
* Odnos izmedju profesor i predmet (gledamo max kardinalitet n:n) a to je odnos vise na vise. To znaci da ide medju tabela izmedju njih. <br/>
* Tabela sa imenom profesor_predmet <br/>

ENTITETI: student, katedra, predmet, profesor <br/>
ATRIBUTI od svakog entiteta <br/>

student (id, broj_indexa, godina_studija, ime, prezime) <br/>
katedra (id, sifra, naziv) <br/>
predmet (id, sifra, naziv, broj_casova, katedra_id) <br/>
student_predmet (id, student_id, predmet_id, datum_polaganja, ocena) <br/>
profesor (id, sifra, ime, prezime, zvanje, plata, katedra_id) <br/>
profesor_predmet(id, profesor_id, predmet_id) <br/>

![1](https://user-images.githubusercontent.com/56784702/208450361-8723eeb6-e7ac-48bd-80ea-43ee18ab23f9.png)
![git](https://user-images.githubusercontent.com/56784702/208663265-1bd35348-e8a3-4790-bc1c-d010ba42eea8.png)
![git novi](https://user-images.githubusercontent.com/56784702/208665329-7c1aeb1b-1d78-4c85-9e4f-8cb6943a98fb.png)

