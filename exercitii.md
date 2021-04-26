# Basic
1. Comanda 'file' se poate folosi pentru:
* a)listarea unor linii intr-un fisier text
* b) printarea continutului unui fisier
* c) determinarea tipului unui fisier -corect

2. O copie a fisierului nume 1 in directorul cu doua niveluri mai sus se face cu
* a)cp nume 1 -2/
* b)copy nume 1 ../
* c)cp nume1 ../.. - corect

3. Care din urmatoarele expresii reprezinta o cale absoluta?../home /
* a) ../home/clasa/rfc  -corect
* b) centre/cjtran
* c) home/centre/cjtran

4. Care din urmatoarele comenzi seteaza permisii ale fisierului numefis cu read, write si executie pentru proprietar, read si executie pentru grup si read pentru toti ceilalti?
* a) chmod 746 numefis  incorect fiindca (read, write si executie pentru proprietar, dar pentru grup este doar red)
* b) chmod 754 numefis - corect 
* c) chmod 574 numefis -incorect fiindca (read si executie pentru proprietar, dar nu si write)

5. Cream un fisier nou rosall.txt prin cncatenarea fisierelor ros1.txt si rosout.txt cu:
* a) cat ros1.txt rosout.txt >rosall.txt  -corect
* b) more ros1.txt rosout.txt
* c) file ros1.txt rosout.txt>rosall.txt

6. Pentru schimbarea permisiunilor de acces ale unui fisier, folosim comanda:
* a. chgrp
* b. chmod  - corect (chmod + -pentru adaugarea permisiuni, si - este pentru refuz)
* c. chown

7. Care este sintaxa generica a unei comenzi ?
* a) nume comanda, urmata de argumentte si apoi optiuni
* b) nume comanda, urmata de argumente
* c) nume comanda,urmata de optiuni si apoi argumente -corect

8. Calculeaza marimea unui folder? = RASPUNS : `du -sh practica/`

9. Statusul unui proces : RASPUNS : `ps -ux`
10. Ai urmatoarea structura de directoare: Desktop:-> Ana1 cu subfolder Ana4 si Ana2 cu subfolder Ana3. Incepe linia de comanda cd ~/Desktop/Ana2/Ana3 si completeaza comanda ca sa ajungi in Ana4. RASPUNS : `cd ~/Desktop/Ana2/Ana3/../../Ana1/Ana4`
11. Ce comandă este utilizată pentru a afișa numele sistemului de operare - `uname` , `uname -r` - versiunea.
12. Ce comandă este utilizată pentru a afișa toate fișierele, inclusiv fișierele ascunse în actualul și subdirectoarele sale? RASPUNS : `ls -aR`
13. Ce vrei să spui prin **Sed**? : Raspuns : 
* Sed este o comandă utilizată pentru transformarea secvențelor de text. 
* Comanda citește fișierele de intrare linie cu linie, apoi modifică fiecare linie corespunzător regulilor specificate într-un limbaj simplu, și afișează linia. 
* Sed este adesea folosit ca instrument de căutare și înlocuire.
14. Explicați despre diferitele versiuni ale comenzii Sed?
`GNU sed` -versiunea 4.8 a GNU sed, un editor de flux.
Drepturi de autor © 1998–2020 Free Software Foundation, Inc.
Se acordă permisiunea de a copia, distribui și / sau modifica acest document în condițiile licenței GNU Free Documentation License.
1.  Explicați sintaxa comenzii Sed. RASPUNS :
Comanda Sed ajuta să modificam fișierele, pentru a înlocui și găsi textul, pentru a căuta și înlocui un șir și este un șir de filtrare multifuncțional.
Sintaxă:  Sed „s / șir vechi / șir nou / g”;
* s: înseamnă substituire
* g: înseamnă fiecare linie toate aparițiile
* fără g: înseamnă fiecare linie prima apariție
16. Poti crea fisiere cu sed? RS: NU


# Incepatori 
1. Cum introduci 2 fisiere intr-un alt fisier :RASPUNS : `cat file1 file 2 >> file3`

2. Ce opțiune din comanda ls utilizată pentru a vizualiza numărul inodului fișierului? RASPUNS: `ls -i` - tipărim numărul index al fiecărui fișier.
3. Cum vă puteți conecta la alt sistem din rețea din sistemul dvs.? RASPUNS : `SSH` poate fi folosit pentru aceasta. Sintaxa este următoarea: `ssh <nume_utilizator> @ <adresa IP>`
4. Explicati comanda `free`. RASPUNS : această comandă este utilizată pentru a afișa memoria liberă, utilizată, swap disponibilă în sistem. Ieșirea este afișată în octeți.
5. Combinati toate rândurile într-unul singur : `paste -s exemplu2.txt` 
6. Am dori să vedem primele 15 linii din fisierul log  : `head -n 15 /var/log/syslog` 
7. `tr -d ello` hello h => transforma ori sterge caractere 
8. Stergeti toate dublurile de linii din fisierul ana.txt si apoi numarati-le :  RASPUNS : `uniq ana.txt` si `uniq -c ana.txt`




