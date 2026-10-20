# 100 exercicis progressius de POO amb JavaScript i TypeScript — 2DAW

## Indicacions generals

- Llevat que l'enunciat indiqui el contrari, implementa les classes i els mètodes necessaris, no una solució basada únicament en funcions independents.
- Utilitza noms descriptius per a classes, propietats i mètodes.
- Quan un valor no sigui vàlid, decideix segons l'enunciat si cal rebutjar-lo amb `throw new Error(...)` o ignorar-lo.
- En els exercicis TypeScript, tipa explícitament les propietats, paràmetres i valors de retorn. No utilitzis `any` com a solució per defecte.
- Afegeix JSDoc a les classes i als mètodes públics.
- Escriu proves amb Vitest per comprovar els casos habituals, els límits i les entrades incorrectes.
- Els exercicis marcats **JS** es recomana fer-los primer en JavaScript; els marcats **TS**, en TypeScript. Els exercicis d'aplicació final es poden implementar en tots dos llenguatges.
- En TypeScript, recorda que `private` i `public` són comprovacions del compilador; les propietats `#privades` de JavaScript tenen privacitat en temps d'execució. No confonguis els dos mecanismes.

## Nota tècnica

- En JavaScript, `#camp` crea un camp privat real en temps d'execució.
- En TypeScript, `private camp` impedeix l'accés des del codi TypeScript durant la comprovació de tipus, però no equival a la privacitat nativa de `#camp`.
- Un getter no ha de retornar necessàriament una dada emmagatzemada: sovint és millor calcular valors derivats com ara el total, el volum o la mitjana.
- Un setter no és obligatori per a cada propietat. Si un valor no s'ha de modificar després de crear l'objecte, pot ser preferible no exposar cap setter.
- Els mètodes d'array no substitueixen el disseny de classes: s'han d'utilitzar per consultar i transformar col·leccions mantenint l'estat intern controlat.

# Bloc 1. Classes, instàncies i mètodes

## Exercici 1. Targeta de presentació (JS)
Crea una classe `Persona` amb les propietats `nom` i `edat`. El constructor ha de rebre els dos valors. Afegeix el mètode `presentar()` que retorni una frase amb el nom i l'edat. Crea tres instàncies i mostra'n les presentacions.

## Exercici 2. Producte de botiga (JS)
Crea una classe `Producte` amb `nom` i `preu`. Afegeix un mètode `preuAmbIVA(percentatge)` que retorni el preu final. Comprova diferents percentatges d'IVA sense modificar el preu original.

## Exercici 3. Comptador (JS)
Crea una classe `Comptador` que comenci a zero. Implementa `incrementar()`, `decrementar()` i `reiniciar()`. Afegeix `valorActual()` per consultar el valor. De moment, permet valors negatius.

## Exercici 4. Rectangle (JS)
Crea una classe `Rectangle` amb `amplada` i `alcada`. Implementa `calcularArea()` i `calcularPerimetre()`. Afegeix `esQuadrat()` que retorni un booleà.

## Exercici 5. Compte enrere (JS)
Crea una classe `CompteEnrere` que rebi un nombre enter inicial. El mètode `tic()` ha de restar-ne un, però no pot baixar de zero. Implementa `estaAcabat()`.

## Exercici 6. Llibre (JS)
Crea una classe `Llibre` amb `titol`, `autor` i `nombrePagines`. Afegeix `descripcio()` i `esLlarg()` (considera llarg un llibre de més de 300 pàgines).

## Exercici 7. Conversor de temperatures (JS)
Crea una classe `Temperatura` que emmagatzemi una temperatura en graus Celsius. Implementa mètodes per retornar Fahrenheit i Kelvin. No cal modificar la temperatura guardada.

## Exercici 8. Temporitzador de joc (JS)
Crea una classe `Temporitzador` amb els segons transcorreguts. Implementa `avancar(segons)` i `reiniciar()`. Si es passen segons negatius, rebutja l'operació.

## Exercici 9. Comanda simple (JS)
Crea una classe `LiniaComanda` amb el nom del producte, el preu unitari i la quantitat. Implementa `calcularSubtotal()`. Els preus i les quantitats han de ser positius.

