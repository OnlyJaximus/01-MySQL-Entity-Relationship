# 01-MySQL-Entity-Relationship & Relational model

https://app.diagrams.net/    ctrl+u = underscore (primary key)

-----------------------------------------   Entity-Relationship  --------------------------------------------------------- <br/>
                                          DIJAGRAM ODNOSA ENTITETA 

- Entity-Relationship ER model, u njemu se identifikuju atributi koji su primarni kljucevi tih tabela jer su jedinstveni.<br /><br />

- Kada se kreira relacioni model, dobra praksa je da se kreira SUROGAT kljuc, odnosno ID koji je autogenerisan. <br />
a) Korisnik toga nije svestan - korisnik ce i dalje koristiti ono sto smatra kljucem (npr. broj indexa za studenta ili maticni broj za osobu)<br />
b) Autogenerisani kljuc olaksava modelovanje veza, ubrzava proces pisanja koda, olaksava izemene itd.<br />

Entity-Relationship ER model:

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
![git](https://user-images.githubusercontent.com/56784702/208663265-1bd35348-e8a3-4790-bc1c-d010ba42eea8.png) <br/>

 ----------------------------------------------- RESENjE ZADATKA BROJ 2  ------------------------------------------------------------------ <br/>
 
                                             *** Entity-Relationship ***  
                                             
-Entity-Relationship ER model, u njemu se identifikuju atributi koji su primarni kljucevi tih tabela jer su jedinstveni.
 
ENTITETI: student, predmet, profesor <br/>

Atributi studenta: broj_indexa, ime, prezime, godina_upisa, godina_rodjenja <br/>
Atributi predmeta: sifra, naziv, broj_kredita <br/>
Atributi prfesora: jmbg, ime, prezime <br/>

GLAGOL: 
1- Student mora PRIJAVITI bar jedan predmet (PRIJAVLjUJE)  <br/>
2- Za predmet se zna koji profesor ga predaje (PREDAJE)  <br/>

KARDINALITET: 
1- Student mora prijaviti makar jedan predmet (1, n)  -> student mora imati makar jedan predmet a moze imati i vise.  <br/>
2- Predmet: Postoji samo jedan profesor na predmetu. Mogu postojati predmeti kojima jos nije dodeljen profesor  (0, 1)   <br/>
3- Profesor moze predavati vise predmeta, mora makar jedan. (1, n)  <br/>

Ako predmet nije niko prijavio, moze da ima 0 studenata ili moze da ima vise studenata. (0, n) <br/> <br/>

                                             *** Relational Model ***   
- ENTITETI: student, predmet, profesor. 
 
- ODNOS IZMEDJU STUDENTA I PREDMETA:  <br/> 
  1-(gledamo njihove max kardinalitete) n:n. Kada imamo vezu vise na vise, kreira se medju tabela koja ce se zvati student_predmet   Tabela student_predmet ce imati svoj primarni kljuc id, takodje ce imati i 2 strana kljuca (foreign key) koji ce gadjati id tih tablea. Ta 2 strana kljuca su student_id i predmet_id <br/>
 
 - ODNOS IZMEDJU PROFESORA I PREDMETA: 
  1- Za predmet se zna koji ga profesor predaje. Ako znamo tu informaciju, onda znaci da cemo unutar tabele PREDMET, moramo nekako proslediti neki podatak od profesora      a to ce biti PROFESOR_ID da bi znacli koji profesor predaje koji predmet. </br>
     - To je veza Predmet(0:1) gde jedan predmet mora da predaje makar jedan profesor i Profesor (0, n), jer profesor moze da ne predaje ni jedan predmet a moze i da predaje vise predmeta.
     -Ovo je veza 1:N, sto znaci da cemo, da cemo na strani gde je 1, ubacujemo strani kljuc profesor_id, da bi nam pokazao koji profesor predaje koji predmet.
- GLAGOLI:  <br/>
         student SLUSA predmet  <br/>
         profesor PREDAJE predmet  <br/>
         
* Za svaki entitet se kreira poseban id i ako se ne trazi. I on je primarni kljuc (PRIMARY KEY)  <br/>

student (id, broj_indexa, ime, prezime, godina_upisa, godina_rodjenja) <br/>
predmet (id, sifra, naziv, ects, profesor_id)  <br/>
profesor (id, jmbg, ime, prezime)  <br/>
student_predmet(id, student_id, predmet_id)  <br/>

![git novi](https://user-images.githubusercontent.com/56784702/208665329-7c1aeb1b-1d78-4c85-9e4f-8cb6943a98fb.png)

![resenje 2 zadattka](https://user-images.githubusercontent.com/56784702/208686002-6ef1620c-d27b-451e-a01e-b2136e3a54d7.png)


