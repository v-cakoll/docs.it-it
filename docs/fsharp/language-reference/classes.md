---
title: Classi (F#)
description: 'Informazioni su come le classi di F # sono tipi che rappresentano oggetti che possono avere proprietà, metodi ed eventi.'
ms.date: 05/16/2016
ms.openlocfilehash: 71cd713d192d28565e879b79b2fc9e0530e5f841
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44138825"
---
# <a name="classes"></a>Classi

*Le classi* sono tipi che rappresentano oggetti che possono avere proprietà, metodi ed eventi.

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

Le classi rappresentano la descrizione fondamentale dei tipi di oggetto .NET. la classe è il concetto di tipo primario che supporta la programmazione orientata agli oggetti in F #.

Nella sintassi precedente, il `type-name` qualsiasi identificatore valido. Il `type-params` vengono descritti i parametri di tipo generico facoltativo. È costituito da nomi di parametro di tipo e vincoli racchiuso tra parentesi angolari (`<` e `>`). Per altre informazioni, vedere [Generics](generics/index.md) e [vincoli](generics/constraints.md). Il `parameter-list` vengono descritti i parametri del costruttore. Il modificatore di accesso prima si riferisce il tipo. il secondo riguarda il costruttore primario. In entrambi i casi, il valore predefinito è `public`.

Specificare la classe base per una classe usando la `inherit` (parola chiave). È necessario fornire argomenti, racchiusi tra parentesi, per il costruttore di classe di base.

Si dichiara i campi o che sono locali rispetto alla classe con valori di funzione `let` associazioni ed è necessario seguire le regole generali per `let` associazioni. Il `do-bindings` sezione include il codice da eseguire durante la costruzione di oggetti.

Il `member-list` include costruttori aggiuntivi, istanza e le dichiarazioni di metodo statico, le dichiarazioni di interfaccia, associazioni astratte e dichiarazioni di proprietà ed eventi. Questi elementi sono descritti [membri](members/index.md).

Il `identifier` che viene usato con l'opzione facoltativa `as` (parola chiave) fornisce un nome per la variabile di istanza oppure autoidentificatore, che può essere utilizzato nella definizione del tipo per fare riferimento all'istanza del tipo. Per altre informazioni, vedere la sezione autoidentificatori più avanti in questo argomento.

Le parole chiave `class` e `end` che contrassegna l'inizio e fine della definizione sono facoltativi.

Si escludono a vicenda tipi ricorsiva, che sono tipi che fanno riferimento a altro, vengono uniti dall'operatore di `and` (parola chiave) come funzioni ricorsive reciproche. Per un esempio, vedere la sezione si escludono a vicenda tipi ricorsiva.

## <a name="constructors"></a>Costruttori

Il costruttore è codice che crea un'istanza del tipo di classe. Costruttori di classi funzionano in modo diverso in F # rispetto ai colleghi in altri linguaggi .NET. In una classe di F #, è sempre presente un costruttore primario i cui argomenti sono descritti nel `parameter-list` che segue il nome del tipo e il cui corpo è costituito il `let` (e `let rec`) associazioni all'inizio della dichiarazione di classe e il `do`associazioni che seguono. Gli argomenti del costruttore primario sono nell'ambito della dichiarazione di classe.

È possibile aggiungere costruttori aggiuntivi utilizzando la `new` (parola chiave) per aggiungere un membro, come indicato di seguito:

`new`(`argument-list`) = `constructor-body`

Il corpo del costruttore della nuova deve richiamare il costruttore primario specificato nella parte superiore della dichiarazione di classe.

Nell'esempio seguente illustra questo concetto. Nel codice seguente, `MyClass` dispone di due costruttori, un costruttore primario che accetta due argomenti e un altro costruttore che non accetta argomenti.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2401.fs)]

## <a name="let-and-do-bindings"></a>Let e associazioni do

Il `let` e `do` associazioni in una definizione di classe costituiscono il corpo del costruttore della classe primaria e pertanto vengono eseguiti ogni volta che viene creata un'istanza della classe. Se un `let` associazione è una funzione, quindi viene compilato in un membro. Se il `let` binding è un valore che non viene usato in qualsiasi funzione o un membro, quindi viene compilato in una variabile locale per il costruttore. In caso contrario, viene compilato in un campo della classe. Il `do` espressioni che seguono vengono compilate nel costruttore primario ed eseguire il codice di inizializzazione per ogni istanza. Poiché i costruttori aggiuntivi sempre chiamare il costruttore principale, il `let` associazioni e `do` vengono sempre eseguite, indipendentemente da quale costruttore viene chiamato.

I campi che vengono creati da `let` associazioni sono accessibili nel corso dei metodi e proprietà della classe; tuttavia, non è accessibile da metodi statici, anche se i metodi statici accettare una variabile di istanza come parametro. Essi non è accessibile tramite l'autoidentificatore, se presente.

## <a name="self-identifiers"></a>Autoidentificatori

Oggetto *autoidentificatore* è un nome che rappresenta l'istanza corrente. Sono simili a autoidentificatori il `this` parola chiave in c# o C++ o `Me` in Visual Basic. È possibile definire un identificatore automatico in due modi diversi, a seconda che si voglia l'autoidentificatore nell'ambito per l'intera definizione di classe o solo per un singolo metodo.

Per definire un identificatore automatico per l'intera classe, usare il `as` (parola chiave) dopo la parentesi di chiusura del parametro del costruttore elencare e specificare il nome dell'identificatore.

Per definire un identificatore automatico per un solo metodo, fornire l'autoidentificatore nella dichiarazione del membro, appena prima del nome del metodo e un punto (.) come separatore.

Esempio di codice seguente illustra due modi per creare un identificatore utente. Nella prima riga, il `as` parola chiave viene usata per definire l'autoidentificatore. Nella quinta riga, l'identificatore `this` viene usato per definire un identificatore utente il cui ambito è limitato al metodo `PrintMessage`.

```fsharp
type MyClass2(dataIn) as self =
    let data = dataIn
    do
        self.PrintMessage()
    member this.PrintMessage() =
        printf "Creating MyClass2 with Data %d" data
```

A differenza di altri linguaggi .NET, è possibile denominare l'autoidentificatore come preferisci; non è limitato ai nomi, ad esempio `self`, `Me`, o `this`.

Stesso identificatore dichiarato con la `as` parola chiave non viene inizializzata finché dopo il `let` associazioni vengono eseguite. Pertanto, non può essere usato nel `let` associazioni. È possibile usare l'autoidentificatore nel `do` sezione delle associazioni.

## <a name="generic-type-parameters"></a>Parametri di tipo generico

Parametri di tipo generico specificati parentesi angolari (`<` e `>`), sotto forma di una virgoletta singola, seguita da un identificatore. Più parametri di tipo generico sono separati da virgole. Il parametro di tipo generico è nell'ambito della dichiarazione. Esempio di codice seguente viene illustrato come specificare i parametri di tipo generico.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2403.fs)]

Gli argomenti di tipo vengono dedotti quando viene utilizzato il tipo. Nel codice seguente, il tipo dedotto è una sequenza di tuple.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24031.fs)]

