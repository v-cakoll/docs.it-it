---
title: Classi (F#)
description: "Informazioni su come le classi F # sono tipi che rappresentano oggetti che possono disporre di proprietà, metodi ed eventi."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: d58679d5-7753-4b3b-a12f-6e9f00ed5ba3
ms.openlocfilehash: 2a73baba1f7c1b0d3bd09d22c9d6d9f0524daef3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="classes"></a>Classi

*Classi* sono tipi che rappresentano oggetti che possono disporre di proprietà, metodi ed eventi.


## <a name="syntax"></a>Sintassi

```fsharp
// Class definition:
type [access-modifier] type-name [type-params] [access-modifier] ( parameter-list ) [ as identifier ] =
[ class ]
[ inherit base-type-name(base-constructor-args) ]
[ let-bindings ]
[ do-bindings ]
member-list
...
[ end ]
// Mutually recursive class definitions:
type [access-modifier] type-name1 ...
and [access-modifier] type-name2 ...
...
```

## <a name="remarks"></a>Note
Le classi rappresentano la descrizione fondamentale dei tipi di oggetto .NET. la classe è il concetto di tipo primario che supporta la programmazione orientata a oggetti in F #.

Nella sintassi precedente, il `type-name` qualsiasi identificatore valido. Il `type-params` vengono descritti i parametri di tipo generico facoltativi. È costituito da nomi di parametro di tipo e vincoli racchiuso tra parentesi angolari (`<` e `>`). Per ulteriori informazioni, vedere [Generics](generics/index.md) e [vincoli](generics/constraints.md). Il `parameter-list` descrive i parametri del costruttore. Il primo modificatore di accesso relativo al tipo; il secondo si riferisce al costruttore primario. In entrambi i casi, il valore predefinito è `public`.

Specificare la classe base per una classe utilizzando il `inherit` (parola chiave). È necessario fornire argomenti tra parentesi, per il costruttore di classe di base.

Si dichiara campi o valori di locale per la classe di funzioni `let` associazioni e si devono seguire le regole generali per `let` associazioni. Il `do-bindings` sezione include codice da eseguire durante la costruzione di oggetti.

Il `member-list` include costruttori aggiuntivi, istanza e le dichiarazioni di metodo statico, le dichiarazioni di interfaccia, associazioni astratte e dichiarazioni di proprietà ed eventi. Questi elementi sono descritti [membri](members/index.md).

Il `identifier` utilizzato con l'opzione facoltativa `as` (parola chiave) fornisce un nome per la variabile di istanza o autoidentificatore, che può essere utilizzato nella definizione del tipo per fare riferimento all'istanza del tipo. Per ulteriori informazioni, vedere la sezione autoidentificatori più avanti in questo argomento.

Le parole chiave `class` e `end` che contrassegna l'inizio e fine della definizione sono facoltativi.

Si escludono a tipi ricorsiva, che sono tipi che fanno riferimento a altro, vengono uniti con il `and` parola chiave come funzioni ricorsive reciproche. Per un esempio, vedere la sezione tipi ricorsivi reciproci.


## <a name="constructors"></a>Costruttori
Il costruttore è codice che crea un'istanza del tipo di classe. Costruttori di classi eseguite in modo diverso in F # rispetto a in altri linguaggi .NET. In una classe F #, è sempre un costruttore primario i cui argomenti sono descritti nel `parameter-list` che segue il nome del tipo e il cui corpo è costituito il `let` (e `let rec`) associazioni all'inizio della dichiarazione di classe e il `do`associazioni che seguono. Gli argomenti del costruttore primario sono nell'ambito della dichiarazione di classe.

È possibile aggiungere costruttori aggiuntivi tramite il `new` (parola chiave) per aggiungere un membro, come indicato di seguito:

`new`(`argument-list`) = `constructor-body`

Il corpo del costruttore della nuova deve richiamare il costruttore primario specificato nella parte superiore della dichiarazione di classe.

Nell'esempio seguente viene illustrato questo concetto. Nel codice seguente, `MyClass` dispone di due costruttori, un costruttore primario che accetta due argomenti e un altro costruttore che non accetta argomenti.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2401.fs)]
    
## <a name="let-and-do-bindings"></a>Associazioni let e do

Il `let` e `do` binding in una definizione di classe formano il corpo del costruttore della classe primaria e pertanto vengono eseguiti ogni volta che viene creata un'istanza della classe. Se un `let` associazione è una funzione, quindi viene compilato in un membro. Se il `let` associazione è un valore che non viene utilizzato in qualsiasi funzione o membro, quindi viene compilato in una variabile locale per il costruttore. In caso contrario, viene compilato in un campo della classe. Il `do` espressioni che seguono vengono compilate nel costruttore primario ed eseguire il codice di inizializzazione per ogni istanza. Poiché qualsiasi costruttore aggiuntivo chiama sempre il costruttore primario, il `let` associazioni e `do` vengono sempre eseguite, indipendentemente da quale costruttore viene chiamato.

I campi che vengono creati `let` associazioni accessibili nei metodi e proprietà della classe; tuttavia, che non siano accessibili da metodi statici, anche se i metodi statici accettano una variabile di istanza come parametro. Non è possibile accedervi tramite l'autoidentificatore, se presente.


## <a name="self-identifiers"></a>Autoidentificatori

Oggetto *autoidentificatore* è un nome che rappresenta l'istanza corrente. Autoidentificatori simile di `this` (parola chiave) in c# o C++ o `Me` in Visual Basic. È possibile definire un autoidentificatore in due modi diversi, a seconda che si voglia l'autoidentificatore sia nell'ambito per l'intera definizione di classe o solo per un singolo metodo.

Per definire un autoidentificatore per l'intera classe, utilizzare il `as` (parola chiave) dopo la parentesi di chiusura del parametro del costruttore elenco e specificare il nome dell'identificatore.

Per definire un autoidentificatore solo per un metodo, fornire l'autoidentificatore nella dichiarazione del membro, appena prima del nome di metodo e un punto (.) come separatore.

Esempio di codice seguente illustra due modi per creare un identificatore utente. Nella prima riga, il `as` parola chiave viene utilizzata per definire l'autoidentificatore. Nella quinta riga, l'identificatore `this` viene utilizzato per definire un autoidentificatore il cui ambito è limitato al metodo `PrintMessage`.

```fsharp
type MyClass2(dataIn) as self =
    let data = dataIn
    do
        self.PrintMessage()
    member this.PrintMessage() =
        printf "Creating MyClass2 with Data %d" data
```

A differenza di altri linguaggi .NET, è possibile denominare l'autoidentificatore tuttavia si desidera. non sono è limitato ai nomi, ad esempio `self`, `Me`, o `this`.

L'autoidentificatore è dichiarato con la `as` parola chiave non viene inizializzato fino a dopo il `let` vengono eseguite le associazioni. Pertanto, non può essere utilizzato nel `let` associazioni. È possibile utilizzare l'autoidentificatore nella `do` sezione delle associazioni.


## <a name="generic-type-parameters"></a>Parametri di tipo generico

Parametri di tipo generico vengono specificati tra parentesi quadre (`<` e `>`), sotto forma di una virgoletta singola, seguita da un identificatore. Più parametri di tipo generico sono separati da virgole. Il parametro di tipo generico è nell'ambito della dichiarazione. Esempio di codice seguente viene illustrato come specificare i parametri di tipo generico.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2403.fs)]

Gli argomenti di tipo vengono dedotti quando viene utilizzato il tipo. Nel codice seguente, il tipo derivato è una sequenza di tuple.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24031.fs)]
    