## Exercici 10. Revisió de classes (JS)
Revisa les classes dels exercicis 1–9. Per a cadascuna, crea almenys tres instàncies i crida tots els seus mètodes. Comprova que les instàncies no comparteixen accidentalment els seus valors.

# Bloc 2. Encapsulació, `private` i `public`

## Exercici 11. Compte bancari (JS)
Crea `CompteBancari` amb titular i saldo. El saldo no s'ha de poder modificar directament des de fora. Implementa `ingressar(import)` i `retirar(import)`. Rebutja imports no positius i retirades superiors al saldo.

## Exercici 12. Saldo privat (TS)
Implementa en TypeScript la classe de l'exercici 11. Fes que el saldo sigui `private` i que els mètodes públics siguin tipats. Demostra amb un comentari quin accés directe hauria de produir un error de compilació.

## Exercici 13. Contrassenya d'usuari (JS)
Crea `Usuari` amb nom públic i contrasenya privada amb `#contrasenya`. Implementa `canviarContrasenya(actual, nova)` i `validarContrasenya(valor)`. No mostris mai la contrasenya en un mètode de consulta.

## Exercici 14. Inventari privat (TS)
Crea `ArticleInventari` amb codi públic i unitats privades. Afegeix mètodes per afegir i retirar unitats. No permetis que les unitats siguin negatives.

## Exercici 15. Perfil d'usuari (TS)
Crea `Perfil` amb `nom` públic i `correu` privat. El correu només es pot canviar mitjançant `actualitzarCorreu()`, que ha de comprovar que contingui `@` i un punt després de l'arrova.

## Exercici 16. Límits d'un termòstat (TS)
Crea `Termostat` amb temperatura privada. Permet establir-la només entre 5 i 35 graus. Implementa mètodes per apujar i abaixar un grau sense sortir dels límits.

## Exercici 17. Cartera digital (TS)
Crea `CarteraDigital` amb saldo privat. Implementa `afegirFons`, `pagar` i `consultarSaldo`. El pagament ha de fallar si no hi ha prou saldo. No es pot accedir directament al saldo.

## Exercici 18. Reproductor de música (JS)
Crea `Reproductor` amb estat privat `reproduint` i volum privat. Implementa `reproduir()`, `pausar()`, `pujarVolum()` i `baixarVolum()`. El volum ha d'estar entre 0 i 100.

## Exercici 19. Nombre de sèrie (TS)
Crea `Dispositiu` amb un número de sèrie privat que s'assigna al constructor i no es pot canviar. Exposa un mètode públic per consultar-lo i un altre per retornar una descripció del dispositiu.

## Exercici 20. Comparació de privacitat (JS i TS)
Implementa una classe amb un camp privat en JavaScript amb `#camp` i una altra en TypeScript amb `private camp`. Explica i comprova què passa quan s'intenta accedir al camp des de fora. Inclou el resultat esperat en un breu document.

# Bloc 3. Getters, setters i invariants

## Exercici 21. Nom complet (JS)
Crea `Persona` amb `nom` i `cognoms` privats. Afegeix getters i setters que rebutgin cadenes buides o formades només per espais. El getter `nomComplet` ha de combinar els dos camps.

## Exercici 22. Preu amb getter i setter (TS)
Crea `Producte` amb `preu` privat. El getter `preu` retorna el valor i el setter rebutja números negatius o no finits. Afegeix `preuAmbDescompte(percentatge)` sense modificar el preu base.

## Exercici 23. Edat calculada (TS)
Crea `Persona` amb any de naixement privat i un getter `edat` que calculi l'edat aproximada a partir de l'any actual rebut com a argument d'un mètode. Evita guardar una edat duplicada que es pugui desincronitzar.

## Exercici 24. Nota acadèmica (TS)
Crea `Nota` amb un valor privat. El getter retorna el valor i el setter accepta una nota numèrica dins del rang 0–10. Si el valor no és vàlid, llança un error. Prova els extrems i els valors invàlids.

## Exercici 25. Dimensions d'un paquet (TS)
Crea `Paquet` amb amplada, alçada i profunditat privades, amb getters i setters. Totes les dimensions han de ser positives. Implementa un getter `volum`.

