---
title: Riferimento per parole chiave
description: Trovare collegamenti a informazioni su tutte le parole chiave del linguaggio F .
f1_keywords:
- new_FS
- use_FS
- end_FS
- lsl_FS
- exception_FS
- asr_FS
- if_FS
- internal_FS
- default_FS
- in_FS
- lsr_FS
- open_FS
- static_FS
- assert_FS
- match_FS
- land_FS
- with_FS
- inherit_FS
- mutable_FS
- downto_FS
- false_FS
- sig_FS
- and_FS
- true_FS
- namespace_FS
- public_FS
- lxor_FS
- val_FS
- void_FS
- downcast_FS
- function_FS
- while_FS
- for_FS
- class_FS
- done_FS
- to_FS
- module_FS
- let_FS
- delegate_FS
- abstract_FS
- then_FS
- when_FS
- lazy_FS
- try_FS
- inline_FS
- do_FS
- upcast_FS
- begin_FS
- base_FS
- fun_FS
- struct_FS
- as_FS
- extern_FS
- null_FS
- lor_FS
- return_FS
- mod_FS
- private_FS
- of_FS
- or_FS
- member_FS
- type_FS
- rec_FS
- elif_FS
- override_FS
- interface_FS
- yield_FS
- else_FS
- finally_FS
- global_FS
- select_FS
- use!_FS
dev_langs:
- FSharp
ms.date: 11/04/2019
ms.openlocfilehash: 34959f471406643e85990c2c80a38a684759a7f9
ms.sourcegitcommit: b16eacb6f94a5b601882a861ad17cc5470a8d5d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80352314"
---
# <a name="keyword-reference"></a>Riferimento per parole chiave

In questo argomento contiene collegamenti a informazioni su tutte le parole chiave del linguaggio F .

## <a name="f-keyword-table"></a>Tabella delle parole chiave di F

Nella tabella seguente vengono illustrate tutte le parole chiave di F in ordine alfabetico, insieme a brevi descrizioni e collegamenti ad argomenti pertinenti che contengono ulteriori informazioni.