## <a name="specifying-inheritance"></a>Impostazione dell'ereditarietà

Il `inherit` clausola identifica la classe base diretta, se presente. In F #, è consentita solo una classe base diretta. Le interfacce implementate da una classe non vengono considerate le classi di base. Vengono descritte le interfacce nella [interfacce](Interfaces.md) argomento.

È possibile accedere i metodi e proprietà della classe base dalla classe derivata utilizzando la parola chiave language `base` come identificatore, seguita da un punto (.) e il nome del membro.

Per altre informazioni, vedere [Ereditarietà](inheritance.md).


## <a name="members-section"></a>Sezione di membri
È possibile definire statici o metodi di istanza, proprietà, le implementazioni dell'interfaccia, membri astratti, dichiarazioni di eventi e costruttori aggiuntivi in questa sezione. Consentire ed effettuare associazioni non può trovarsi in questa sezione. Poiché è possibile aggiungere membri a una varietà di tipi F #, oltre alle classi, questi vengono illustrati in argomenti separati, [membri](members/index.md).


## <a name="mutually-recursive-types"></a>Tipi ricorsivi reciproci
Quando si definiscono i tipi che fanno riferimento a altro in modo circolare, unire le definizioni dei tipi utilizzando il `and` (parola chiave). Il `and` (parola chiave) sostituisce il `type` parola chiave in tutti, ad eccezione della prima definizione, come indicato di seguito.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2404.fs)]

