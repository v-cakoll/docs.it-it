---
title: Classi
description: Informazioni sul F# modo in cui le classi sono tipi che rappresentano oggetti che possono avere proprietà, metodi ed eventi.
ms.date: 05/16/2016
ms.openlocfilehash: 5c012d028bc1f89e3e9f5969b3461faab9aad3a0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630449"
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

Le classi rappresentano la descrizione fondamentale dei tipi di oggetto .NET; la classe è il concetto di tipo principale che supporta la programmazione orientata F#a oggetti in.

Nella sintassi precedente, `type-name` è qualsiasi identificatore valido. Descrive `type-params` i parametri facoltativi di tipo generico. È costituito da nomi di parametri di tipo e vincoli racchiusi tra`<` parentesi `>`angolari (e). Per altre informazioni, vedere [generics](./generics/index.md) and [Constraints](./generics/constraints.md). Descrive `parameter-list` i parametri del costruttore. Il primo modificatore di accesso è relativo al tipo. il secondo riguarda il costruttore primario. In entrambi i casi, il valore `public`predefinito è.

È possibile specificare la classe di base per una classe usando `inherit` la parola chiave. È necessario fornire argomenti, tra parentesi, per il costruttore della classe base.

Si dichiarano i campi o i valori delle funzioni locali alla classe `let` utilizzando le associazioni ed è necessario seguire le regole generali per `let` le associazioni. La `do-bindings` sezione include il codice da eseguire alla costruzione dell'oggetto.

`member-list` È costituito da costruttori aggiuntivi, dichiarazioni di metodi e istanze statiche, dichiarazioni di interfaccia, associazioni astratte e dichiarazioni di proprietà e eventi. Questi sono descritti in [membri](./members/index.md).

L' `identifier` oggetto utilizzato con la parola chiave `as` optional assegna un nome alla variabile di istanza o a un identificatore automatico che può essere utilizzato nella definizione del tipo per fare riferimento all'istanza del tipo. Per ulteriori informazioni, vedere la sezione identificatori autonomi più avanti in questo argomento.

Le parole `class` chiave `end` e che contrassegnano l'inizio e la fine della definizione sono facoltative.

I tipi ricorsivamente ricorsivi, ovvero i tipi che fanno riferimento l'uno all'altro, vengono `and` Uniti insieme alla parola chiave come le funzioni ricorsive reciproche. Per un esempio, vedere la sezione tipi ricorsivamente ricorsivi.

## <a name="constructors"></a>Costruttori

Il costruttore è un codice che crea un'istanza del tipo di classe. I costruttori per le classi funzionano in modo F# diverso in rispetto a quanto avviene in altri linguaggi .NET. In una F# classe è sempre presente un costruttore primario i cui argomenti sono descritti in `parameter-list` che seguono il nome del tipo e il cui `let` corpo è costituito dalle associazioni `let rec`(e) all'inizio della dichiarazione di classe e `do` associazioni che seguono. Gli argomenti del costruttore primario rientrano nell'ambito della dichiarazione di classe.

È possibile aggiungere ulteriori costruttori utilizzando la `new` parola chiave per aggiungere un membro, come indicato di seguito:

`new`(`argument-list`) = `constructor-body`

Il corpo del nuovo costruttore deve richiamare il costruttore primario specificato all'inizio della dichiarazione di classe.

Nell'esempio seguente viene illustrato questo concetto. Nel codice seguente, `MyClass` dispone di due costruttori, un costruttore primario che accetta due argomenti e un altro costruttore che non accetta argomenti.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2401.fs)]

## <a name="let-and-do-bindings"></a>Associazioni let and do

Le `let` associazioni `do` e in una definizione di classe formano il corpo del costruttore della classe primaria, quindi vengono eseguite ogni volta che viene creata un'istanza della classe. Se un' `let` associazione è una funzione, viene compilata in un membro. Se l' `let` associazione è un valore che non viene usato in alcuna funzione o membro, viene compilato in una variabile locale del costruttore. In caso contrario, viene compilato in un campo della classe. Le `do` espressioni che seguono vengono compilate nel costruttore primario ed eseguono il codice di inizializzazione per ogni istanza. Poiché tutti i costruttori aggiuntivi chiamano sempre il costruttore primario, le `let` associazioni e `do` le associazioni vengono sempre eseguite indipendentemente dal costruttore chiamato.

È possibile accedere ai campi `let` creati dalle associazioni in tutti i metodi e le proprietà della classe. Tuttavia, non è possibile accedervi dai metodi statici, anche se i metodi statici accettano una variabile di istanza come parametro. Non è possibile accedervi usando l'identificatore automatico, se disponibile.

## <a name="self-identifiers"></a>Identificatori autonomi

Un *identificatore auto* è un nome che rappresenta l'istanza corrente. Gli identificatori autonomi assomigliano `this` alla parola `Me` chiave in C# o C++ o in Visual Basic. È possibile definire un identificatore autonomo in due modi diversi, a seconda che si desideri che l'autoidentificatore sia nell'ambito per la definizione di classe intera o solo per un singolo metodo.

Per definire un identificatore automatico per l'intera classe, usare la `as` parola chiave dopo le parentesi di chiusura dell'elenco di parametri del costruttore e specificare il nome dell'identificatore.

Per definire un identificatore automatico per un solo metodo, specificare l'identificatore automatico nella dichiarazione del membro, immediatamente prima del nome del metodo e un punto (.) come separatore.

Nell'esempio di codice riportato di seguito vengono illustrati i due modi per creare un identificatore automatico. Nella prima riga, la `as` parola chiave viene usata per definire l'identificatore automatico. Nella quinta riga, l'identificatore `this` viene usato per definire un identificatore autonomo il cui ambito è limitato al metodo. `PrintMessage`