## <a name="specifying-inheritance"></a>Impostazione dell'ereditarietà

Il `inherit` clausola identifica la classe di base diretta, se presente. In F #, è consentita una sola classe base diretta. Interfacce implementate da una classe non vengono considerate classi base. Le interfacce vengono discussi nel [interfacce](Interfaces.md) argomento.

È possibile accedere i metodi e le proprietà della classe base dalla classe derivata usando la parola chiave del linguaggio `base` come identificatore, seguito da un punto (.) e il nome del membro.

Per altre informazioni, vedere [Ereditarietà](inheritance.md).

## <a name="members-section"></a>Sezione membri

È possibile definire statico o i metodi di istanza, le proprietà, le implementazioni dell'interfaccia, i membri astratti, le dichiarazioni di eventi e costruttori aggiuntivi in questa sezione. Let ed effettuare associazioni non può trovarsi in questa sezione. Poiché è possibile aggiungere membri a una varietà di tipi F #, oltre alle classi, questi vengono illustrati in un argomento separato [membri](members/index.md).

## <a name="mutually-recursive-types"></a>Si escludono a vicenda tipi ricorsiva

Quando si definiscono i tipi che fanno riferimento a altro in modo circolare, è unire le definizioni dei tipi tramite la `and` (parola chiave). Il `and` parola chiave sostituisce il `type` la parola chiave nel tutto eccetto la prima definizione, come indicato di seguito.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2404.fs)]

L'output è un elenco di tutti i file nella directory corrente.

## <a name="when-to-use-classes-unions-records-and-structures"></a>Quando usare le classi, unioni discriminate, record e strutture

Data la varietà di tipi tra cui scegliere, è necessario avere una buona conoscenza di ciò che è progettato per ogni tipo per selezionare il tipo appropriato per una determinata situazione. Classi sono progettate per l'uso in contesti di programmazione orientata agli oggetti. La programmazione orientata agli oggetti è il paradigma principale usato dalle applicazioni che sono destinate a .NET Framework. Se il codice F # deve lavorare a stretto contatto con .NET Framework o a un'altra libreria orientate a oggetti e soprattutto se è necessario estendere da un sistema di tipi orientate a oggetti, ad esempio una libreria dell'interfaccia utente, le classi sono probabilmente appropriate.

Se non si interagisce strettamente con il codice orientate a oggetti o se si sta scrivendo codice che è indipendente e pertanto protetti contro il frequente interazione con codice orientate a oggetti, è consigliabile usare record e unioni discriminate. Un singolo, anche pensiero – out unione discriminata, insieme a codice, corrispondenza dei appropriato può spesso essere utilizzato come un'alternativa più semplice per una gerarchia di oggetti. Per altre informazioni sulle unioni discriminate, vedere [unioni discriminate](discriminated-unions.md).

I record hanno il vantaggio di essere più semplice rispetto alle classi, ma non sono appropriati quando le richieste di un tipo di superare i risultati ottenuti con la loro semplicità. I record sono fondamentalmente aggregazioni semplici di valori, senza costruttori separati che possono eseguire azioni personalizzate, senza campi nascosti e senza alcuna implementazione dell'ereditarietà o interfaccia. Anche se i membri, ad esempio proprietà e metodi possono essere aggiunti ai record per rendere il proprio comportamento più complesso, i campi archiviati in un record sono comunque una semplice aggregazione di valori. Per altre informazioni sui record, vedere [record](records.md).

Le strutture sono utili anche per piccole aggregazioni di dati, ma si differenziano dalle classi e i record in quanto sono tipi di valore .NET. Classi e i record sono i tipi di riferimento .NET. La semantica dei tipi di valore e tipi di riferimento è diversa in quanto i tipi di valore vengono passati per valore. Ciò significa che vengono copiati in bit per bit quando vengono passati come parametro o restituiti da una funzione. Vengono inoltre archiviate nello stack o, se vengono usati come un campo, incorporato all'interno dell'oggetto padre anziché archiviati nel proprio percorso separato nell'heap. Pertanto, le strutture sono appropriate per i dati utilizzati di frequente quando il sovraccarico dovuto all'accesso l'heap è un problema. Per altre informazioni sulle strutture, vedere [strutture](structures.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Membri](members/index.md)
- [Ereditarietà](inheritance.md)
- [Interfacce](interfaces.md)