# Mediu
1. Scrieți o comandă care va face următoarele:
* Căutați toate fișierele din directoarele curente și ulterioare cu o extensie txt si  md
* scoateti cele cu md din rezultat (puteți utiliza comanda sed)
* utilizați rezultatul și utilizați o comandă grep pentru a căuta toate aparițiile cuvântului ANA în  fișiere.
* RASPUNS: `find ./ -type f \( -name "*.txt" -o -name "*.md" \) | sed -e /md$/d | grep -i "ana"`

2. Comanda `find / -name '*'`   -  va lista toate fișierele și directoarele recursiv începând de la root/

3. Ce comandă este utilizată pentru a înregistra o sesiune de conectare a utilizatorului într-un fișier? 
RASPUNS : `Script`  - inregistreaza toate actiunile sau comenzi din terminal si ce a fost afisat pe consola  din mometul in care ai activat comanda pana cand rulezi exit.

4. Cum se vede lista dispozitivelor montate pe Linux? RASPUNS : ruland comanda `mount l` – listeaza toate device-urile montate. De exemplu – stick, va fi afisat in folderul media din root , creand un director temporar, pentru a accesa contintul stick-ului.
5. Ai urmatoarea structura de fisiere:
Desktop: director Ana1 cu fisiere a1.txt, a2.txt si subfolder Ana2. In subfolder Ana1 se afla b1.txt, b2.txt si alt subfolder Ana 3, in care se afla fisierul c1.txt
Toate fisiere contin doua caractere: ab
Fiind in directorul ~/Desktop/Ana1, cauta folosind doar comanda grep, fisierele care contin ab, insa doar pe cele find folderul curent, adica Ana1, nu si in folderele copil ale lui. Apoi cauta, folosind doar comanda grep, fisierele care contin ab in folderul curent si in toate subfolder-ele lui. RASPUNS : `grep -r "ab"`-toate fisierele ce contin ab in folderul curent si in subfoldere, iar `grep "ab" *` -doar in folderul curent Ana1.
6. Sa spunem că am două fișiere pe care vreau să le unesc:\
fisier1.txt:  1 Radu     2 Ioana     3 Maria\
fisier2.txt : 1 Popescu  2 Popescu   3 Ionescu\
RASPUNS : `join fisier1.txt fisier2.txt`\
1 Radu Popescu
2 Ioana Popescu
3 Maria Ionescu
7. Dar cum am putea oare uni următoarele fișiere?\
fisier1.txt: Radu 1   Ioana 2   Maria 3\
fisier2.tx  :1 Popescu  2 Popescu   3 Ionescu\
RASPUNS : `join -1 2 -2 1 fisier1.txt fisier2.txt`\
1 Radu Popescu
2 Ioana Popescu
3 Maria Ionescu
8. Cum se elimină liniile goale dintr-un fișier specific utilizând comanda Sed? RASPUNS: 
`sed ‘/^$/d’ Sed_File.txt`; sau `sed 'n;d' Sed_File.txt`
Deoarece „^” indică începutul liniei și „$” indică sfârșitul liniei, „^ $” înseamnă linii goale. n N    Read/append the next line of input into the pattern space.
9. Cum să tipăriți numai linia goală utilizând comanda Sed? RASPUNS : `sed -n ‘/^$/p’ Sed_file.txt`  sau `sed -n 'n;p' Sed_File.txt`
10. Cum stergi cuvantul complexsql din fisier ? RASPUNS :`sed "s/complexsql//g" Sed_File.txt`
11. Afisati primul si ultimul rand din fisier cu sed. RASPUNS : `sed -n "1p;$p" Sed_File.txt`
12. Scrieți o comandă pentru a duplica fiecare linie într-un fișier? RASPUNS : `sed "p" Sed_File.txt`
13. Scrieți o comandă pentru a duplica fiecare linie într-un fișier? RASPUNS : `sed "p" Sed_File.txt`
14. Scrieți o comandă pentru a duplica liniile goale într-un fișier? RASPUNS: `sed "/^$/p" Sed_File.txt`
15. Scrieți o comandă sed pentru a imprima liniile care nu conțin cuvântul „complex”? RASPUNS : `sed -n '/complex/!p' Sed_File.txt` sau `sed '/complex/d' Sed_File.txt`