## Exercici 26. Nom d'usuari normalitzat (JS)
Crea `CompteUsuari` amb un setter per al nom d'usuari que elimini espais als extrems i el converteixi a minúscules. Rebutja noms de menys de tres caràcters. El getter ha de retornar el valor normalitzat.

## Exercici 27. Capacitat d'un dipòsit (TS)
Crea `Diposit` amb capacitat màxima fixa i quantitat actual privada. El setter de quantitat no ha de permetre valors negatius ni superar la capacitat. Implementa `omplir()` i `buidar()`.

## Exercici 28. Línia de comanda amb quantitat (TS)
Crea `LiniaComanda` amb preu unitari i quantitat privats. La quantitat ha de ser un enter positiu. El getter `subtotal` ha de calcular el resultat, no emmagatzemar-lo.

## Exercici 29. Cistella de compra (JS)
Crea `Cistella` amb un array privat de línies de comanda. Implementa `afegirProducte`, `eliminarProducte(id)` i getters per al nombre de línies i el total. No exposis directament l'array intern.

## Exercici 30. Revisió d'invariants (TS)
Tria tres classes anteriors i identifica les condicions que sempre han de ser certes (invariants). Assegura't que tots els constructors, setters i mètodes les mantenen. Escriu proves per a cada invariant.

# Bloc 4. Mètodes d'array dins de classes

## Exercici 31. Llista de tasques (JS)
Crea una classe `GestorTasques` que guardi tasques en un array privat. Cada tasca té `id`, `descripcio` i `completada`. Implementa afegir, completar i eliminar tasques.

## Exercici 32. Filtrar tasques pendents (JS)
Amplia `GestorTasques` amb `obtenirPendents()` i `obtenirCompletades()` utilitzant `filter`. Retorna nous arrays i evita que el codi extern modifiqui l'array intern.

## Exercici 33. Cerca per identificador (JS)
Afegeix `buscarPerId(id)` amb `find`. Retorna la tasca trobada o `undefined` si no existeix. Decideix com evitar que el resultat permeti modificar accidentalment l'estat intern.

## Exercici 34. Comprovar tasques (JS)
Afegeix `totesCompletades()` amb `every` i `hiHaTasquesUrgents()` amb `some`, considerant que les tasques tenen també una propietat `prioritat`.

## Exercici 35. Resum de tasques (JS)
Afegeix mètodes que calculin el nombre de tasques totals, completades i pendents amb `filter` i `length`. Compara aquesta solució amb una altra basada en `reduce`.

## Exercici 36. Catàleg de productes (TS)
Crea `Cataleg` amb una llista privada de productes tipats (`id`, `nom`, `preu`, `categoria`, `stock`). Implementa `afegirProducte` i `eliminarProducte`.

## Exercici 37. Filtrar per preu i categoria (TS)
Afegeix a `Cataleg` mètodes per filtrar productes per preu màxim i per categoria. Combina les condicions en un únic mètode amb paràmetres opcionals tipats.

## Exercici 38. Transformar dades amb `map` (TS)
Afegeix `obtenirNoms()` i `obtenirEtiquetes()` que retornin, respectivament, els noms i cadenes del tipus `"Teclat — 29.90 €"`. Mostra sempre els preus amb dos decimals.

## Exercici 39. Estadístiques amb `reduce` (TS)
Afegeix mètodes per calcular el valor total de l'inventari (`preu * stock`), el preu mitjà i el nombre total d'unitats. Gestiona el catàleg buit sense retornar `NaN`.

## Exercici 40. Ordenar sense alterar l'original (TS)
Afegeix `ordenarPerPreu()` i `ordenarPerNom()`. Retorna una còpia ordenada; no modifiquis l'ordre intern. Per al preu, si hi ha empat, ordena pel nom alfabèticament.

# Bloc 5. Gestió de col·leccions d'objectes

## Exercici 41. Llista d'alumnes (JS)
Crea `GrupClasse` que guardi objectes `Alumne` amb identificador, nom i edat. Implementa alta, baixa i cerca per identificador, controlant els identificadors duplicats.

