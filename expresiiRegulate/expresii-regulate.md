# Expresii regulate 
Expresiile regulate sunt șiruri speciale de caractere care reprezintă un șablon (model) de căutare. De asemenea cunoscute că “regex” sau “regexp”, acestea ajută programatorii să potrivească, să caute și să înlocuiască texte.

Cu ajutorul expresiilor regulate poţi găsi sau înlocui anumite părţi dintr-un text. Sunt o metodă puternică de verificare pentru validitatea adreselor de e-mail, domenii de internet sau coduri poştale. Un e-mail valid trebuie să se muleze pe un model prestabilit. Cu RegEx putem verifica dacă o adresă e-mail se mulează sau nu se mulează pe respectivul model. Deasemenea cu ajutorul expresiilor regulate putem să analizăm fişiere tot mai mari de text în căutarea informaţiilor dorite.

De exemplu, pentru a găsi cuvântul "mere" în stringul `"Ana are mere."`, poate fi folosită următoarea expresie regulată: `/mere/` . Nu este necesară folosirea ghilimelelor în cadrul expresiilor regulate.
* `simbolul *`  - reprezintă conceptul de “orice” => `s^The .* hack$` -Sirurile care incep cu "the " si se sfarsesc cu " hack"
* `simbolul ^ (ancora)` - inceputul unui rand => `^[hc]at` se potrivește cu "hat" și "cat", dar numai de la începutul șirului sau rândului.
* `simbolul $` - sfarsitul unui rand
  * `^tură$` se va potrivi doar cu șirul "tură", nu și cu "tură  " sau "  tură" sau "alătură".
  *  `[hc]at$` se potrivește cu "hat" și "cat", dar numai la sfârșitul șirului sau rândului.
* `simbolul punct .` - gasirea unui anumit caracter:
    * `b.t` se potrivește cu b2t, bft, bJt sau cu orice șir de trei caractere care începe cu b și se termină cu t.
    * `.at` se potrivește cu orice șir de trei caractere terminat cu "at", inclusiv "hat", "cat", și "bat".
* `Simbolul + `  - caracterul (expresia) anterior acestui semn se poate repeta odata si de cate ori e posibil (de la 1 la infinit) => `^www.[a-z0-9]+.ro$`   - Reprezinta sirurile "www.---.ro" unde '---' poate fi orice litera sau cuvant ce contine litere mici si numere
* `Simbolul ?` - caracterul (expresia) anterior acestui semn se poate repeta ce mult odata.
* `<>`   - un cuvant intreg
* `(|)`   - lista de optiuni SAU
* `{m, n} `  - repetarea expresiei de la "m" la "n" ori
* `paranteze[]` - ne permit să specificăm caracterele în interiorul lor care trebuiesc găsite. _Atentie Key sensitive!_
    * `d[aou]r` -va găsi și va returna: dar, dor, dur
    * `d[^u]r` - va găsi și va returna: dar și dor dar nu și dur. Simbolul tip ancoră ^ atunci când este folosit în interiorul parantezelor drepte semnifică orice cu excepția caracterelor din interiorul parantezelor drepte.  
    * `d[a-c]r` - va găsi și va returna tipare ca dar, dbr, and dcr. Parantezele drepte pot folosi deasemenea intervale pentru a crește numărul de caractere pe care doriți sa îl folosiți.
* **Operatori pentru specificarea repetițiilor** -  o expresie regulată poate fi urmată de un simbol special care arată de câte ori trebuie să se repete caracterul sau grupul de caractere pe care îl urmează:
    * `asteriscul (*)`- înseamnă zero sau mai multe apariții ale caracterului pe care îl urmează; de exemplu, dacă vom scrie `bc*`, expresia regulată se va potrivi cu orice șir format dintr-un b și urmat de oricâte caractere c (chiar și de niciunul!)
    * `semnul plus (+)` - reprezintă una sau mai multe apariții (potrivește o dată sau de mai multe ori);
    * `semnul întrebării (?)` - reprezintă zero potriviri sau una singură.
* **Operatorul de alternare (|)** - bara verticală separă două posibile potriviri; de exemplu, expresia regulată `mere|pere` se potrivește atât cu mere, cât și cu pere= gr(a|e)y
    * `(ci|co)tim`   - Reprezinta "citim" si "cotim"
* `Parantezele rotunde ( )` - parantezele rotunde înconjoară subexpresiile (pentru gruparea expresiilor regulate); rescriind un exemplu de mai sus, vom observa că operatorul astersic * se va aplica grupului: expresia regulată (bc)* se va potrivi cu mai multe repetiții ale grupului de caractere bc (chiar și cu niciunul).
* `Escaping (\)`  - dacă vrem să facem o potrivire cu unul sau mai multe caractere speciale care să nu fie tratate ca operatori ai expresiei regulate, cum ar fi punctul, trebuie să-l precedem cu caracterul escape (reprezentat printr-un backslash); de exemplu, pentru a face o potrivire cu un hostname (să spunem subdomeniu.bobses.eu), vom folosi caracterul escape pentru puncte, astfel: subdomeniu\.bobses\.eu

* `grep [opțiuni] regexp [fișiere]`  : grep -E 'expresie-regulată', exemple:
    * `egrep -w 'cuvânt1|cuvânt2' fișier` 

## Exercitii practice:
1. Sa presupunem ca dorim sa specificam intr-o expresie regulata sirurile "sat", "mat" si "lat". Pentru aceasta, avem nevoie de expresia regulata `[sml]at`. Semnificatia acestei expresii regulate este urmatoarea: "alege oricare din literele 's', 'm' si 'l' si scrie dupa litera respectiva literele 'at'".
2. expresia regulata care corespunde oricarui caracter care nu este o litera mica: Raspuns :`[^a-z]`
3. expresia regula care corespunde unui numar de una sau doua repetari ale oricaruia dintre sirurile "sat", "mat" sau "lat". Raspuns : `([sml]at){1 ,2}`
4. Reprezentati o înmultire intre doua numere. Raspuns : `[0-9]\*[0-9]`.
5. SelectaTI prima parte a adreselor URL, cel care spune „http” sau „https”. Raspuns : `grep -E 'https?' regex`
6. Dorim să găsim liniile în care apar anii 2002 și 2004 in fisierul proiect.txt. Raspuns : Pare a fi două căutări, dar se pot face simultan astfel: `grep '200[24]' proiect.txt`
7. Vrem să găsim cuvinte care au între 3 și 6 litere mici. Raspuns : `grep '[a-z]\{3,6\}' regex`