L'output è un elenco di tutti i file nella directory corrente.


## <a name="when-to-use-classes-unions-records-and-structures"></a>Quando utilizzare strutture, unioni, record e classi
Data la varietà di tipi tra cui scegliere, è necessario avere una buona conoscenza di ciò che è progettata per ogni tipo per selezionare il tipo appropriato per una determinata situazione. Classi sono progettate per l'utilizzo in contesti di programmazione orientata agli oggetti. Programmazione orientata a oggetti è il paradigma principale utilizzato nelle applicazioni che vengono scritti per .NET Framework. Se il codice F # include a collaborare con .NET Framework o a un'altra libreria orientata agli oggetti, e in particolare se è necessario estendere da un sistema di tipo orientata agli oggetti, ad esempio una libreria dell'interfaccia utente, le classi sono probabilmente appropriate.

Se non si interagisce strettamente con il codice orientato o se si scrive codice che è indipendente e pertanto frequente interazione con codice orientata agli oggetti, si consiglia di utilizzare i record e unioni discriminate. Un singolo anche pensiero: out unione discriminata, insieme a codice, corrispondenza dei appropriato può spesso essere utilizzata come un'alternativa più semplice per una gerarchia di oggetti. Per ulteriori informazioni sulle unioni discriminate, vedere [unioni discriminate](discriminated-unions.md).

Record hanno il vantaggio di essere più semplice rispetto alle classi, ma non sono appropriati quando le richieste di un tipo superano ciò che può essere eseguita con la loro semplicità. I record sono fondamentalmente aggregazioni semplici di valori, senza costruttori distinti che possono eseguire azioni personalizzate, senza campi nascosti e senza implementazioni di interfaccia o di ereditarietà. Sebbene ai record per rendere il proprio comportamento più complesso, è possibile aggiungere membri, ad esempio proprietà e metodi, i campi archiviati in un record sono comunque una semplice aggregazione di valori. Per ulteriori informazioni sui record, vedere [record](records.md).

Le strutture sono utili anche per piccole aggregazioni di dati, ma differiscono da classi e i record in quanto sono tipi di valore .NET. Le classi e i record sono tipi di riferimento .NET. La semantica dei tipi di valore e tipi di riferimento è diversi tipi di valore vengono passati per valore. Ciò significa che vengono copiati bit per bit quando vengono passati come parametro o restituiti da una funzione. Vengono anche archiviate nello stack o, se vengono usati come un campo, incorporato all'interno dell'oggetto padre anziché archiviati in una posizione separata nell'heap. Le strutture sono pertanto appropriate per i dati utilizzati di frequente quando l'overhead di accesso all'heap è un problema. Per ulteriori informazioni sulle strutture, vedere [strutture](structures.md).


## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

[Membri](members/index.md)

[Ereditarietà](inheritance.md)

[Interfacce](interfaces.md)