```fsharp
type MyClass2(dataIn) as self =
    let data = dataIn
    do
        self.PrintMessage()
    member this.PrintMessage() =
        printf "Creating MyClass2 with Data %d" data
```

Diversamente da altri linguaggi .NET, è possibile assegnare un nome all'identificatore automatico, non si è limitati a nomi `self`come, `Me`o `this`.

L'identificatore autonomo dichiarato con la `as` parola chiave non viene inizializzato finché non vengono eseguite le `let` associazioni. Pertanto, non può essere utilizzato nelle `let` associazioni. È possibile usare l'identificatore automatico nella `do` sezione Bindings.

## <a name="generic-type-parameters"></a>Parametri di tipo generico

I parametri di tipo generico sono specificati tra parentesi angolari (`<` e `>`), sotto forma di virgolette singole seguite da un identificatore. Più parametri di tipo generico sono separati da virgole. Il parametro di tipo generico è nell'ambito dell'intera dichiarazione. Nell'esempio di codice seguente viene illustrato come specificare parametri di tipo generico.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2403.fs)]

Gli argomenti di tipo vengono dedotti quando viene usato il tipo. Nel codice seguente, il tipo dedotto è una sequenza di Tuple.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24031.fs)]

## <a name="specifying-inheritance"></a>Specifica dell'ereditarietà

La `inherit` clausola identifica la classe di base diretta, se ne esiste una. In F#è consentita una sola classe di base diretta. Le interfacce implementate da una classe non sono considerate classi di base. Le interfacce sono descritte nell'argomento [interfacce](Interfaces.md) .

È possibile accedere ai metodi e alle proprietà della classe di base dalla classe derivata usando la parola chiave `base` del linguaggio come identificatore, seguito da un punto (.) e dal nome del membro.

Per altre informazioni, vedere [Ereditarietà](inheritance.md).

## <a name="members-section"></a>Sezione Members

In questa sezione è possibile definire metodi statici o di istanza, proprietà, implementazioni di interfacce, membri astratti, dichiarazioni di eventi e costruttori aggiuntivi. Le associazioni let e do non possono essere visualizzate in questa sezione. Poiché i membri possono essere aggiunti a un'ampia F# gamma di tipi, oltre alle classi, vengono illustrati in un argomento separato, ovvero [membri](./members/index.md).

## <a name="mutually-recursive-types"></a>Tipi ricorsivi reciproci

Quando si definiscono i tipi che fanno riferimento l'uno all'altro in modo circolare, è possibile stringere le definizioni `and` dei tipi usando la parola chiave. La `and` parola chiave sostituisce `type` la parola chiave su All eccetto la prima definizione, come indicato di seguito.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2404.fs)]

L'output è un elenco di tutti i file nella directory corrente.

## <a name="when-to-use-classes-unions-records-and-structures"></a>Quando utilizzare classi, unioni, record e strutture

Data la varietà di tipi tra cui scegliere, è necessario avere una conoscenza approfondita di ciò che ciascun tipo è progettato per selezionare il tipo appropriato per una particolare situazione. Le classi sono progettate per essere usate nei contesti di programmazione orientata a oggetti. La programmazione orientata a oggetti è il paradigma principale utilizzato nelle applicazioni scritte per il .NET Framework. Se il F# codice deve collaborare strettamente con la .NET Framework o un'altra libreria orientata a oggetti e, soprattutto se è necessario estendere da un sistema di tipi orientato a oggetti, ad esempio una libreria dell'interfaccia utente, le classi sono probabilmente appropriate.

Se non si interagisce strettamente con il codice orientato a oggetti o se si sta scrivendo codice indipendente e pertanto protetto da interazioni frequenti con codice orientato a oggetti, è consigliabile utilizzare record e unioni discriminate. Un'unione discriminata unica, ben concepita, insieme al codice appropriato per i criteri di ricerca, può essere spesso utilizzata come alternativa più semplice a una gerarchia di oggetti. Per altre informazioni sulle unioni discriminate, vedere [unioni discriminate](discriminated-unions.md).

I record hanno il vantaggio di essere più semplici delle classi, ma i record non sono appropriati quando le richieste di un tipo superano ciò che può essere ottenuto con la loro semplicità. I record sono essenzialmente semplici aggregazioni di valori, senza costruttori distinti che possono eseguire azioni personalizzate, senza campi nascosti e senza implementazioni di ereditarietà o di interfaccia. Sebbene i membri come proprietà e metodi possano essere aggiunti ai record per rendere il loro comportamento più complesso, i campi archiviati in un record sono ancora una semplice aggregazione di valori. Per ulteriori informazioni sui record, vedere [record](records.md).

Le strutture sono utili anche per piccole aggregazioni di dati, ma si differenziano dalle classi e dai record in quanto sono tipi di valore .NET. Le classi e i record sono tipi di riferimento .NET. La semantica dei tipi di valore e i tipi di riferimento sono diversi in quanto i tipi di valore vengono passati per valore. Ciò significa che vengono copiati bit per bit quando vengono passati come parametro o restituiti da una funzione. Vengono inoltre archiviati nello stack o, se vengono utilizzati come campo, incorporati all'interno dell'oggetto padre anziché archiviati nella propria posizione separata nell'heap. Pertanto, le strutture sono appropriate per i dati a cui si accede di frequente quando l'overhead di accesso all'heap costituisce un problema. Per ulteriori informazioni sulle strutture, vedere [strutture](structures.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Membri](./members/index.md)
- [Ereditarietà](inheritance.md)
- [Interfacce](interfaces.md)
