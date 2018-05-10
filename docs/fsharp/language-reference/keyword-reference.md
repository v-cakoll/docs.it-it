---
title: Riferimento per parole chiave (F#)
description: 'Trovare collegamenti a informazioni su tutte le parole chiave del linguaggio F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 7d8a2bf667f5303cc19e8d4279e433efca25c294
ms.sourcegitcommit: c03eef711abe961a85db2b4d0715257d1524aef6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2018
---
# <a name="keyword-reference"></a>Riferimento per parole chiave

In questo argomento contiene collegamenti a informazioni su tutte le parole chiave del linguaggio F #.

## <a name="f-keyword-table"></a>Tabella delle parole chiave F #

Nella tabella seguente mostra tutte le parole chiave F # in ordine alfabetico, insieme a brevi descrizioni e collegamenti ai relativi argomenti contenenti ulteriori informazioni.

|Parola chiave|Collegamento|Descrizione|
|-------|----|-----------|
|`abstract`|[Membri](members/index.md)<br /><br />[Classi astratte](abstract-classes.md)|Indica un metodo che non dispone di implementazione del tipo in cui viene dichiarato o che è virtuale e si dispone di un'implementazione predefinita.|
|`and`|[`let` Associazioni](functions/let-bindings.md)<br /><br />[Membri](members/index.md)<br /><br />[Vincoli](generics/constraints.md)|Usato nelle associazioni ricorsive reciproche, nelle dichiarazioni di proprietà e con più vincoli sui parametri generici.|
|`as`|[Classi](classes.md)<br /><br />[Criteri di ricerca](Pattern-Matching.md)|Utilizzato per assegnare un nome di oggetto di oggetto della classe corrente. Viene utilizzato anche per assegnare un nome a un intero modello all'interno di un criterio di ricerca.|
|`assert`|[Asserzioni](assertions.md)|Utilizzato per verificare il codice durante il debug.|
|`base`|[Classi](classes.md)<br /><br />[Ereditarietà](inheritance.md)|Utilizzato come nome dell'oggetto della classe base.|
|`begin`|[Sintassi dettagliata](verbose-syntax.md)|Nella sintassi dettagliata indica l'inizio di un blocco di codice.|
|`class`|[Classi](classes.md)|Nella sintassi dettagliata indica l'inizio di una definizione di classe.|
|`default`|[Membri](members/index.md)|Indica un'implementazione di un metodo astratto. utilizzato insieme a una dichiarazione di metodo astratto per creare un metodo virtuale.|
|`delegate`|[Delegati](delegates.md)|Usato per dichiarare un delegato.|
|`do`|[Associazioni do](functions/do-bindings.md)<br /><br />[Cicli: espressione `for...to`](loops-for-to-expression.md)<br /><br />[Cicli: espressione `for...in`](loops-for-in-expression.md)<br /><br />[Cicli: espressione `while...do`](loops-while-do-expression.md)|Utilizzato in costrutti di ciclo per eseguire codice imperativo.|
|`done`|[Sintassi dettagliata](verbose-syntax.md)|Nella sintassi dettagliata indica la fine di un blocco di codice in un'espressione di ciclo.|
|`downcast`|[Cast e conversioni](casting-and-conversions.md)|Consente di convertire in un tipo di livello inferiore nella catena di ereditarietà.|
|`downto`|[Cicli: espressione `for...to`](loops-for-to-expression.md)|In un `for` espressione, utilizzata quando il conteggio in ordine inverso.|
|`elif`|[Espressioni condizionali: `if...then...else`](conditional-expressions-if-then-else.md)|Utilizzata nella creazione di rami condizionali. Forma abbreviata del `else if`.|
|`else`|[Espressioni condizionali: `if...then...else`](conditional-expressions-if-then-else.md)|Utilizzata nella creazione di rami condizionali.|
|`end`|[Strutture](structures.md)<br /><br />[Unioni discriminate](discriminated-unions.md)<br /><br />[Record](records.md)<br /><br />[Estensioni di tipo](type-extensions.md)<br /><br />[Sintassi dettagliata](verbose-syntax.md)|Nelle definizioni di tipi ed estensioni di tipo, indica la fine di una sezione di definizioni di membro.<br /><br />Nella sintassi dettagliata viene utilizzata per specificare la fine di un blocco di codice che inizia con il `begin` (parola chiave).|
|`exception`|[Gestione delle eccezioni](exception-handling/index.md)<br /><br />[Tipi di eccezione](exception-handling/exception-types.md)|Usato per dichiarare un tipo di eccezione.|
|`extern`|[Funzioni esterne](functions/external-functions.md)|Indica che un elemento del programma dichiarato è definito in un altro file binario o assembly.|
|`false`|[Tipi primitivi](primitive-types.md)|Utilizzato come valori letterali booleani.|
|`finally`|[Eccezioni: espressione `try...finally`](exception-handling/the-try-finally-expression.md)|Utilizzata in combinazione con `try` per introdurre un blocco di codice che viene eseguita indipendentemente dal fatto che si verifica un'eccezione.|
|`fixed`|[predefinito](fixed.md)|Consentono di "aggiungere" puntatore dello stack per impedire che venga raccolto nel garbage collector.|
|`for`|[Cicli: espressione `for...to`](loops-for-to-expression.md)<br /><br />[Espressione Loops: for...in](loops-for-in-expression.md)|Utilizzato in costrutti di ciclo.|
|`fun`|[Espressioni lambda: I `fun` (parola chiave)](functions/lambda-expressions-the-fun-keyword.md)|Usato nelle espressioni lambda, anche note come funzioni anonime.|
|`function`|[Espressioni match](match-expressions.md)<br /><br />[Espressioni lambda: Parola chiave fun](functions/lambda-expressions-the-fun-keyword.md)|Utilizzato come alternativa alla più breve il `fun` (parola chiave) e un `match` espressione in un'espressione lambda con i criteri di ricerca in un singolo argomento.|
|`global`|[Spazi dei nomi](namespaces.md)|Utilizzato per fare riferimento il primo livello dello spazio dei nomi .NET.|
|`if`|[Espressioni condizionali: `if...then...else`](conditional-expressions-if-then-else.md)|Utilizzato in costrutti di creazione di rami condizionali.|
|`in`|[Espressione Loops: for...in](loops-for-in-expression.md)<br /><br />[Sintassi dettagliata](verbose-syntax.md)|Utilizzato per le espressioni di sequenza e, nella sintassi dettagliata per separare le espressioni dalle associazioni.|
|`inherit`|[Ereditarietà](inheritance.md)|Utilizzato per specificare una classe base o l'interfaccia di base.|
|`inline`|[Funzioni](functions/index.md)<br /><br />[Funzioni inline](functions/inline-functions.md)|Utilizzato per indicare una funzione che deve essere integrata direttamente nel codice del chiamante.|
|`interface`|[Interfacce](interfaces.md)|Utilizzato per dichiarare e implementare interfacce.|
|`internal`|[Controllo di accesso](access-control.md)|Utilizzato per specificare che un membro è visibile all'interno di un assembly, ma non al suo esterno.|
|`lazy`|[Calcoli differiti](lazy-computations.md)|Consente di specificare un calcolo che deve essere eseguita solo se è necessario un risultato.|
|`let`|[`let` Associazioni](functions/let-bindings.md)|Utilizzato per associare o un nome a un valore o funzione.|
|`let!`|[Flussi di lavoro asincroni](asynchronous-workflows.md)<br /><br />[Espressioni di calcolo](computation-expressions.md)|Utilizzata nei flussi di lavoro asincroni per associare un nome al risultato di un calcolo asincrono o, in altre espressioni di calcolo, utilizzati per associare un nome a un risultato, che è del tipo di calcolo.|
|`match`|[Espressioni match](match-expressions.md)|Utilizzato per ramo confrontando un valore a un modello.|
|`member`|[Membri](members/index.md)|Usato per dichiarare una proprietà o metodo in un tipo di oggetto.|
|`module`|[Moduli](modules.md)|Utilizzato per associare un nome a un gruppo di tipi correlati, valori e le funzioni, per separare logicamente da altro codice.|
|`mutable`|[Associazioni let](functions/let-bindings.md)|Usato per dichiarare una variabile, vale a dire un valore che può essere modificato.|
|`namespace`|[Spazi dei nomi](namespaces.md)|Utilizzato per associare un nome a un gruppo di tipi correlati e i moduli, per separare logicamente da altro codice.|
|`new`|[Costruttori](members/constructors.md)<br /><br />[Vincoli](generics/constraints.md)|Utilizzato per dichiarare, definire o richiamare un costruttore che crea o che consente di creare un oggetto.<br /><br />Nonché i vincoli del parametro generico per indicare che un tipo deve avere un costruttore di determinati.|
|`not`|[Riferimenti per simboli e operatori](symbol-and-operator-reference/index.md)<br /><br />[Vincoli](generics/constraints.md)|Non è effettivamente una parola chiave. Tuttavia, `not struct` in combinazione, viene utilizzato come vincolo di parametro generico.|
|`null`|[Valori Null](values/null-values.md)<br /><br />[Vincoli](generics/constraints.md)|Indica l'assenza di un oggetto.<br /><br />Inoltre utilizzate nei vincoli di parametro generico.|
|`of`|[Unioni discriminate](discriminated-unions.md)<br /><br />[Delegati](delegates.md)<br /><br />[Tipi di eccezione](exception-handling/exception-types.md)|Usato nelle unioni discriminate per indicare il tipo di categorie di valori e nelle dichiarazioni di delegato e l'eccezione.|
|`open`|[Dichiarazioni di importazione: parola chiave `open`](import-declarations-the-open-keyword.md)|Utilizzato per rendere il contenuto di un modulo o spazio dei nomi disponibili senza qualifica.|
|`or`|[Riferimenti per simboli e operatori](symbol-and-operator-reference/index.md)<br /><br />[Vincoli](generics/constraints.md)|Utilizzato con le condizioni booleane come valore Boolean `or` operatore. Equivale a '||`.<br /><br />Viene utilizzato anche nei vincoli di membro.|
|`override`|[Membri](members/index.md)|Utilizzato per implementare una versione di un metodo astratto o virtuale che è diverso dalla versione di base.|
|`private`|[Controllo di accesso](access-control.md)|Limita l'accesso a un membro al codice nello stesso tipo o modulo.|
|`public`|[Controllo di accesso](access-control.md)|Consente l'accesso a un membro dall'esterno del tipo.|
|`rec`|[Funzioni](functions/index.md)|Utilizzato per indicare che una funzione è ricorsiva.|
|`return`|[Flussi di lavoro asincroni](Asynchronous-Workflows.md)<br /><br />[Espressioni di calcolo](computation-expressions.md)|Utilizzato per indicare un valore da fornire come risultato di un'espressione di calcolo.|
|`return!`|[Espressioni di calcolo](computation-expressions.md)<br /><br />[Flussi di lavoro asincroni](asynchronous-workflows.md)|Utilizzato per indicare un'espressione di calcolo che, quando valutata, fornisce il risultato dell'espressione di calcolo che lo contiene.|
|`select`|[Espressioni di query](query-expressions.md)|Utilizzato nelle espressioni di query per specificare quali campi o le colonne da estrarre. Si tratta di una parola chiave contestuale, che significa che non è in realtà una parola riservata e agisce come una parola chiave nel contesto appropriato.|
|`static`|[Membri](members/index.md)|Utilizzato per indicare un metodo o proprietà che può essere chiamato senza un'istanza di un tipo o membro condiviso tra tutte le istanze di un tipo di valore.|
|`struct`|[Strutture](structures.md)<br /><br />[Vincoli](generics/constraints.md)|Usato per dichiarare un tipo di struttura.<br /><br />Inoltre utilizzate nei vincoli di parametro generico.<br /><br />Utilizzato per la compatibilità con OCaml nelle definizioni dei moduli.|
|`then`|[Espressioni condizionali: `if...then...else`](conditional-expressions-if-then-else.md)<br /><br />[Costruttori](members/constructors.md)|Utilizzata nelle espressioni condizionali.<br /><br />Questo campo viene usato anche per eseguire gli effetti collaterali dopo la costruzione di oggetti.|
|`to`|[Cicli: espressione `for...to`](loops-for-to-expression.md)|Utilizzato `for` cicli per indicare un intervallo.|
|`true`|[Tipi primitivi](primitive-types.md)|Utilizzato come valori letterali booleani.|
|`try`|[Eccezioni: Try... with espressione](exception-handling/the-try-with-expression.md)<br /><br />[Eccezioni: Try... finally espressione](exception-handling/the-try-finally-expression.md)|Utilizzato per introdurre un blocco di codice che potrebbe generare un'eccezione. Utilizzata in combinazione con `with` o `finally`.|
|`type`|[Tipi F#](fsharp-types.md)<br /><br />[Classi](classes.md)<br /><br />[Record](records.md)<br /><br />[Strutture](structures.md)<br /><br />[Enumerazioni](enumerations.md)<br /><br />[Unioni discriminate](discriminated-unions.md)<br /><br />[Abbreviazioni dei tipi](type-abbreviations.md)<br /><br />[Unità di misura](units-of-measure.md)|Utilizzato per dichiarare una classe, record, struttura, unione discriminata, tipo di enumerazione, unità di misura o l'abbreviazione di tipo.|
|`upcast`|[Cast e conversioni](casting-and-conversions.md)|Consente di convertire in un tipo di livello superiore nella catena di ereditarietà.|
|`use`|[Gestione delle risorse: parola chiave `use` ](resource-management-the-use-keyword.md)|Utilizzare invece di `let` per i valori che richiedono `Dispose` da chiamare per liberare risorse.|
|`use!`|[Espressioni di calcolo](computation-expressions.md)<br /><br />[Flussi di lavoro asincroni](asynchronous-workflows.md)|Utilizzare invece di `let!` in flussi di lavoro asincroni e altre espressioni di calcolo per i valori che richiedono `Dispose` da chiamare per liberare risorse.|
|`val`|[Campi espliciti: parola chiave `val`](members/explicit-fields-the-val-keyword.md)<br /><br />[Firme](signatures.md)<br /><br />[Membri](members/index.md)|Utilizzato in una firma per indicare un valore o in un tipo per dichiarare un membro, in situazioni limitate.|
|`void`|[Tipi primitivi](primitive-types.md)|Indica il .NET `void` tipo. Utilizzato quando si interagisce con altri linguaggi .NET.|
|`when`|[Vincoli](generics/constraints.md)|Utilizzato per le condizioni booleane (*quando Guard*) alle corrispondenze e introdurre una clausola di vincolo per un parametro di tipo generico.|
|`while`|[Cicli: espressione `while...do`](loops-while-do-expression.md)|Introduce un costrutto di ciclo.|
|`with`|[Espressioni match](match-expressions.md)<br /><br />[Espressioni di oggetto](object-expressions.md)<br /><br />[Copiare e aggiornare espressioni di record](copy-and-update-record-expressions.md)<br /><br />[Estensioni di tipo](type-extensions.md)<br /><br />[Eccezioni: espressione `try...with`](exception-handling/the-try-with-expression.md)|Utilizzata in combinazione con il `match` (parola chiave) nelle espressioni dei criteri. Utilizzato anche in espressioni di oggetto, registrare la copia di espressioni e le estensioni per introdurre le definizioni dei membri, nonché di introdurre i gestori di eccezioni di tipo.|
|`yield`|[Sequenze](sequences.md)|Utilizzato in un'espressione di sequenza per produrre un valore per una sequenza.|
|`yield!`|[Espressioni di calcolo](computation-expressions.md)<br /><br />[Flussi di lavoro asincroni](asynchronous-workflows.md)|Utilizzato in un'espressione di calcolo per aggiungere una raccolta di risultati per l'espressione di calcolo che contiene il risultato di un'espressione di calcolo specificato.|

I token seguenti sono riservati in F # perché sono parole chiave del linguaggio OCaml:

* `asr`
* `land`
* `lor`
* `lsl`
* `lsr`
* `lxor`
* `mod`
* `sig`

Se si utilizza il `--mlcompatibility` l'opzione del compilatore, le parole chiave precedente possono essere utilizzati come identificatori.

I token seguenti sono riservati come parole chiave per l'espansione futura del linguaggio F #:

* `atomic`
* `break`
* `checked`
* `component`
* `const`
* `constraint`
* `constructor`
* `continue`
* `eager`
* `event`
* `external`
* `functor`
* `include`
* `method`
* `mixin`
* `object`
* `parallel`
* `process`
* `protected`
* `pure`
* `sealed`
* `tailcall`
* `trait`
* `virtual`
* `volatile`

## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

[Riferimenti per simboli e operatori](symbol-and-operator-reference/index.md)

[Opzioni del compilatore](compiler-options.md)
