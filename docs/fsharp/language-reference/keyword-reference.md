---
title: Riferimento per parole chiave
description: Fare clic sui collegamenti alle informazioni relative a tutte le F# parole chiave del linguaggio.
ms.date: 05/16/2016
ms.openlocfilehash: 20592c57e09c6e0f09bb3acae021369ac5e511d6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54579839"
---
# <a name="keyword-reference"></a>Riferimento per parole chiave

In questo argomento contiene collegamenti a informazioni su tutti i F# parole chiave del linguaggio.

## <a name="f-keyword-table"></a>F#Tabella delle parole chiave

La tabella seguente illustra tutti i F# parole chiave in ordine alfabetico, insieme a brevi descrizioni e collegamenti agli argomenti rilevanti che contengono altre informazioni.

|Parola chiave|Collegamento|Descrizione|
|-------|----|-----------|
|`abstract`|[Membri](members/index.md)<br /><br />[Classi astratte](abstract-classes.md)|Indica un metodo che non dispone di implementazione del tipo in cui viene dichiarato o che è virtuale e ha un'implementazione predefinita.|
|`and`|[`let` associazioni](functions/let-bindings.md)<br /><br />[Record](records.md)<br /><br />[Membri](members/index.md)<br /><br />[Vincoli](generics/constraints.md)|Utilizzato, si escludono a vicenda associazioni ricorsive e i record in dichiarazioni di proprietà e con più vincoli sui parametri generici.|
|`as`|[Classi](classes.md)<br /><br />[Criteri di ricerca](Pattern-Matching.md)|Usato per assegnare un nome di oggetto oggetto della classe corrente. Usato anche per assegnare un nome a un intero modello all'interno di un criterio di ricerca.|
|`assert`|[Asserzioni](assertions.md)|Utilizzato per verificare il codice durante il debug.|
|`base`|[Classi](classes.md)<br /><br />[Ereditarietà](inheritance.md)|Utilizzato come nome dell'oggetto della classe base.|
|`begin`|[Sintassi dettagliata](verbose-syntax.md)|Nella sintassi dettagliata, indica l'inizio di un blocco di codice.|
|`class`|[Classi](classes.md)|Nella sintassi dettagliata, indica l'inizio di una definizione di classe.|
|`default`|[Membri](members/index.md)|Indica un'implementazione di un metodo astratto. utilizzato insieme a una dichiarazione di metodo astratto per creare un metodo virtuale.|
|`delegate`|[Delegati](delegates.md)|Usata per dichiarare un delegato.|
|`do`|[Associazioni do](functions/do-bindings.md)<br /><br />[Cicli: `for...to` Expression](loops-for-to-expression.md)<br /><br />[Cicli: `for...in` Expression](loops-for-in-expression.md)<br /><br />[Cicli: `while...do` Expression](loops-while-do-expression.md)|Utilizzato in costrutti di ciclo per eseguire il codice imperativo.|
|`done`|[Sintassi dettagliata](verbose-syntax.md)|Nella sintassi dettagliata, indica la fine di un blocco di codice in un'espressione di ciclo.|
|`downcast`|[Cast e conversioni](casting-and-conversions.md)|Consente di convertire un tipo di livello inferiore nella catena di ereditarietà.|
|`downto`|[Cicli: `for...to` Expression](loops-for-to-expression.md)|In un `for` espressione, utilizzata quando il conteggio in ordine inverso.|
|`elif`|[Espressioni condizionali: `if...then...else`](conditional-expressions-if-then-else.md)|Utilizzato nella diramazione condizionale. Una versione abbreviata di `else if`.|
|`else`|[Espressioni condizionali: `if...then...else`](conditional-expressions-if-then-else.md)|Utilizzato nella diramazione condizionale.|
|`end`|[Strutture](structures.md)<br /><br />[Unioni discriminate](discriminated-unions.md)<br /><br />[Record](records.md)<br /><br />[Estensioni di tipo](type-extensions.md)<br /><br />[Sintassi dettagliata](verbose-syntax.md)|Nelle definizioni di tipi ed estensioni di tipo, indica la fine di una sezione di definizioni dei membri.<br /><br />Nella sintassi dettagliata viene usata per specificare la fine di un blocco di codice che inizia con la `begin` (parola chiave).|
|`exception`|[Gestione delle eccezioni](exception-handling/index.md)<br /><br />[Tipi di eccezione](exception-handling/exception-types.md)|Usata per dichiarare un tipo di eccezione.|
|`extern`|[Funzioni esterne](functions/external-functions.md)|Indica che un elemento dichiarato del programma è definito in un altro file binario o assembly.|
|`false`|[Tipi primitivi](primitive-types.md)|Usati come valori letterali booleani.|
|`finally`|[Eccezioni: Il `try...finally` espressione](exception-handling/the-try-finally-expression.md)|Usata in combinazione con `try` per introdurre un blocco di codice che viene eseguito indipendentemente dal fatto che si verifica un'eccezione.|
|`fixed`|[Fixed](fixed.md)|Consente di "aggiungere" un puntatore dello stack per impedire che venga sottoposto a garbage collection.|
|`for`|[Cicli: `for...to` Expression](loops-for-to-expression.md)<br /><br />[Espressione Loops: for...in](loops-for-in-expression.md)|Utilizzato in costrutti di ciclo.|
|`fun`|[Espressioni lambda: Parola chiave `fun`](functions/lambda-expressions-the-fun-keyword.md)|Usato nelle espressioni lambda, anche note come funzioni anonime.|
|`function`|[Espressioni match](match-expressions.md)<br /><br />[Espressioni lambda: Parola chiave fun](functions/lambda-expressions-the-fun-keyword.md)|Usato come alternativa più breve per il `fun` parola chiave e un `match` espressione in un'espressione lambda con criteri di ricerca in un singolo argomento.|
|`global`|[Spazi dei nomi](namespaces.md)|Utilizzato per fare riferimento il primo livello dello spazio dei nomi .NET.|
|`if`|[Espressioni condizionali: `if...then...else`](conditional-expressions-if-then-else.md)|Utilizzato in costrutti di diramazioni condizionali.|
|`in`|[Espressione Loops: for...in](loops-for-in-expression.md)<br /><br />[Sintassi dettagliata](verbose-syntax.md)|Utilizzato per le espressioni di sequenza e, nella sintassi dettagliata, per separare le espressioni dalle associazioni.|
|`inherit`|[Ereditarietà](inheritance.md)|Consente di specificare una classe di base o interfaccia di base.|
|`inline`|[Funzioni](functions/index.md)<br /><br />[Funzioni inline](functions/inline-functions.md)|Utilizzato per indicare che una funzione che deve essere integrata direttamente nel codice del chiamante.|
|`interface`|[Interfacce](interfaces.md)|Usato per dichiarare e implementare interfacce.|
|`internal`|[Controllo di accesso](access-control.md)|Consente di specificare che un membro è visibile all'interno di un assembly, ma non al suo esterno.|
|`lazy`|[Calcoli differiti](lazy-computations.md)|Consente di specificare un calcolo che deve essere eseguita solo quando è necessario un risultato.|
|`let`|[`let` associazioni](functions/let-bindings.md)|Utilizzato per associare o di binding, un nome a un valore o una funzione.|
|`let!`|[Flussi di lavoro asincroni](asynchronous-workflows.md)<br /><br />[Espressioni di calcolo](computation-expressions.md)|Usato nei flussi di lavoro asincrone per associare un nome al risultato di un calcolo asincrono o, in altre espressioni di calcolo, utilizzati per associare un nome a un risultato, che è del tipo di calcolo.|
|`match`|[Espressioni match](match-expressions.md)|Utilizzato al ramo confrontando un valore a un modello.|
|`match!`|[Espressioni di calcolo](computation-expressions.md#match)|Utilizzato per inline una chiamata a una corrispondenza di espressione e modello di calcolo nel relativo risultato.|
|`member`|[Membri](members/index.md)|Usata per dichiarare una proprietà o metodo in un tipo di oggetto.|
|`module`|[Moduli](modules.md)|Utilizzato per associare un nome a un gruppo di tipi correlati, valori e le funzioni, per separare logicamente da altro codice.|
|`mutable`|[Associazioni let](functions/let-bindings.md)|Usata per dichiarare una variabile, vale a dire, un valore che può essere modificato.|
|`namespace`|[Spazi dei nomi](namespaces.md)|Utilizzato per associare un nome a un gruppo di tipi correlati e i moduli, per separare logicamente da altro codice.|
|`new`|[Costruttori](members/constructors.md)<br /><br />[Vincoli](generics/constraints.md)|Consente di dichiarare, definire o richiamare un costruttore che crea o che può creare un oggetto.<br /><br />Usato anche in vincoli del parametro generico per indicare che un tipo deve avere un costruttore di determinati.|
|`not`|[Riferimenti per simboli e operatori](symbol-and-operator-reference/index.md)<br /><br />[Vincoli](generics/constraints.md)|Non è effettivamente una parola chiave. Tuttavia, `not struct` insieme viene usato come vincolo il parametro generico.|
|`null`|[Valori Null](values/null-values.md)<br /><br />[Vincoli](generics/constraints.md)|Indica l'assenza di un oggetto.<br /><br />Usato anche in vincoli del parametro generico.|
|`of`|[Unioni discriminate](discriminated-unions.md)<br /><br />[Delegati](delegates.md)<br /><br />[Tipi di eccezione](exception-handling/exception-types.md)|Usato nelle unioni discriminate per indicare il tipo di categorie di valori e nelle dichiarazioni di delegato e l'eccezione.|
|`open`|[Dichiarazioni di importazione: Parola chiave `open`](import-declarations-the-open-keyword.md)|Utilizzato per rendere il contenuto di un modulo o dello spazio dei nomi disponibili senza qualifica.|
|`or`|[Riferimenti per simboli e operatori](symbol-and-operator-reference/index.md)<br /><br />[Vincoli](generics/constraints.md)|Utilizzato con condizioni booleane come un valore booleano `or` operatore. Equivalente a '||`.<br /><br />Utilizzato anche nei vincoli di membro.|
|`override`|[Membri](members/index.md)|Usato per implementare una versione di un metodo astratto o virtuale che è diversa dalla versione di base.|
|`private`|[Controllo di accesso](access-control.md)|Limita l'accesso a un membro al codice nello stesso tipo o modulo.|
|`public`|[Controllo di accesso](access-control.md)|Consente l'accesso a un membro dall'esterno del tipo.|
|`rec`|[Funzioni](functions/index.md)|Utilizzato per indicare che una funzione è ricorsiva.|
|`return`|[Flussi di lavoro asincroni](Asynchronous-Workflows.md)<br /><br />[Espressioni di calcolo](computation-expressions.md)|Utilizzato per indicare un valore da fornire come risultato di un'espressione di calcolo.|
|`return!`|[Espressioni di calcolo](computation-expressions.md)<br /><br />[Flussi di lavoro asincroni](asynchronous-workflows.md)|Utilizzato per indicare un'espressione di calcolo che, quando valutata, fornisce il risultato dell'espressione di calcolo che lo contiene.|
|`select`|[Espressioni di query](query-expressions.md)|Utilizzato nelle espressioni di query per specificare quali campi o le colonne da estrarre. Si tratta di una parola chiave contestuale, che significa che non è effettivamente una parola riservata e OCS funge solo da una parola chiave nel contesto appropriato.|
|`static`|[Membri](members/index.md)|Utilizzato per indicare un metodo o proprietà che può essere chiamato senza un'istanza di un tipo o membro condiviso tra tutte le istanze di un tipo valore.|
|`struct`|[Strutture](structures.md)<br /><br />[Vincoli](generics/constraints.md)|Usata per dichiarare un tipo di struttura.<br /><br />Usato anche in vincoli del parametro generico.<br /><br />Utilizzato per la compatibilità OCaml nelle definizioni dei moduli.|
|`then`|[Espressioni condizionali: `if...then...else`](conditional-expressions-if-then-else.md)<br /><br />[Costruttori](members/constructors.md)|Usato nelle espressioni condizionali.<br /><br />Usato anche per ottenere effetti collaterali dopo la costruzione di oggetti.|
|`to`|[Cicli: `for...to` Expression](loops-for-to-expression.md)|Utilizzato in `for` cicli per indicare un intervallo.|
|`true`|[Tipi primitivi](primitive-types.md)|Usati come valori letterali booleani.|
|`try`|[Eccezioni: Try... with espressione](exception-handling/the-try-with-expression.md)<br /><br />[Eccezioni: Try... espressione finally](exception-handling/the-try-finally-expression.md)|Usato per presentare un blocco di codice che potrebbe generare un'eccezione. Usata in combinazione con `with` o `finally`.|
|`type`|[Tipi F#](fsharp-types.md)<br /><br />[Classi](classes.md)<br /><br />[Record](records.md)<br /><br />[Strutture](structures.md)<br /><br />[Enumerazioni](enumerations.md)<br /><br />[Unioni discriminate](discriminated-unions.md)<br /><br />[Abbreviazioni dei tipi](type-abbreviations.md)<br /><br />[Unità di misura](units-of-measure.md)|Usata per dichiarare una classe, record, struttura, unione discriminata, tipo di enumerazione, unità di misura, o abbreviazione di tipo.|
|`upcast`|[Cast e conversioni](casting-and-conversions.md)|Usata per convertire in un tipo di livello superiore nella catena di ereditarietà.|
|`use`|[Gestione delle risorse: Parola chiave `use`](resource-management-the-use-keyword.md)|Utilizzare al posto di `let` per i valori che richiedono `Dispose` da chiamare per liberare risorse.|
|`use!`|[Espressioni di calcolo](computation-expressions.md)<br /><br />[Flussi di lavoro asincroni](asynchronous-workflows.md)|Utilizzare al posto di `let!` flussi di lavoro asincroni e altre espressioni di calcolo per i valori che richiedono `Dispose` da chiamare per liberare risorse.|
|`val`|[Campi espliciti: Parola chiave `val`](members/explicit-fields-the-val-keyword.md)<br /><br />[Firme](signatures.md)<br /><br />[Membri](members/index.md)|Utilizzato in una firma per indicare un valore o in un tipo per dichiarare un membro, in alcune situazioni.|
|`void`|[Tipi primitivi](primitive-types.md)|Indica il .NET `void` tipo. Utilizzato quando si interagisce con altri linguaggi .NET.|
|`when`|[Vincoli](generics/constraints.md)|Utilizzato per le condizioni booleane (*quando si protegge*) in Criteri di corrispondenza e introdurre una clausola di vincolo per un parametro di tipo generico.|
|`while`|[Cicli: `while...do` Expression](loops-while-do-expression.md)|Introduce un costrutto di ciclo.|
|`with`|[Espressioni match](match-expressions.md)<br /><br />[Espressioni di oggetto](object-expressions.md)<br /><br />[Copiare e aggiornare espressioni di record](copy-and-update-record-expressions.md)<br /><br />[Estensioni di tipo](type-extensions.md)<br /><br />[Eccezioni: Il `try...with` espressione](exception-handling/the-try-with-expression.md)|Usata in combinazione con il `match` parola chiave in Criteri di ricerca di espressioni. Utilizzato anche nelle espressioni di oggetto, copia le espressioni di record e digitare le estensioni per introdurre le definizioni dei membri, nonché di introdurre i gestori di eccezioni.|
|`yield`|[Sequenze](sequences.md)|Usato in un'espressione di sequenza per produrre un valore per una sequenza.|
|`yield!`|[Espressioni di calcolo](computation-expressions.md)<br /><br />[Flussi di lavoro asincroni](asynchronous-workflows.md)|Usato in un'espressione di calcolo per aggiungere il risultato di un'espressione di calcolo specificato da una raccolta di risultati per l'espressione di calcolo che lo contiene.|

I token seguenti sono riservati in F# perché sono parole chiave del linguaggio OCaml:

* `asr`
* `land`
* `lor`
* `lsl`
* `lsr`
* `lxor`
* `mod`
* `sig`

Se si usa il `--mlcompatibility` opzione del compilatore, le parole chiave precedente possono essere utilizzati come identificatori.

I token seguenti vengono usati esclusivamente come parole chiave per l'espansione futura del F# linguaggio:

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
- [Riferimenti per simboli e operatori](symbol-and-operator-reference/index.md)
- [Opzioni del compilatore](compiler-options.md)