## Exercici 42. Filtrar alumnes (JS)
Afegeix mètodes per obtenir alumnes majors d'una edat determinada, cercar noms que comencin per una lletra i trobar un alumne pel nom. Utilitza `filter` i `find`.

## Exercici 43. Notes d'un alumne (JS)
Crea `Alumne` amb un array privat de notes. Implementa afegir nota, consultar notes, calcular mitjana amb `reduce` i comprovar si ha aprovat. Valida les notes entre 0 i 10.

## Exercici 44. Mitjanes del grup (TS)
Crea `GrupClasse` amb alumnes que tenen notes. Calcula la mitjana de cada alumne i retorna un array de resums `{ nom, mitjana }` amb `map`. Defineix tipus explícits per als resums.

## Exercici 45. Rànquing acadèmic (TS)
Ordena els alumnes per mitjana descendent i, en cas d'empat, pel nom ascendent. No modifiquis l'array original. Comprova empats i noms amb majúscules/minúscules.

## Exercici 46. Biblioteca (TS)
Crea `Biblioteca` amb llibres que tenen ISBN, títol, autor i estat de préstec. Implementa prestar, retornar i consultar disponibilitat. No permetis prestar un llibre ja prestat.

## Exercici 47. Cerca i filtratge de llibres (TS)
Afegeix cerca per títol, filtre per autor i filtre de llibres disponibles. Decideix si la cerca de text ha de distingir majúscules i minúscules i documenta el comportament.

## Exercici 48. Estadístiques de biblioteca (TS)
Calcula quants llibres hi ha en total, quants estan prestats i quin percentatge està disponible. Evita la divisió per zero quan la biblioteca és buida.

## Exercici 49. Historial de moviments (TS)
Amplia la biblioteca amb un historial de préstecs i devolucions. Cada moviment conté ISBN, data i tipus de moviment. Implementa consultes amb `filter`, `map` i `reduce`.

## Exercici 50. Catàleg de pel·lícules (JS/TS)
Crea `Videoteca` amb pel·lícules que tenen títol, director, any i valoració. Implementa filtratge per any, cerca per director, ordenació per valoració i mitjana de valoracions. Fes una versió en JS i una en TS.

# Bloc 6. Composició i relacions entre classes

## Exercici 51. Adreça i persona (JS)
Crea una classe `Adreca` i utilitza-la com a propietat d'una classe `Persona`. La persona ha de poder retornar una adreça completa. Evita repetir els camps de l'adreça dins de `Persona`.

## Exercici 52. Comanda i línies (JS)
Crea `Comanda` que contingui diverses instàncies de `LiniaComanda`. Implementa afegir línies, eliminar-les i calcular el total. El total s'ha de calcular a partir de les línies actuals.

## Exercici 53. Client i comandes (TS)
Crea `Client` amb identificador, nom i historial de comandes. Permet afegir comandes i calcular la despesa acumulada amb `reduce`. No exposis l'array intern directament.

## Exercici 54. Motor i vehicle (TS)
Crea `Motor` amb cilindrada i potència, i `Vehicle` que contingui un motor. Implementa una descripció del vehicle que utilitzi les dades del motor.

## Exercici 55. Cartera i transaccions (TS)
Crea `Transaccio` amb import, data i tipus. `CarteraDigital` ha de mantenir l'historial de transaccions i calcular el saldo a partir dels moviments. Evita que una transacció invàlida alteri el saldo.

## Exercici 56. Equip i jugadors (JS)
Crea `Jugador` i `Equip`. Un equip conté jugadors; implementa afegir, treure i cercar jugadors, impedir dorsals duplicats i obtenir la llista de noms amb `map`.

## Exercici 57. Reserva i habitació (TS)
Crea `Habitacio` i `Reserva`. Una reserva té data d'inici i data de finalització. Valida que la data final sigui posterior a la inicial i implementa una comprovació de solapament entre reserves.

## Exercici 58. Carretó i productes (TS)
Crea `CarretoCompra` que contingui referències a productes i quantitats. Implementa afegir producte, canviar quantitat, eliminar i calcular total. Valida que el stock sigui suficient.