|Parola chiave|Collegamento|Descrizione|
|-------|----|-----------|
|`abstract`|[Membri](./members/index.md)<br /><br />[Classi astratte](abstract-classes.md)|Indica un metodo che non dispone di alcuna implementazione nel tipo in cui viene dichiarato o che è virtuale e dispone di un'implementazione predefinita.|
|`and`|[`let`Associazioni](./functions/let-bindings.md)<br /><br />[Record](records.md)<br /><br />[Membri](./members/index.md)<br /><br />[Vincoli](./generics/constraints.md)|Utilizzato in associazioni e record ricorsivi reciproci, nelle dichiarazioni di proprietà e con più vincoli sui parametri generici.|
|`as`|[Classi](classes.md)<br /><br />[Criteri di ricerca](Pattern-Matching.md)|Utilizzato per assegnare un nome all'oggetto classe corrente. Utilizzato anche per assegnare un nome a un intero modello all'interno di una corrispondenza di modello.|
|`assert`|[Asserzioni](assertions.md)|Utilizzato per verificare il codice durante il debug.|
|`base`|[Classi](classes.md)<br /><br />[Ereditarietà](inheritance.md)|Utilizzato come nome dell'oggetto della classe base.|
|`begin`|[Sintassi dettagliata](verbose-syntax.md)|Nella sintassi dettagliata, indica l'inizio di un blocco di codice.|
|`class`|[Classi](classes.md)|Nella sintassi dettagliata, indica l'inizio di una definizione di classe.|
|`default`|[Membri](./members/index.md)|Indica un'implementazione di un metodo astratto. utilizzato insieme a una dichiarazione di metodo astratto per creare un metodo virtuale.|
|`delegate`|[Delegati](delegates.md)|Utilizzato per dichiarare un delegato.|
|`do`|[Associazioni do](./functions/do-bindings.md)<br /><br />[Cicli: espressione `for...to`](loops-for-to-expression.md)<br /><br />[Cicli: espressione `for...in`](loops-for-in-expression.md)<br /><br />[Cicli: espressione `while...do`](loops-while-do-expression.md)|Utilizzato nei costrutti di ciclo o per eseguire codice imperativo.|
|`done`|[Sintassi dettagliata](verbose-syntax.md)|Nella sintassi dettagliata, indica la fine di un blocco di codice in un'espressione ciclica.|
|`downcast`|[Cast e conversioni](casting-and-conversions.md)|Utilizzato per eseguire la conversione in un tipo più in basso nella catena di ereditarietà.|
|`downto`|[Cicli: espressione `for...to`](loops-for-to-expression.md)|In `for` un'espressione, utilizzata quando si conta in senso inverso.|
|`elif`|[Espressioni condizionali:`if...then...else`](conditional-expressions-if-then-else.md)|Utilizzato nella diramazione condizionale. Una breve `else if`forma di .|
|`else`|[Espressioni condizionali:`if...then...else`](conditional-expressions-if-then-else.md)|Utilizzato nella diramazione condizionale.|
|`end`|[Strutture](structures.md)<br /><br />[Unioni discriminate](discriminated-unions.md)<br /><br />[Record](records.md)<br /><br />[Estensioni di tipo](type-extensions.md)<br /><br />[Sintassi dettagliata](verbose-syntax.md)|Nelle definizioni di tipo e nelle estensioni di tipo, indica la fine di una sezione di definizioni di membri.<br /><br />Nella sintassi dettagliata, usata per specificare la `begin` fine di un blocco di codice che inizia con la parola chiave .|
|`exception`|[Gestione delle eccezioni](./exception-handling/index.md)<br /><br />[Tipi di eccezioneException Types](./exception-handling/exception-types.md)|Utilizzato per dichiarare un tipo di eccezione.|
|`extern`|[Funzioni esterne](./functions/external-functions.md)|Indica che un elemento di programma dichiarato è definito in un altro file binario o assembly.|
|`false`|[Tipi primitivi](basic-types.md)|Utilizzato come valore letterale booleano.|
|`finally`|[Eccezioni: espressione `try...finally`](./exception-handling/the-try-finally-expression.md)|Utilizzato insieme `try` per introdurre un blocco di codice che viene eseguito indipendentemente dal fatto che si verifichi un'eccezione.|
|`fixed`|[Fisso](fixed.md)|Utilizzato per "bloccare" un puntatore nello stack per impedirne la raccolta di rifiuti.|
|`for`|[Cicli: espressione `for...to`](loops-for-to-expression.md)<br /><br />[Espressione Loops: for...in](loops-for-in-expression.md)|Utilizzato nei costrutti di ciclo.|
|`fun`|[Espressioni lambda: `fun` la parola chiaveLambda Expressions: The Keyword](./functions/lambda-expressions-the-fun-keyword.md)|Utilizzato nelle espressioni lambda, note anche come funzioni anonime.|
|`function`|[Espressioni match](match-expressions.md)<br /><br />[Espressioni lambda: la parola chiave funLambda Expressions: The fun Keyword](./functions/lambda-expressions-the-fun-keyword.md)|Utilizzato come alternativa più `fun` breve alla `match` parola chiave e a un'espressione in un'espressione lambda con criteri di ricerca in un singolo argomento.|
|`global`|[Spazi dei nomi](namespaces.md)|Utilizzato per fare riferimento allo spazio dei nomi .NET di primo livello.|
|`if`|[Espressioni condizionali:`if...then...else`](conditional-expressions-if-then-else.md)|Utilizzato nei costrutti di diramazione condizionale.|
|`in`|[Espressione Loops: for...in](loops-for-in-expression.md)<br /><br />[Sintassi dettagliata](verbose-syntax.md)|Utilizzato per le espressioni di sequenza e, nella sintassi dettagliata, per separare le espressioni dalle associazioni.|
|`inherit`|[Ereditarietà](inheritance.md)|Utilizzato per specificare una classe base o un'interfaccia di base.|
|`inline`|[Funzioni](./functions/index.md)<br /><br />[Funzioni inline](./functions/inline-functions.md)|Utilizzato per indicare una funzione che deve essere integrata direttamente nel codice del chiamante.|
|`interface`|[Interfacce](interfaces.md)|Utilizzato per dichiarare e implementare le interfacce.|
|`internal`|[Controllo degli accessi](access-control.md)|Utilizzato per specificare che un membro è visibile all'interno di un assembly ma non all'esterno di esso.|
|`lazy`|[Espressioni lazy](lazy-expressions.md)|Utilizzato per specificare un'espressione che deve essere eseguita solo quando è necessario un risultato.|
|`let`|[`let`Associazioni](./functions/let-bindings.md)|Utilizzato per associare o associare un nome a un valore o a una funzione.|
|`let!`|[Flussi di lavoro asincroni](asynchronous-workflows.md)<br /><br />[Espressioni di calcolo](computation-expressions.md)|Utilizzato nei flussi di lavoro asincroni per associare un nome al risultato di un calcolo asincrono o, in altre espressioni di calcolo, utilizzato per associare un nome a un risultato, ovvero del tipo di calcolo.|
|`match`|[Espressioni match](match-expressions.md)|Utilizzato per eseguire la diramazione confrontando un valore con un modello.|
|`match!`|[Espressioni di calcolo](computation-expressions.md#match)|Utilizzato per inline una chiamata a un'espressione di calcolo e una corrispondenza di modello sul risultato.|
|`member`|[Membri](./members/index.md)|Utilizzato per dichiarare una proprietà o un metodo in un tipo di oggetto.|
|`module`|[Moduli](modules.md)|Utilizzato per associare un nome a un gruppo di tipi, valori e funzioni correlati per separarlo logicamente da altro codice.|
|`mutable`|[Associazioni let](./functions/let-bindings.md)|Utilizzato per dichiarare una variabile, ovvero un valore che può essere modificato.|
|`namespace`|[Spazi dei nomi](namespaces.md)|Utilizzato per associare un nome a un gruppo di tipi e moduli correlati, per separarlo logicamente da altro codice.|
|`new`|[Costruttori](./members/constructors.md)<br /><br />[Vincoli](./generics/constraints.md)|Utilizzato per dichiarare, definire o richiamare un costruttore che crea o che può creare un oggetto.<br /><br />Utilizzato anche nei vincoli di parametro generico per indicare che un tipo deve avere un determinato costruttore.|
|`not`|[Riferimenti per simboli e operatori](./symbol-and-operator-reference/index.md)<br /><br />[Vincoli](./generics/constraints.md)|In realtà non è una parola chiave. Tuttavia, `not struct` in combinazione viene utilizzato come vincolo di parametro generico.|
|`null`|[Valori NullNull Values](./values/null-values.md)<br /><br />[Vincoli](./generics/constraints.md)|Indica l'assenza di un oggetto.<br /><br />Utilizzato anche nei vincoli di parametro generico.|
|`of`|[Unioni discriminate](discriminated-unions.md)<br /><br />[Delegati](delegates.md)<br /><br />[Tipi di eccezioneException Types](./exception-handling/exception-types.md)|Utilizzato nelle unioni discriminate per indicare il tipo di categorie di valori e nelle dichiarazioni di delegato ed eccezione.|
|`open`|[Dichiarazioni di importazione: parola chiave `open`](import-declarations-the-open-keyword.md)|Utilizzato per rendere disponibile senza qualificazione il contenuto di uno spazio dei nomi o di un modulo.|
|`or`|[Riferimenti per simboli e operatori](./symbol-and-operator-reference/index.md)<br /><br />[Vincoli](./generics/constraints.md)|Utilizzato con condizioni `or` booleane come operatore booleano. È equivalente a `||`.<br /><br />Utilizzato anche nei vincoli dei membri.|
|`override`|[Membri](./members/index.md)|Utilizzato per implementare una versione di un metodo astratto o virtuale diverso dalla versione di base.|
|`private`|[Controllo degli accessi](access-control.md)|Limita l'accesso a un membro al codice nello stesso tipo o modulo.|
|`public`|[Controllo degli accessi](access-control.md)|Consente l'accesso a un membro dall'esterno del tipo.|
|`rec`|[Funzioni](./functions/index.md)|Utilizzato per indicare che una funzione è ricorsiva.|
|`return`|[Flussi di lavoro asincroni](Asynchronous-Workflows.md)<br /><br />[Espressioni di calcolo](computation-expressions.md)|Utilizzato per indicare un valore da fornire come risultato di un'espressione di calcolo.|
|`return!`|[Espressioni di calcolo](computation-expressions.md)<br /><br />[Flussi di lavoro asincroni](asynchronous-workflows.md)|Utilizzato per indicare un'espressione di calcolo che, quando viene valutata, fornisce il risultato dell'espressione di calcolo contenitore.|
|`select`|[Espressioni di queryQuery Expressions](query-expressions.md)|Utilizzato nelle espressioni di query per specificare i campi o le colonne da estrarre. Si noti che si tratta di una parola chiave contestuale, il che significa che non è in realtà una parola riservata e agisce solo come una parola chiave nel contesto appropriato.|
|`static`|[Membri](./members/index.md)|Utilizzato per indicare un metodo o una proprietà che può essere chiamata senza un'istanza di un tipo o un membro di valore condiviso tra tutte le istanze di un tipo.|
|`struct`|[Strutture](structures.md)<br /><br /> [Tuple](tuples.md)<br/><br/>[Vincoli](./generics/constraints.md)|Utilizzato per dichiarare un tipo di struttura.<br /><br/>Utilizzato per specificare una tupla struct.<br/><br />Utilizzato anche nei vincoli di parametro generico.<br /><br />Utilizzato per la compatibilità OCaml nelle definizioni dei moduli.|
|`then`|[Espressioni condizionali:`if...then...else`](conditional-expressions-if-then-else.md)<br /><br />[Costruttori](./members/constructors.md)|Utilizzato nelle espressioni condizionali.<br /><br />Utilizzato anche per eseguire effetti collaterali dopo la costruzione dell'oggetto.|
|`to`|[Cicli: espressione `for...to`](loops-for-to-expression.md)|Utilizzato `for` nei cicli per indicare un intervallo.|
|`true`|[Tipi primitivi](basic-types.md)|Utilizzato come valore letterale booleano.|
|`try`|[Eccezioni: espressione try...with](./exception-handling/the-try-with-expression.md)<br /><br />[Eccezioni: espressione try...finally](./exception-handling/the-try-finally-expression.md)|Utilizzato per introdurre un blocco di codice che potrebbe generare un'eccezione. Utilizzato insieme `with` `finally`a o .|
|`type`|[Tipi F#](fsharp-types.md)<br /><br />[Classi](classes.md)<br /><br />[Record](records.md)<br /><br />[Strutture](structures.md)<br /><br />[Enumerazioni](enumerations.md)<br /><br />[Unioni discriminate](discriminated-unions.md)<br /><br />[Abbreviazioni dei tipi](type-abbreviations.md)<br /><br />[Unità di misura](units-of-measure.md)|Utilizzato per dichiarare una classe, un record, una struttura, un'unione discriminata, un tipo di enumerazione, un'unità di misura o un'abbreviazione di tipo.|
|`upcast`|[Cast e conversioni](casting-and-conversions.md)|Utilizzato per eseguire la conversione in un tipo più in alto nella catena di ereditarietà.|
|`use`|[Gestione delle risorse: parola chiave `use`](resource-management-the-use-keyword.md)|Utilizzato al `let` posto di `Dispose` per i valori che devono essere chiamati per liberare risorse.|
|`use!`|[Espressioni di calcolo](computation-expressions.md)<br /><br />[Flussi di lavoro asincroni](asynchronous-workflows.md)|Utilizzato al `let!` posto dei flussi di lavoro `Dispose` asincroni e di altre espressioni di calcolo per i valori che devono essere chiamati per liberare risorse.|
|`val`|[Campi espliciti: parola chiave `val`](./members/explicit-fields-the-val-keyword.md)<br /><br />[Firme](signature-files.md)<br /><br />[Membri](./members/index.md)|Utilizzato in una firma per indicare un valore o in un tipo per dichiarare un membro in situazioni limitate.|
|`void`|[Tipi primitivi](basic-types.md)|Indica il tipo `void` .NET. Utilizzato quando si interagisce con altri linguaggi .NET.|
|`when`|[Vincoli](./generics/constraints.md)|Utilizzato per le condizioni booleane (*when guards*) nelle corrispondenze di criteri e per introdurre una clausola di vincolo per un parametro di tipo generico.|
|`while`|[Cicli: espressione `while...do`](loops-while-do-expression.md)|Introduce un costrutto di ciclo.|
|`with`|[Espressioni match](match-expressions.md)<br /><br />[Espressioni di oggetto](object-expressions.md)<br /><br />[Copiare e aggiornare espressioni di record](copy-and-update-record-expressions.md)<br /><br />[Estensioni di tipo](type-extensions.md)<br /><br />[Eccezioni: espressione `try...with`](./exception-handling/the-try-with-expression.md)|Utilizzato insieme `match` alla parola chiave nelle espressioni di criteri di ricerca. Utilizzato anche nelle espressioni oggetto, nelle espressioni di copia dei record e nelle estensioni dei tipi per introdurre le definizioni dei membri e per introdurre i gestori di eccezioni.|
|`yield`|[Elenchi](lists.md), [Matrici](arrays.md), [Sequenze](sequences.md)|Utilizzato in un'espressione di elenco, matrice o sequenza per produrre un valore per una sequenza. In genere può essere omesso, come è implicito nella maggior parte delle situazioni.|
|`yield!`|[Espressioni di calcolo](computation-expressions.md)<br /><br />[Flussi di lavoro asincroni](asynchronous-workflows.md)|Utilizzato in un'espressione di calcolo per aggiungere il risultato di una determinata espressione di calcolo a una raccolta di risultati per l'espressione di calcolo contenitore.|

I token seguenti sono riservati in F, perché sono parole chiave nel linguaggio OCaml:The following tokens are reserved in F, because they are keywords in the OCaml language:

- `asr`
- `land`
- `lor`
- `lsl`
- `lsr`
- `lxor`
- `mod`
- `sig`

Se si `--mlcompatibility` utilizza l'opzione del compilatore, le parole chiave precedenti sono disponibili per l'utilizzo come identificatori.

I token seguenti sono riservati come parole chiave per l'espansione futura del linguaggio F:

- `atomic`
- `break`
- `checked`
- `component`
- `const`
- `constraint`
- `constructor`
- `continue`
- `eager`
- `event`
- `external`
- `functor`
- `include`
- `method`
- `mixin`
- `object`
- `parallel`
- `process`
- `protected`
- `pure`
- `sealed`
- `tailcall`
- `trait`
- `virtual`
- `volatile`

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento al linguaggio F](index.md)
- [Riferimenti per simboli e operatori](./symbol-and-operator-reference/index.md)
- [Opzioni del compilatore](compiler-options.md)
