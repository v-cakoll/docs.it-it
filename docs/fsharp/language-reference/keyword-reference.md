---
title: Riferimento per parole chiave
description: Trovare collegamenti a informazioni su tutte le F# parole chiave del linguaggio.
ms.date: 05/16/2016
ms.openlocfilehash: 680b270a99eff7aa98652579d2fd31b4b05080ca
ms.sourcegitcommit: 8c6426a3d2adff5fbcbe1fed0f28eda718c15351
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "68733487"
---
# <a name="keyword-reference"></a>Riferimento per parole chiave

Questo argomento contiene collegamenti a informazioni su tutte F# le parole chiave del linguaggio.

## <a name="f-keyword-table"></a>F#Tabella parole chiave

Nella tabella seguente vengono illustrate tutte le F# parole chiave in ordine alfabetico, insieme a brevi descrizioni e collegamenti ad argomenti rilevanti che contengono ulteriori informazioni.

|Parola chiave|Collegamento|Descrizione|
|-------|----|-----------|
|`abstract`|[Membri](./members/index.md)<br /><br />[Classi astratte](abstract-classes.md)|Indica un metodo che non ha alcuna implementazione nel tipo in cui è dichiarato o che è virtuale e ha un'implementazione predefinita.|
|`and`|[`let`Associazioni](./functions/let-bindings.md)<br /><br />[Record](records.md)<br /><br />[Membri](./members/index.md)<br /><br />[Vincoli](./generics/constraints.md)|Utilizzato in binding e record ricorsivi reciprocamente, nelle dichiarazioni di proprietà e con più vincoli sui parametri generici.|
|`as`|[Classi](classes.md)<br /><br />[Criteri di ricerca](Pattern-Matching.md)|Utilizzato per assegnare all'oggetto classe corrente un nome di oggetto. Utilizzato anche per assegnare un nome a un intero modello all'interno di una corrispondenza di criteri.|
|`assert`|[Asserzioni](assertions.md)|Utilizzato per verificare il codice durante il debug.|
|`base`|[Classi](classes.md)<br /><br />[Ereditarietà](inheritance.md)|Utilizzato come nome dell'oggetto della classe di base.|
|`begin`|[Sintassi dettagliata](verbose-syntax.md)|Nella sintassi dettagliata indica l'inizio di un blocco di codice.|
|`class`|[Classi](classes.md)|Nella sintassi dettagliata indica l'inizio di una definizione di classe.|
|`default`|[Membri](./members/index.md)|Indica un'implementazione di un metodo astratto; utilizzato insieme a una dichiarazione di metodo astratto per creare un metodo virtuale.|
|`delegate`|[Delegati](delegates.md)|Utilizzato per dichiarare un delegato.|
|`do`|[Associazioni do](./functions/do-bindings.md)<br /><br />[Cicli `for...to`Espressione](loops-for-to-expression.md)<br /><br />[Cicli `for...in`Espressione](loops-for-in-expression.md)<br /><br />[Cicli `while...do`Espressione](loops-while-do-expression.md)|Utilizzato nei costrutti di ciclo o per eseguire codice imperativo.|
|`done`|[Sintassi dettagliata](verbose-syntax.md)|Nella sintassi Verbose, indica la fine di un blocco di codice in un'espressione di ciclo.|
|`downcast`|[Cast e conversioni](casting-and-conversions.md)|Utilizzato per eseguire la conversione in un tipo più basso nella catena di ereditarietà.|
|`downto`|[Cicli `for...to`Espressione](loops-for-to-expression.md)|In un' `for` espressione, utilizzata per il conteggio in ordine inverso.|
|`elif`|[Espressioni condizionali: `if...then...else`](conditional-expressions-if-then-else.md)|Utilizzato nella diramazione condizionale. Forma abbreviata `else if`di.|
|`else`|[Espressioni condizionali: `if...then...else`](conditional-expressions-if-then-else.md)|Utilizzato nella diramazione condizionale.|
|`end`|[Strutture](structures.md)<br /><br />[Unioni discriminate](discriminated-unions.md)<br /><br />[Record](records.md)<br /><br />[Estensioni di tipo](type-extensions.md)<br /><br />[Sintassi dettagliata](verbose-syntax.md)|Nelle definizioni di tipo e nelle estensioni di tipo, indica la fine di una sezione di definizioni dei membri.<br /><br />Nella sintassi Verbose, usata per specificare la fine di un blocco di codice che inizia con `begin` la parola chiave.|
|`exception`|[Gestione delle eccezioni](./exception-handling/index.md)<br /><br />[Tipi di eccezione](./exception-handling/exception-types.md)|Utilizzato per dichiarare un tipo di eccezione.|
|`extern`|[Funzioni esterne](./functions/external-functions.md)|Indica che un elemento del programma dichiarato è definito in un altro assembly o binario.|
|`false`|[Tipi primitivi](primitive-types.md)|Utilizzato come valore letterale booleano.|
|`finally`|[Eccezioni: `try...finally` Espressione](./exception-handling/the-try-finally-expression.md)|Utilizzato insieme `try` a per introdurre un blocco di codice che viene eseguito indipendentemente dal fatto che si verifichi un'eccezione.|
|`fixed`|[Fissa](fixed.md)|Utilizzato per "aggiungere" un puntatore sullo stack per impedire che venga sottoposta a Garbage Collection.|
|`for`|[Cicli `for...to`Espressione](loops-for-to-expression.md)<br /><br />[Espressione Loops: for...in](loops-for-in-expression.md)|Utilizzato nei costrutti di ciclo.|
|`fun`|[Espressioni lambda: Parola chiave `fun`](./functions/lambda-expressions-the-fun-keyword.md)|Usato nelle espressioni lambda, note anche come funzioni anonime.|
|`function`|[Espressioni match](match-expressions.md)<br /><br />[Espressioni lambda: Parola chiave fun](./functions/lambda-expressions-the-fun-keyword.md)|Usato come alternativa più breve alla `fun` parola chiave e un' `match` espressione in un'espressione lambda con criteri di ricerca in un singolo argomento.|
|`global`|[Spazi dei nomi](namespaces.md)|Usato per fare riferimento allo spazio dei nomi .NET di primo livello.|
|`if`|[Espressioni condizionali: `if...then...else`](conditional-expressions-if-then-else.md)|Utilizzato nei costrutti di diramazione condizionale.|
|`in`|[Espressione Loops: for...in](loops-for-in-expression.md)<br /><br />[Sintassi dettagliata](verbose-syntax.md)|Utilizzato per le espressioni di sequenza e, in sintassi dettagliata, per separare le espressioni dalle associazioni.|
|`inherit`|[Ereditarietà](inheritance.md)|Utilizzato per specificare una classe base o un'interfaccia di base.|
|`inline`|[Funzioni](./functions/index.md)<br /><br />[Funzioni inline](./functions/inline-functions.md)|Utilizzato per indicare una funzione che deve essere integrata direttamente nel codice del chiamante.|
|`interface`|[Interfacce](interfaces.md)|Utilizzato per dichiarare e implementare le interfacce.|
|`internal`|[Controllo di accesso](access-control.md)|Utilizzato per specificare che un membro è visibile all'interno di un assembly ma non al suo esterno.|
|`lazy`|[Espressioni lazy](lazy-expressions.md)|Utilizzato per specificare un'espressione da eseguire solo quando è necessario un risultato.|
|`let`|[`let`Associazioni](./functions/let-bindings.md)|Utilizzato per associare o associare un nome a un valore o a una funzione.|
|`let!`|[Flussi di lavoro asincroni](asynchronous-workflows.md)<br /><br />[Espressioni di calcolo](computation-expressions.md)|Utilizzato nei flussi di lavoro asincroni per associare un nome al risultato di un calcolo asincrono, oppure, in altre espressioni di calcolo, utilizzato per associare un nome a un risultato, che è del tipo di calcolo.|
|`match`|[Espressioni match](match-expressions.md)|Utilizzato per creare un ramo confrontando un valore con un modello.|
|`match!`|[Espressioni di calcolo](computation-expressions.md#match)|Utilizzato per inline una chiamata a un'espressione di calcolo e a un criterio di ricerca per il risultato.|
|`member`|[Membri](./members/index.md)|Utilizzato per dichiarare una proprietà o un metodo in un tipo di oggetto.|
|`module`|[Moduli](modules.md)|Utilizzato per associare un nome a un gruppo di tipi, valori e funzioni correlati, per separare logicamente tale nome da altro codice.|
|`mutable`|[Associazioni let](./functions/let-bindings.md)|Utilizzato per dichiarare una variabile, ovvero un valore che può essere modificato.|
|`namespace`|[Spazi dei nomi](namespaces.md)|Utilizzato per associare un nome a un gruppo di tipi e moduli correlati, per separarlo logicamente da altro codice.|
|`new`|[Costruttori](./members/constructors.md)<br /><br />[Vincoli](./generics/constraints.md)|Utilizzato per dichiarare, definire o richiamare un costruttore che crea o in grado di creare un oggetto.<br /><br />Utilizzato anche nei vincoli di parametro generico per indicare che un tipo deve avere un determinato costruttore.|
|`not`|[Riferimenti per simboli e operatori](./symbol-and-operator-reference/index.md)<br /><br />[Vincoli](./generics/constraints.md)|In realtà non è una parola chiave. Tuttavia, `not struct` in combinazione viene usato come vincolo di parametro generico.|
|`null`|[Valori Null](./values/null-values.md)<br /><br />[Vincoli](./generics/constraints.md)|Indica l'assenza di un oggetto.<br /><br />Utilizzato anche nei vincoli di parametro generici.|
|`of`|[Unioni discriminate](discriminated-unions.md)<br /><br />[Delegati](delegates.md)<br /><br />[Tipi di eccezione](./exception-handling/exception-types.md)|Utilizzato nelle unioni discriminate per indicare il tipo di categorie di valori e nelle dichiarazioni di delegato e di eccezione.|
|`open`|[Dichiarazioni di importazione: Parola chiave `open`](import-declarations-the-open-keyword.md)|Utilizzato per rendere disponibile il contenuto di uno spazio dei nomi o di un modulo senza qualifica.|
|`or`|[Riferimenti per simboli e operatori](./symbol-and-operator-reference/index.md)<br /><br />[Vincoli](./generics/constraints.md)|Utilizzato con condizioni booleane come operatore booleano `or` . Equivalente a `||`.<br /><br />Utilizzato anche nei vincoli del membro.|
|`override`|[Membri](./members/index.md)|Utilizzato per implementare una versione di un metodo astratto o virtuale che differisce dalla versione di base.|
|`private`|[Controllo di accesso](access-control.md)|Limita l'accesso a un membro al codice nello stesso tipo o modulo.|
|`public`|[Controllo di accesso](access-control.md)|Consente l'accesso a un membro dall'esterno del tipo.|
|`rec`|[Funzioni](./functions/index.md)|Utilizzato per indicare che una funzione è ricorsiva.|
|`return`|[Flussi di lavoro asincroni](Asynchronous-Workflows.md)<br /><br />[Espressioni di calcolo](computation-expressions.md)|Utilizzato per indicare un valore da fornire come risultato di un'espressione di calcolo.|
|`return!`|[Espressioni di calcolo](computation-expressions.md)<br /><br />[Flussi di lavoro asincroni](asynchronous-workflows.md)|Utilizzato per indicare un'espressione di calcolo che, quando valutata, fornisce il risultato dell'espressione di calcolo contenitore.|
|`select`|[Espressioni di query](query-expressions.md)|Utilizzato nelle espressioni di query per specificare i campi o le colonne da estrarre. Si noti che si tratta di una parola chiave contestuale, che significa che non si tratta in realtà di una parola riservata e che agisce solo come una parola chiave nel contesto appropriato.|
|`static`|[Membri](./members/index.md)|Utilizzato per indicare un metodo o una proprietà che può essere chiamata senza un'istanza di un tipo o un membro del valore condiviso tra tutte le istanze di un tipo.|
|`struct`|[Strutture](structures.md)<br /><br /> [Tuple](tuples.md)<br/><br/>[Vincoli](./generics/constraints.md)|Utilizzato per dichiarare un tipo di struttura.<br /><br/>Utilizzato per specificare una tupla struct.<br/><br />Utilizzato anche nei vincoli di parametro generici.<br /><br />Usato per la compatibilità con OCaml nelle definizioni dei moduli.|
|`then`|[Espressioni condizionali: `if...then...else`](conditional-expressions-if-then-else.md)<br /><br />[Costruttori](./members/constructors.md)|Utilizzato nelle espressioni condizionali.<br /><br />Utilizzato anche per eseguire effetti collaterali dopo la costruzione di oggetti.|
|`to`|[Cicli `for...to`Espressione](loops-for-to-expression.md)|Utilizzato nei `for` cicli per indicare un intervallo.|
|`true`|[Tipi primitivi](primitive-types.md)|Utilizzato come valore letterale booleano.|
|`try`|[Eccezioni: Prova... Espressione with](./exception-handling/the-try-with-expression.md)<br /><br />[Eccezioni: Prova... Espressione finally](./exception-handling/the-try-finally-expression.md)|Utilizzato per introdurre un blocco di codice che potrebbe generare un'eccezione. Utilizzato insieme a `with` o `finally`.|
|`type`|[Tipi F#](fsharp-types.md)<br /><br />[Classi](classes.md)<br /><br />[Record](records.md)<br /><br />[Strutture](structures.md)<br /><br />[Enumerazioni](enumerations.md)<br /><br />[Unioni discriminate](discriminated-unions.md)<br /><br />[Abbreviazioni dei tipi](type-abbreviations.md)<br /><br />[Unità di misura](units-of-measure.md)|Utilizzato per dichiarare una classe, un record, una struttura, un'unione discriminata, un tipo di enumerazione, un'unità di misura o un'abbreviazione di tipo.|
|`upcast`|[Cast e conversioni](casting-and-conversions.md)|Utilizzato per eseguire la conversione in un tipo di livello superiore nella catena di ereditarietà.|
|`use`|[Gestione delle risorse: Parola chiave `use`](resource-management-the-use-keyword.md)|Usato al posto `let` di per i valori `Dispose` che richiedono la chiamata a risorse gratuite.|
|`use!`|[Espressioni di calcolo](computation-expressions.md)<br /><br />[Flussi di lavoro asincroni](asynchronous-workflows.md)|Utilizzato anziché in `let!` flussi di lavoro asincroni e altre espressioni di calcolo per i valori `Dispose` che richiedono la chiamata a risorse gratuite.|
|`val`|[Campi espliciti: Parola chiave `val`](./members/explicit-fields-the-val-keyword.md)<br /><br />[Firme](signatures.md)<br /><br />[Membri](./members/index.md)|Utilizzato in una firma per indicare un valore o in un tipo per dichiarare un membro, in situazioni limitate.|
|`void`|[Tipi primitivi](primitive-types.md)|Indica il tipo `void` .NET. Utilizzato per l'interoperabilità con altri linguaggi .NET.|
|`when`|[Vincoli](./generics/constraints.md)|Usato per le condizioni booleane (*When guardes*) sulle corrispondenze del criterio e per introdurre una clausola di vincolo per un parametro di tipo generico.|
|`while`|[Cicli `while...do`Espressione](loops-while-do-expression.md)|Introduce un costrutto di ciclo.|
|`with`|[Espressioni match](match-expressions.md)<br /><br />[Espressioni di oggetto](object-expressions.md)<br /><br />[Copiare e aggiornare espressioni di record](copy-and-update-record-expressions.md)<br /><br />[Estensioni di tipo](type-extensions.md)<br /><br />[Eccezioni: `try...with` Espressione](./exception-handling/the-try-with-expression.md)|Utilizzato insieme `match` alla parola chiave nelle espressioni di criteri di ricerca. Utilizzato anche nelle espressioni di oggetto, nella copia di record e nelle estensioni di tipo per introdurre le definizioni dei membri e per introdurre gestori di eccezioni.|
|`yield`|[Sequenze](sequences.md)|Utilizzato in un'espressione di sequenza per produrre un valore per una sequenza.|
|`yield!`|[Espressioni di calcolo](computation-expressions.md)<br /><br />[Flussi di lavoro asincroni](asynchronous-workflows.md)|Utilizzato in un'espressione di calcolo per accodare il risultato di un'espressione di calcolo specificata a una raccolta di risultati per l'espressione di calcolo contenitore.|

I token seguenti sono riservati in F# perché sono parole chiave nel linguaggio OCaml:

* `asr`
* `land`
* `lor`
* `lsl`
* `lsr`
* `lxor`
* `mod`
* `sig`

Se si usa l' `--mlcompatibility` opzione del compilatore, le parole chiave precedenti sono disponibili per l'uso come identificatori.

I token seguenti sono riservati come parole chiave per l' F# espansione futura del linguaggio:

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

- [Riferimenti per il linguaggio F#](index.md)
- [Riferimenti per simboli e operatori](./symbol-and-operator-reference/index.md)
- [Opzioni del compilatore](compiler-options.md)