## Exercici 59. Departament i treballadors (TS)
Crea `Treballador` i `Departament`. Calcula la despesa salarial del departament amb `reduce`, troba el salari més alt i retorna una llista ordenada per cognom i nom.

## Exercici 60. Diagrama de classes (JS/TS)
A partir de dues classes dels exercicis 51–59, dibuixa un diagrama de classes que mostri propietats, mètodes i relacions. Implementa després les classes i comprova que el codi respecta el diagrama.

# Bloc 7. Herència i polimorfisme

## Exercici 61. Persona i estudiant (JS)
Crea una classe base `Persona` i una classe `Estudiant` que n'hereti. Afegeix curs i implementa un mètode de presentació que reutilitzi el comportament de la classe base amb `super`.

## Exercici 62. Empleat i responsable (JS)
Crea `Empleat` amb nom i salari. Crea `Responsable` que hereti d'`Empleat` i afegeixi un complement salarial. Implementa el càlcul del salari total.

## Exercici 63. Formes geomètriques (TS)
Crea una classe base `Forma` i subclasses `Cercle` i `Rectangle`. Cada forma ha de calcular la seva àrea. Tipifica les propietats i sobreescriu el mètode adequadament.

## Exercici 64. Instruments musicals (TS)
Crea una classe base `Instrument` amb un mètode `tocar()`. Implementa `Guitarra`, `Piano` i `Bateria`, cadascun amb una resposta diferent. Recorre un array d'instruments i crida `tocar()` sense comprovar el tipus concret.

## Exercici 65. Mètode sobreescrit (JS)
Crea `Notificacio` i subclasses `NotificacioEmail` i `NotificacioSMS`. Totes implementen `enviar()`. Escriu una funció que accepti qualsevol notificació i l'enviï polimòrficament.

## Exercici 66. Classes abstractes (TS)
Crea una classe abstracta `Figura` amb el mètode abstracte `calcularArea()`. Implementa `Cercle`, `Rectangle` i `Triangle`. Comprova que no es pot instanciar `Figura` directament.

## Exercici 67. Mètodes protegits (TS)
Crea una classe base `Document` amb un camp `protected` per al títol i un mètode públic per generar una capçalera. Crea `Informe` que utilitzi el camp protegit. Explica per què no és accessible des de codi extern.

## Exercici 68. Pagaments polimòrfics (TS)
Defineix una classe base o una interfície `MetodePagament` amb `pagar(import)`. Implementa pagament amb targeta i amb cartera digital. Crea un servei que processi diferents mètodes de pagament sense conèixer-ne la implementació concreta.

## Exercici 69. Descompte per tipus de client (TS)
Crea `Client` i subclasses `ClientParticular` i `ClientPremium`. Implementa un mètode per calcular el descompte. Processa un array de clients amb `map` i calcula l'import final de cada compra.

## Exercici 70. Polimorfisme amb arrays (JS/TS)
Crea diverses subclasses d'una classe base `Missatge`. Emmagatzema-les en un array i utilitza `map` per obtenir el contingut i `filter` per seleccionar els missatges d'una categoria. Implementa-ho en JS i TS.

# Bloc 8. Disseny, tipus i robustesa en TypeScript

## Exercici 71. Tipus per a productes (TS)
Defineix un `type ProducteDades` per representar les dades necessàries per crear un producte. Fes que el constructor rebi aquest objecte i utilitzi desestructuració. Mantén separades les dades d'entrada i l'estat privat de la instància.

## Exercici 72. Paràmetres opcionals (TS)
Crea `CercadorProductes` amb mètodes de cerca que acceptin filtres opcionals de categoria, preu màxim i text. Aplica només els filtres indicats, sense duplicar la lògica.

## Exercici 73. Unions discriminades (TS)
Modela els pagaments com una unió discriminada: efectiu, targeta o transferència. Crea una classe `ProcessadorPagaments` que validi el tipus i calculi una descripció adequada amb una comprovació exhaustiva.

## Exercici 74. Errors tipats conceptualment (TS)
Crea una classe `Reserva` que llanci errors quan les dates siguin invàlides o quan hi hagi solapaments. Escriu proves que comprovin el missatge o el tipus d'error i explica que les excepcions no substitueixen els tipus estàtics.

## Exercici 75. Dades desconegudes (TS)
Implementa `ImportadorProductes` amb un mètode que rebi `unknown`. Valida en temps d'execució que el valor sigui un array d'objectes amb `id`, `nom` i `preu` correctes abans de crear instàncies de `Producte`. No utilitzis `as Producte[]` sense validar.

## Exercici 76. Còpia defensiva (TS)
Crea una classe amb un array privat d'elements. Implementa un getter que retorni una còpia i comprova que modificar l'array retornat no canvia l'estat intern. Si els elements són objectes, analitza si cal una còpia superficial o profunda.

## Exercici 77. Comparador reutilitzable (TS)
Crea un mètode genèric que ordeni una còpia d'un array segons una funció comparadora. Utilitza'l per ordenar productes per preu, alumnes per nota i llibres per títol. No modifiquis l'array original.

## Exercici 78. Repositori genèric (TS)
Crea una classe genèrica `Repositori<T>` amb operacions per afegir, obtenir tots els elements, cercar per predicat i eliminar elements. Evita assumir que qualsevol `T` té una propietat `id`; si necessites un identificador, defineix una restricció genèrica adequada.

## Exercici 79. Principi de responsabilitat única (TS)
Revisa una classe que gestioni productes, validació, càlculs, impressió de missatges i persistència simulada. Divideix-la en classes amb responsabilitats més clares. Documenta què fa cada classe i quines dependències té.

## Exercici 80. Refactorització (JS/TS)
Tria una classe extensa d'un exercici anterior. Separa les responsabilitats, redueix duplicacions, encapsula les dades i afegeix proves. Conserva el comportament observable i explica els canvis.

# Bloc 9. Exercicis integradors

## Exercici 81. Gestor de tasques complet (TS)
Construeix una aplicació de terminal per gestionar tasques. Cada tasca té identificador, títol, prioritat, data límit i estat. Implementa alta, modificació, eliminació, cerca, filtratge, ordenació i estadístiques. Les dades internes han d'estar encapsulades.

## Exercici 82. Botiga en línia (TS)
Implementa `Producte`, `Client`, `LiniaComanda`, `Comanda` i `Botiga`. La botiga permet cercar productes, afegir-los a una cistella, validar stock i calcular el total. Els imports s'han de mostrar sempre amb dos decimals.

## Exercici 83. Sistema de notes (TS)
Implementa `Alumne`, `Assignatura` i `GrupClasse`. Cada assignatura conté notes per alumne. Calcula mitjanes, filtra aprovats, ordena el rànquing i calcula estadístiques del grup. Valida les notes i evita divisions per zero.

## Exercici 84. Biblioteca amb usuaris (TS)
Implementa `Llibre`, `Usuari`, `Prestec` i `Biblioteca`. Gestiona préstecs i devolucions, impedeix prestar llibres no disponibles i limita el nombre de préstecs actius per usuari. Inclou un historial consultable.

## Exercici 85. Gestió de reserves (TS)
Implementa habitacions, clients i reserves. Permet cercar habitacions disponibles en un interval, crear i cancel·lar reserves i calcular el preu segons el nombre de nits. Evita solapaments i valida les dates.

## Exercici 86. Gestor de despeses (TS)
Implementa `Despesa`, `Categoria` i `Pressupost`. Permet registrar despeses, filtrar per categoria i període, agrupar per categoria amb `reduce` i comparar la despesa amb el pressupost. Mostra imports amb dos decimals.

## Exercici 87. Inventari d'un magatzem (TS)
Implementa productes, moviments d'estoc i magatzem. Gestiona entrades i sortides, impedeix stock negatiu i calcula el valor de l'inventari. Afegeix cerques, filtres i ordenació amb mètodes d'array.

## Exercici 88. Gestor de cursos (TS)
Implementa `Curs`, `Alumne` i `Matricula`. Un alumne pot matricular-se en diversos cursos i un curs pot tenir diversos alumnes, amb límit de places. Calcula ocupació, llista d'espera i cursos disponibles.

## Exercici 89. Sistema de notificacions (TS)
Implementa notificacions per correu, SMS i notificació interna amb una abstracció comuna. Afegeix una cua de notificacions, filtres per estat i recompte de notificacions enviades o fallides. Simula l'enviament sense serveis externs.

## Exercici 90. Mini API en memòria (TS)
Crea una classe `ServeiUsuaris` que simuli una API amb dades en memòria. Implementa crear, consultar, actualitzar i eliminar usuaris. Valida les dades d'entrada, tipa els resultats i no retornis referències modificables a l'estat intern.

# Bloc 10. Reptes de disseny i ampliació

## Exercici 91. Refactoritzar dades planes a POO (JS)
Parteix d'un array d'objectes de comandes i diverses funcions independents. Dissenya classes que representin el domini, decideix quines operacions pertanyen a cada classe i compara la versió original amb la refactoritzada.

## Exercici 92. Herència o composició? (TS)
Dissenya un sistema de vehicles amb motor, conductor i funcions especials. Proposa dues solucions, una amb herència i una amb composició. Implementa la que consideris més adequada i justifica la decisió.

## Exercici 93. No exposar l'estat intern (TS)
Crea una classe que gestioni un array d'objectes. Demostra com un getter que retorna l'array original permet modificar l'estat des de fora. Corregeix-ho amb còpies defensives i proves.

## Exercici 94. Ordenació amb diversos criteris (TS)
Crea una classe que gestioni resultats d'un torneig. Ordena per puntuació descendent, després per nombre de victòries descendent i finalment pel nom ascendent. No modifiquis l'ordre intern i prova empats múltiples.

## Exercici 95. Agrupació d'objectes (TS)
Crea una classe `RegistreVendes` amb vendes de productes. Implementa un mètode que agrupi les vendes per categoria i retorni, per categoria, el total venut i el nombre de vendes. Utilitza `reduce` i defineix els tipus del resultat.

## Exercici 96. Generar informes (TS)
A partir d'un catàleg de productes, genera un informe amb `map`, `filter`, `sort` i `reduce`: productes amb stock baix, valor total per categoria i top cinc productes més cars. Els informes no han d'alterar les dades originals.

## Exercici 97. Validació de dades importades (TS)
Rep dades simulades d'una API com a `unknown`. Valida camps obligatoris, tipus, valors numèrics i identificadors duplicats. Converteix les dades validades en instàncies de classe. Defineix què passa quan una part del conjunt és invàlida.

## Exercici 98. Proves de regressió (JS/TS)
Selecciona un dels projectes integradors. Escriu proves unitàries per a constructors, getters/setters, mètodes de canvi d'estat, validacions, errors i operacions amb arrays. Afegeix casos límit i proves que comprovin que una operació fallida no modifica l'estat.

## Exercici 99. Revisió de disseny (TS)
Revisa un projecte integrador i identifica: dades públiques que haurien de ser privades, getters/setters innecessaris, mètodes massa extensos, duplicacions, classes amb massa responsabilitats i ús incorrecte d'herència. Refactoritza almenys tres problemes.

## Exercici 100. Projecte final: sistema de gestió (JS i TS)
Dissenya una aplicació de terminal amb vite+vitest+typescruipt per a un domini que triïs (biblioteca, botiga, acadèmia, reserves, inventari, gestió de tasques o bé el que creguis addients).

Requisits mínims:
- Com a mínim tres classes amb responsabilitats diferenciades.
- Constructors amb validació de dades.
- Encapsulació amb camps privats i mètodes públics.
- Getters/setters només quan tinguin sentit i mantinguin invariants.
- Composició entre classes i, si és adequada, herència o polimorfisme.
- Arrays d'instàncies i ús justificat de `map`, `filter`, `find`, `some`, `every`, `reduce` i `sort`.
- Cerca, filtratge, ordenació i estadístiques.
- Gestió d'errors amb excepcions quan les operacions no siguin vàlides.
- JSDoc en català i noms coherents.
- Proves amb Vitest, incloent-hi casos límit i errors.
- Una versió JavaScript i una versió TypeScript, o una justificació de quines parts canvien en la migració.
- Un breu document (detall.md) amd decisions de disseny, instruccions d'execució, decisions preseses, perquè heu escollit el domini i diagrama de classes.

