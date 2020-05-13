---
title: Linee guida per la progettazione dei componenti F#
description: "Informazioni sulle linee guida per la scrittura di componenti F # destinati all'utilizzo da parte di altri chiamanti."
ms.date: 05/14/2018
ms.openlocfilehash: 590bda0660d54ea73c590d31e694f3d499e0fd9f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209136"
---
# <a name="f-component-design-guidelines"></a>Linee guida per la progettazione dei componenti F#

Questo documento è un set di linee guida di progettazione di componenti per la programmazione F #, basate sulle linee guida di progettazione dei componenti F #, V14, Microsoft Research e una versione che è stata originariamente curata e gestita da F # Software Foundation.

In questo documento si presuppone che l'utente abbia familiarità con la programmazione F #. Molti ringraziano la community di F # per i loro contributi e commenti e suggerimenti utili su diverse versioni di questa guida.

## <a name="overview"></a>Panoramica

In questo documento vengono esaminati alcuni problemi relativi alla progettazione e alla codifica dei componenti F #. Un componente può indicare uno dei seguenti elementi:

* Livello nel progetto F # con consumer esterni all'interno del progetto.
* Libreria destinata all'utilizzo da parte del codice F # tra i limiti dell'assembly.
* Libreria destinata all'utilizzo da parte di qualsiasi linguaggio .NET tra i confini degli assembly.
* Libreria destinata alla distribuzione tramite un repository di pacchetti, ad esempio [NuGet](https://nuget.org).

Le tecniche descritte in questo articolo seguono i [cinque principi del codice F # valido](index.md#five-principles-of-good-f-code)e quindi utilizzano la programmazione funzionale e di oggetti in base alle esigenze.

Indipendentemente dalla metodologia, la finestra di progettazione di componenti e librerie affronta una serie di problemi pratici e prosaici quando si tenta di creare un'API più facilmente utilizzabile dagli sviluppatori. L'applicazione coscienziosa delle [linee guida di progettazione della libreria .NET](../../standard/design-guidelines/index.md) consentirà di creare un set coerente di API gradevoli da utilizzare.

## <a name="general-guidelines"></a>Linee guida generali

Esistono alcune linee guida universali valide per le librerie F #, a prescindere dai destinatari della libreria.

### <a name="learn-the-net-library-design-guidelines"></a>Informazioni sulle linee guida di progettazione della libreria .NET

Indipendentemente dal tipo di codice F #, è importante avere una conoscenza pratica delle [linee guida di progettazione delle librerie .NET](../../standard/design-guidelines/index.md). La maggior parte degli altri programmatori F # e .NET avrà una certa familiarità con queste linee guida e prevede che il codice .NET sia conforme.

Le linee guida per la progettazione di librerie .NET forniscono indicazioni generali sulla denominazione, sulla progettazione di classi e interfacce, sulla progettazione di membri (proprietà, metodi, eventi e così via), oltre a un primo punto di riferimento utile per un'ampia gamma di linee guida di progettazione.

### <a name="add-xml-documentation-comments-to-your-code"></a>Aggiungere commenti alla documentazione XML al codice

La documentazione XML sulle API pubbliche garantisce che gli utenti possano ottenere IntelliSense e informazioni rapide eccezionali quando usano questi tipi e membri e abilitare la compilazione di file di documentazione per la libreria. Vedere la [documentazione XML](../language-reference/xml-documentation.md) sui diversi tag XML che possono essere usati per markup aggiuntivi nei commenti xmldoc.

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo: otherPoint:Point -> float
```

È possibile utilizzare i commenti XML in formato breve ( `/// comment` ) o i commenti XML standard ( `///<summary>comment</summary>` ).

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a>Prendere in considerazione l'uso di file di firma espliciti (con estensione FSI) per le API di librerie e componenti

L'uso di file di firme esplicite in una libreria F # fornisce un riepilogo conciso dell'API pubblica, che consente di ottenere informazioni sulla superficie pubblica completa della libreria e fornisce una netta separazione tra la documentazione pubblica e i dettagli di implementazione interna. I file delle firme aggiungono un attrito alla modifica dell'API pubblica, richiedendo modifiche da apportare nei file di implementazione e di firma. Di conseguenza, i file della firma devono essere in genere introdotti solo quando un'API diventa solidificata e non è più prevista una modifica significativa.

### <a name="always-follow-best-practices-for-using-strings-in-net"></a>Seguire sempre le procedure consigliate per l'uso di stringhe in .NET

Seguire le procedure consigliate [per l'uso delle stringhe nelle linee guida di .NET](../../standard/base-types/best-practices-strings.md) . In particolare, si dichiara sempre in modo esplicito *finalità culturali* nella conversione e nel confronto delle stringhe (se applicabile).

## <a name="guidelines-for-f-facing-libraries"></a>Linee guida per le librerie F #

Questa sezione presenta i consigli per lo sviluppo di librerie F # pubbliche. ovvero le librerie che espongono le API pubbliche destinate a essere utilizzate dagli sviluppatori F #. Esistono diverse raccomandazioni per la progettazione di librerie applicabili in modo specifico a F #. In assenza di raccomandazioni specifiche che seguono, le linee guida per la progettazione di librerie .NET sono le linee guida di fallback.

### <a name="naming-conventions"></a>Convenzioni di denominazione

#### <a name="use-net-naming-and-capitalization-conventions"></a>Usare le convenzioni di denominazione e di capitalizzazione .NET

La tabella seguente segue le convenzioni di denominazione e di maiuscole e minuscole .NET. Sono disponibili piccole aggiunte per includere anche costrutti F #.

| Costrutto | Caso | Parte | Esempi | Note |
|-----------|------|------|----------|-------|
| Tipi concreti | PascalCase | Sostantivo/aggettivo | Elenco, doppio, complesso | I tipi concreti sono struct, classi, enumerazioni, delegati, record e unioni. Anche se i nomi dei tipi sono tradizionalmente minuscoli in OCaml, F # ha adottato lo schema di denominazione .NET per i tipi.
| DLL           | PascalCase |                 | Fabrikam. Core. dll |  |
| Tag Union     | PascalCase | Sostantivo | Alcuni, Aggiungi, esito positivo | Non usare un prefisso nelle API pubbliche. Usare facoltativamente un prefisso quando è interno, ad esempio`type Teams = TAlpha | TBeta | TDelta.` |
| Event          | PascalCase | Verbo | ValueChanged/ValueChanging |  |
| Eccezioni     | PascalCase |      | WebException | Il nome deve terminare con "Exception". |
| Campo          | PascalCase | Sostantivo | Currentname  | |
| Tipi interfaccia |  PascalCase | Sostantivo/aggettivo | IDisposable | Il nome deve iniziare con "I". |
| Metodo |  PascalCase |  Verbo | ToString | |
| Spazio dei nomi | PascalCase | | Microsoft. FSharp. Core | Utilizzare in genere `<Organization>.<Technology>[.<Subnamespace>]` , anche se eliminare l'organizzazione se la tecnologia è indipendente dall'organizzazione. |
| Parametri | camelCase | Sostantivo |  typeName, Transform, intervallo | |
| valori Let (interni) | camelCase o PascalCase | Sostantivo/verbo |  getValue, MyTable |
| valori Let (External) | camelCase o PascalCase | Sostantivo/verbo  | List. map, dates. Today | i valori associati a Let sono spesso pubblici quando si seguono modelli di progettazione funzionali tradizionali. Tuttavia, in genere si usa PascalCase quando l'identificatore può essere usato da altri linguaggi .NET. |
| Proprietà  | PascalCase  | Sostantivo/aggettivo  | IsEndOfFile, backcolor  | Le proprietà booleane in genere usano e possono e devono essere affermativa, come in IsEndOfFile, non in IsNotEndOfFile.

#### <a name="avoid-abbreviations"></a>Evitare abbreviazioni

Le linee guida di .NET scoraggiano l'uso delle abbreviazioni (ad esempio, "use `OnButtonClick` anziché `OnBtnClick` "). Sono tollerate abbreviazioni comuni, ad esempio `Async` per "asincrono". Questa guida viene talvolta ignorata per la programmazione funzionale; USA, ad esempio, `List.iter` un'abbreviazione per "iterare". Per questo motivo, l'uso delle abbreviazioni tende a essere tollerato a un livello superiore nella programmazione F #-to-F #, ma in genere dovrebbe comunque essere evitato nella progettazione di componenti pubblici.

#### <a name="avoid-casing-name-collisions"></a>Evitare conflitti di nomi di maiuscole e minuscole

Le linee guida di .NET indicano che non è possibile usare solo la combinazione di maiuscole e minuscole per evitare ambiguità nei conflitti di nomi, poiché alcune lingue client, ad esempio Visual Basic, non fanno distinzione tra maiuscole e minuscole.

#### <a name="use-acronyms-where-appropriate"></a>Usare gli acronimi laddove appropriato

Gli acronimi come XML non sono abbreviazioni e sono ampiamente usati nelle librerie .NET in formato senza maiuscole (XML). Devono essere usati solo gli acronimi noti e ampiamente riconosciuti.

#### <a name="use-pascalcase-for-generic-parameter-names"></a>Usare PascalCase per i nomi dei parametri generici

Usare PascalCase per i nomi di parametro generici nelle API pubbliche, incluse le librerie con rivolte a F #. In particolare, usare nomi come `T` , `U` , `T1` , `T2` per i parametri generici arbitrari e quando i nomi specifici hanno senso, quindi per le librerie con rivolte a F # usare nomi come `Key` , `Value` , `Arg` (ma non ad esempio, `TKey` ).

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a>Usare PascalCase o camelCase per le funzioni e i valori pubblici nei moduli F #

camelCase viene usato per le funzioni pubbliche progettate per essere usate non qualificate (ad esempio, `invalidArg` ) e per "funzioni di raccolta standard" (ad esempio, List. map). In entrambi i casi, i nomi di funzione agiscono in modo analogo alle parole chiave del linguaggio.

### <a name="object-type-and-module-design"></a>Progettazione di oggetti, tipi e moduli

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a>Usare spazi dei nomi o moduli per contenere tipi e moduli

Ogni file F # in un componente deve iniziare con una dichiarazione dello spazio dei nomi o con una dichiarazione del modulo.

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

oppure

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

Le differenze tra l'utilizzo di moduli e spazi dei nomi per organizzare il codice al primo livello sono le seguenti:

* Gli spazi dei nomi possono estendersi su più file
* Gli spazi dei nomi non possono contenere funzioni F # a meno che non si trovino all'interno di un modulo interno
* Il codice per qualsiasi modulo specificato deve essere contenuto in un singolo file
* I moduli di livello superiore possono contenere funzioni F # senza la necessità di un modulo interno

La scelta tra uno spazio dei nomi o un modulo di primo livello influisce sulla forma compilata del codice e pertanto influirà sulla visualizzazione di altri linguaggi .NET se l'API viene utilizzata all'esterno del codice F #.

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a>Usare i metodi e le proprietà per le operazioni intrinseche ai tipi di oggetto

Quando si utilizzano gli oggetti, è consigliabile assicurarsi che la funzionalità utilizzabile venga implementata come metodi e proprietà su tale tipo.

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

La maggior parte delle funzionalità per un determinato membro non deve necessariamente essere implementata in quel membro, ma la parte utilizzabile di tale funzionalità dovrebbe essere.

#### <a name="use-classes-to-encapsulate-mutable-state"></a>Usare classi per incapsulare lo stato modificabile

In F #, questa operazione deve essere eseguita solo se lo stato non è già incapsulato da un altro costrutto di linguaggio, ad esempio una chiusura, un'espressione di sequenza o un calcolo asincrono.

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a>Usare le interfacce per raggruppare le operazioni correlate

Usare i tipi di interfaccia per rappresentare un set di operazioni. Questa operazione è preferibile ad altre opzioni, ad esempio tuple di funzioni o record di funzioni.

```fsharp
type Serializer =
    abstract Serialize<'T>: preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T>: preserveRefEq: bool -> pickle: string -> 'T
```

Preferenza per:

```fsharp
type Serializer<'T> = {
    Serialize: bool -> 'T -> string
    Deserialize: bool -> string -> 'T
}
```

Le interfacce sono concetti di primo livello in .NET, che è possibile usare per ottenere i risultati di funtori in genere. Inoltre, possono essere usati per codificare i tipi esistenziali nel programma, che non possono essere registrati nelle funzioni.

#### <a name="use-a-module-to-group-functions-that-act-on-collections"></a>Usare un modulo per raggruppare le funzioni che agiscono sulle raccolte

Quando si definisce un tipo di raccolta, è consigliabile fornire un set standard di operazioni come `CollectionType.map` e `CollectionType.iter` ) per i nuovi tipi di raccolta.

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

Se si include tale modulo, seguire le convenzioni di denominazione standard per le funzioni disponibili in FSharp. Core.

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a>Usare un modulo per raggruppare le funzioni per funzioni canoniche comuni, soprattutto nelle librerie matematiche e DSL

Ad esempio, `Microsoft.FSharp.Core.Operators` è una raccolta aperta automaticamente di funzioni di primo livello (ad esempio `abs` e `sin` ) fornita da FSharp. Core. dll.

Analogamente, una libreria di statistiche può includere un modulo con funzioni `erf` e `erfc` , in cui questo modulo è progettato per essere aperto in modo esplicito o automatico.

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a>Prendere in considerazione l'uso di RequireQualifiedAccess e applicare con attenzione gli attributi di apertura

L'aggiunta dell' `[<RequireQualifiedAccess>]` attributo a un modulo indica che il modulo potrebbe non essere aperto e che i riferimenti agli elementi del modulo richiedono un accesso qualificato esplicito. Ad esempio, il `Microsoft.FSharp.Collections.List` modulo dispone di questo attributo.

Questa operazione è utile quando le funzioni e i valori nel modulo hanno nomi che probabilmente sono in conflitto con i nomi in altri moduli. La richiesta di accesso qualificato può aumentare significativamente la gestibilità a lungo termine e la evolvibilità di una libreria.

L'aggiunta dell' `[<AutoOpen>]` attributo a un modulo indica che il modulo verrà aperto quando lo spazio dei nomi contenitore viene aperto. L' `[<AutoOpen>]` attributo può essere applicato anche a un assembly per indicare un modulo che viene aperto automaticamente quando si fa riferimento all'assembly.

Una raccolta di statistiche **MathsHeaven. Statistics** , ad esempio, potrebbe contenere `module MathsHeaven.Statistics.Operators` `erf` le funzioni e `erfc` . È ragionevole contrassegnare questo modulo come `[<AutoOpen>]` . Ciò significa `open MathsHeaven.Statistics` che aprirà anche questo modulo e riporterà i nomi `erf` e l' `erfc` ambito. Un altro valido utilizzo di `[<AutoOpen>]` è per i moduli che contengono metodi di estensione.

L'utilizzo eccessivo di `[<AutoOpen>]` lead per gli spazi dei nomi inquinati e l'attributo deve essere utilizzato con cautela. Per librerie specifiche in domini specifici, l'uso oculato di `[<AutoOpen>]` può condurre a una migliore usabilità.

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a>Prendere in considerazione la definizione dei membri dell'operatore nelle classi in cui l'utilizzo di operatori noti è appropriato

A volte le classi vengono usate per modellare costrutti matematici, ad esempio vettori. Quando il dominio da modellare dispone di operatori noti, la relativa definizione come membri intrinseci alla classe è utile.

```fsharp
type Vector(x: float) =

    member v.X = x

    static member (*) (vector: Vector, scalar: float) = Vector(vector.X * scalar)

    static member (+) (vector1: Vector, vector2: Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

Questa guida corrisponde alle linee guida generali di .NET per questi tipi. Tuttavia, può essere importante anche nel codice F # perché consente l'uso di questi tipi insieme a funzioni e metodi F # con vincoli di membro, ad esempio List. sumBy.

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a>Provare a usare Compiled per fornire un oggetto. Nome descrittivo di rete per altri consumer di linguaggio .NET

In alcuni casi può essere utile assegnare un nome a un elemento in uno stile per i consumer F # (ad esempio un membro statico in lettere minuscole, in modo che venga visualizzato come se fosse una funzione associata al modulo), ma abbia uno stile diverso per il nome quando viene compilato in un assembly. È possibile utilizzare l' `[<CompiledName>]` attributo per fornire uno stile diverso per l'utilizzo dell'assembly da parte del codice non F #.

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

Utilizzando `[<CompiledName>]` , è possibile utilizzare le convenzioni di denominazione .NET per i consumer non F # dell'assembly.

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a>Usare l'overload del metodo per le funzioni membro, se questa operazione fornisce un'API più semplice

L'overload dei metodi è uno strumento potente per semplificare un'API che potrebbe dover eseguire funzionalità simili, ma con opzioni o argomenti diversi.

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

In F # è più comune eseguire l'overload su un numero di argomenti anziché sui tipi di argomenti.

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a>Nascondere le rappresentazioni dei tipi di record e di Unione se è probabile che la progettazione di questi tipi evolva

Evitare di rivelare rappresentazioni concrete di oggetti. La rappresentazione concreta dei valori, ad esempio, <xref:System.DateTime> non viene rivelata dall'API esterna e pubblica della progettazione della libreria .NET. In fase di esecuzione, Common Language Runtime conosce l'implementazione di cui è stato eseguito il commit che verrà usata durante l'esecuzione. Tuttavia, il codice compilato non acquisisce dipendenze dalla rappresentazione concreta.

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a>Evitare l'utilizzo dell'ereditarietà dell'implementazione per l'estendibilità

In F # l'ereditarietà dell'implementazione viene utilizzata raramente. Inoltre, le gerarchie di ereditarietà sono spesso complesse e difficili da modificare quando arrivano nuovi requisiti. L'implementazione dell'ereditarietà è ancora presente in F # per la compatibilità e rari casi in cui è la soluzione migliore a un problema, ma è necessario cercare tecniche alternative nei programmi F # quando si progetta per il polimorfismo, ad esempio l'implementazione dell'interfaccia.

### <a name="function-and-member-signatures"></a>Firme di funzioni e membri

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a>Utilizzare le tuple per i valori restituiti quando viene restituito un numero ridotto di più valori non correlati

Di seguito è riportato un esempio di utilizzo di una tupla in un tipo restituito:

```fsharp
val divrem: BigInteger -> BigInteger -> BigInteger * BigInteger
```

Per i tipi restituiti che contengono molti componenti o per i quali i componenti sono correlati a una singola entità identificabile, provare a usare un tipo denominato anziché una tupla.

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a>Usare `Async<T>` per la programmazione asincrona nei limiti dell'API F #

Se è presente un'operazione sincrona corrispondente denominata `Operation` che restituisce un `T` , l'operazione asincrona deve essere denominata `AsyncOperation` se restituisce `Async<T>` o se restituisce `OperationAsync` `Task<T>` . Per i tipi .NET comunemente usati che espongono i metodi Begin/End, provare `Async.FromBeginEnd` a usare per scrivere i metodi di estensione come facciata per fornire il modello di programmazione asincrona F # alle API .NET.

```fsharp
type SomeType =
    member this.Compute(x:int): int =
        ...
    member this.AsyncCompute(x:int): Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a>Eccezioni

Per informazioni sull'uso appropriato di eccezioni, risultati e opzioni, vedere [gestione degli errori](conventions.md#error-management) .

### <a name="extension-members"></a>Membri di estensione

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a>Applicare con attenzione i membri di estensione F # nei componenti F #-to-F #

I membri di estensione F # in genere devono essere usati solo per le operazioni che si trovano nella chiusura di operazioni intrinseche associate a un tipo nella maggior parte delle modalità d'uso. Un uso comune è quello di fornire API più idiomatiche a F # per diversi tipi .NET:

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a>Tipi di Unione

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a>Usare unioni discriminate anziché gerarchie di classi per i dati strutturati ad albero

Le strutture di tipo albero sono definite in modo ricorsivo. Questa operazione è imbarazzante con l'ereditarietà, ma è elegante con le unioni discriminate.

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

La rappresentazione di dati di tipo albero con unioni discriminate consente inoltre di trarre vantaggio dalla completezza dei criteri di ricerca.

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a>Utilizzare `[<RequireQualifiedAccess>]` sui tipi unione i cui nomi case non sono sufficientemente univoci

È possibile che si trovi in un dominio in cui lo stesso nome è il nome migliore per diversi elementi, ad esempio i case di Unione discriminati. È possibile utilizzare `[<RequireQualifiedAccess>]` per evitare ambiguità nei nomi dei case al fine di evitare l'attivazione di errori di confusione dovuti all'ombreggiatura dipendente dall'ordinamento delle `open` istruzioni

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a>Nascondere le rappresentazioni delle unioni discriminate per le API binarie compatibili se è probabile che la progettazione di questi tipi evolva

I tipi di Unione si basano sui moduli di corrispondenza dei modelli F # per un modello di programmazione conciso. Come indicato in precedenza, è consigliabile evitare di rivelare rappresentazioni di dati concreti se è probabile che la progettazione di questi tipi si evolva.

La rappresentazione di un'unione discriminata, ad esempio, può essere nascosta utilizzando una dichiarazione privata o interna oppure utilizzando un file di firma.

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

Se si rivelano le unioni discriminate in modo indiscriminato, potrebbe risultare difficile eseguire la versione della libreria senza interruzioni del codice utente. In alternativa, considerare la possibilità di rivelare uno o più criteri attivi per consentire la corrispondenza dei criteri con i valori del tipo.

I criteri attivi forniscono un metodo alternativo per fornire agli utenti F # i criteri di ricerca, evitando di esporre direttamente i tipi di Unione F #.

### <a name="inline-functions-and-member-constraints"></a>Funzioni inline e vincoli del membro

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a>Definire algoritmi numerici generici usando funzioni inline con vincoli di membri impliciti e tipi generici risolti in modo statico

I vincoli dei membri aritmetici e i vincoli di confronto F # sono uno standard per la programmazione F #. Si consideri il codice di esempio seguente:

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

Il tipo di questa funzione è il seguente:

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

Si tratta di una funzione adatta per un'API pubblica in una libreria matematica.

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a>Evitare di usare vincoli di membro per simulare classi di tipi e tipi Duck

È possibile simulare "Duck Typing" con i vincoli del membro F #. Tuttavia, i membri che utilizzano questa operazione non devono essere in genere utilizzati nelle progettazioni della libreria F # a F #. Ciò è dovuto al fatto che le progettazioni di librerie basate su vincoli impliciti non noti o non standard tendono a impedire che il codice utente diventi non flessibile e associato a un modello di Framework specifico.

Inoltre, è probabile che l'utilizzo intensivo di vincoli di membri in questo modo possa causare tempi di compilazione molto lunghi.

### <a name="operator-definitions"></a>Definizioni degli operatori

#### <a name="avoid-defining-custom-symbolic-operators"></a>Evitare di definire operatori simbolici personalizzati

Gli operatori personalizzati sono essenziali in alcune situazioni e sono dispositivi di notazione estremamente utili all'interno di un grande corpo di codice di implementazione. Per i nuovi utenti di una libreria, le funzioni denominate sono spesso più facili da usare. Gli operatori simbolici personalizzati, inoltre, possono essere difficili da documentare, mentre gli utenti trovano più difficile individuare la guida sugli operatori, a causa delle limitazioni esistenti nei motori IDE e di ricerca.

Di conseguenza, è preferibile pubblicare le funzionalità come funzioni e membri denominati, nonché esporre gli operatori per questa funzionalità solo se i vantaggi della notazione superano la documentazione e il costo cognitivo per la loro presenza.

### <a name="units-of-measure"></a>Unità di misura

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a>Usare con attenzione le unità di misura per la sicurezza dei tipi aggiuntiva nel codice F #

Le informazioni di tipizzazione aggiuntive per le unità di misura vengono cancellate se visualizzate da altri linguaggi .NET. Tenere presente che i componenti, gli strumenti e la reflection .NET vedranno i tipi-sans-units. Ad esempio, i consumer C# vedranno `float` invece di `float<kg>` .

### <a name="type-abbreviations"></a>Abbreviazioni dei tipi

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a>Usare con attenzione le abbreviazioni di tipo per semplificare il codice F #

I componenti .NET, gli strumenti e la reflection non visualizzeranno nomi abbreviati per i tipi. Un uso significativo delle abbreviazioni di tipo può anche rendere un dominio più complesso rispetto al fatto, che può confondere i consumer.

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a>Evitare abbreviazioni di tipo per i tipi pubblici i cui membri e proprietà devono essere intrinsecamente diversi da quelli disponibili sul tipo abbreviato

In questo caso, il tipo abbreviato rivela troppo la rappresentazione del tipo effettivo definito. In alternativa, è consigliabile eseguire il wrapping dell'abbreviazione in un tipo di classe o in un'unione discriminata a singolo caso oppure, quando le prestazioni sono essenziali, è consigliabile usare un tipo di struct per eseguire il wrapping dell'abbreviazione.

Ad esempio, si tenta di definire una mappa multimappa come caso speciale di una mappa F #, ad esempio:

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

Tuttavia, le operazioni logiche per la notazione del punto su questo tipo non sono le stesse delle operazioni su una mappa. ad esempio, è ragionevole che l'operatore di ricerca esegue il mapping. [key] restituisce l'elenco vuoto se la chiave non è presente nel dizionario, anziché generare un'eccezione.

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a>Linee guida per le librerie da usare con altri linguaggi .NET

Quando si progettano le librerie per l'uso da altri linguaggi .NET, è importante attenersi alle [linee guida di progettazione della libreria .NET](../../standard/design-guidelines/index.md). In questo documento, queste librerie sono etichettate come librerie .NET Vanilla, a differenza delle librerie con rivolte a F # che usano costrutti F # senza restrizioni. La progettazione di librerie .NET Vanilla significa fornire API Note e idiomatiche coerenti con il resto del .NET Framework riducendo al minimo l'uso di costrutti specifici di F # nell'API pubblica. Le regole sono illustrate nelle sezioni seguenti.

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a>Progettazione dello spazio dei nomi e del tipo (per le librerie da usare con altri linguaggi .NET)

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a>Applicare le convenzioni di denominazione .NET all'API pubblica dei componenti

Prestare particolare attenzione all'uso di nomi abbreviati e alle linee guida per la capitalizzazione di .NET.

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a>Usare spazi dei nomi, tipi e membri come struttura organizzativa primaria per i componenti

Tutti i file contenenti funzionalità pubbliche devono iniziare con una `namespace` dichiarazione e le uniche entità pubbliche negli spazi dei nomi devono essere tipi. Non usare i moduli F #.

Usare moduli non pubblici per mantenere il codice di implementazione, i tipi di utilità e le funzioni di utilità.

I tipi statici dovrebbero essere preferiti rispetto ai moduli, perché consentono l'evoluzione futura dell'API per l'uso dell'overload e di altri concetti di progettazione dell'API .NET che non possono essere usati nei moduli F #.

Ad esempio, al posto della seguente API pubblica:

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

In alternativa, prendere in considerazione:

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a>Usare i tipi di record F # nelle API Vanilla .NET se la progettazione dei tipi non evolverà

I tipi di record F # vengono compilati in una semplice classe .NET. Questi sono adatti per alcuni tipi semplici e stabili nelle API. Provare a usare `[<NoEquality>]` gli `[<NoComparison>]` attributi e per disattivare la generazione automatica di interfacce. Evitare inoltre di usare campi di record modificabili nelle API Vanilla .NET perché espongono un campo pubblico. Considerare sempre se una classe fornisce un'opzione più flessibile per l'evoluzione futura dell'API.

Il codice F # seguente, ad esempio, espone l'API pubblica a un consumer C#:

F#:

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing: int
        SecondThing: string }
```

C#:

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a>Nascondere la rappresentazione di tipi di Unione F # nelle API Vanilla .NET

I tipi di Unione f # non vengono comunemente usati tra i limiti dei componenti, anche per la codifica F #-to-F #. Si tratta di un dispositivo di implementazione eccellente se usato internamente all'interno di componenti e librerie.

Quando si progetta un'API Vanilla .NET, è consigliabile nascondere la rappresentazione di un tipo di Unione usando una dichiarazione privata o un file di firma.

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

È anche possibile aumentare i tipi che usano internamente una rappresentazione di Unione con i membri per fornire un oggetto desiderato. API per il NET.

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True

    /// A public member for use from C#
    member x.Evaluate =
        match x with
        | And(a,b) -> a.Evaluate && b.Evaluate
        | Not a -> not a.Evaluate
        | True -> true

    /// A public member for use from C#
    static member CreateAnd(a,b) = And(a,b)
```

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a>Progettare GUI e altri componenti usando i modelli di progettazione del Framework

In .NET sono disponibili molti Framework diversi, ad esempio WinForms, WPF e ASP.NET. Quando si progettano componenti da usare in questi Framework, è consigliabile usare le convenzioni di denominazione e progettazione per ciascuna di esse. Per la programmazione WPF, ad esempio, adottare modelli di progettazione WPF per le classi in corso di progettazione. Per i modelli nella programmazione dell'interfaccia utente, usare modelli di progettazione quali eventi e raccolte basate su notifiche, ad esempio quelli disponibili in <xref:System.Collections.ObjectModel> .

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a>Progettazione di oggetti e membri (per le librerie da usare con altri linguaggi .NET)

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a>Usare l'attributo CLIEvent (per esporre gli eventi .NET

Costruire un `DelegateEvent` oggetto con un tipo delegato .NET specifico che accetta un oggetto e `EventArgs` , anziché un oggetto `Event` , che usa semplicemente il `FSharpHandler` tipo per impostazione predefinita, in modo che gli eventi vengano pubblicati in modo familiare in altri linguaggi .NET.

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x: int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-that-return-net-tasks"></a>Esporre le operazioni asincrone come metodi che restituiscono attività .NET

Le attività vengono usate in .NET per rappresentare i calcoli asincroni attivi. Le attività sono in genere meno composizionali rispetto `Async<T>` agli oggetti F #, perché rappresentano attività "già in esecuzione" e non possono essere composte insieme in modi che eseguono la composizione parallela o che nascondono la propagazione dei segnali di annullamento e altri parametri contestuali.

Tuttavia, nonostante questo, i metodi che restituiscono attività sono la rappresentazione standard della programmazione asincrona in .NET.

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int): Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

Si vorrà spesso accettare anche un token di annullamento esplicito:

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x: int): Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a>Usare i tipi di delegato .NET anziché i tipi di funzione F #

Qui "i tipi di funzione F #" significano "Arrow", ad esempio `int -> int` .

Anziché:

```fsharp
member this.Transform(f: int->int) =
    ...
```

Eseguire questa operazione:

```fsharp
member this.Transform(f: Func<int,int>) =
    ...
```

Il tipo di funzione F # appare come `class FSharpFunc<T,U>` ad altri linguaggi .NET ed è meno adatto per le funzionalità del linguaggio e gli strumenti che comprendono i tipi delegati. Quando si crea un metodo di ordine superiore destinato a .NET Framework 3,5 o superiore, i `System.Func` `System.Action` delegati e sono le API appropriate per la pubblicazione per consentire agli sviluppatori .NET di utilizzare tali API in modo insufficiente. Quando la destinazione è .NET Framework 2,0, i tipi delegati definiti dal sistema sono più limitati. provare a usare tipi delegati predefiniti, ad esempio `System.Converter<T,U>` o a definire un tipo delegato specifico.

Sul lato flip, i delegati .NET non sono naturali per le librerie con rivolto a F # (vedere la sezione successiva sulle librerie F #). Di conseguenza, una strategia di implementazione comune quando si sviluppano metodi di ordine superiore per le librerie Vanilla .NET consiste nel creare tutte le implementazioni usando i tipi di funzione F #, quindi creare l'API pubblica usando i delegati come facciata sottile sopra l'effettiva implementazione di F #.

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a>Usare il modello TryGetValue anziché restituire i valori delle opzioni F # e preferire l'overload del metodo per accettare i valori delle opzioni F # come argomenti

I modelli comuni di utilizzo per il tipo di opzione F # nelle API sono implementati in modo migliore nelle API Vanilla .NET utilizzando le tecniche standard di progettazione .NET. Anziché restituire un valore di opzione F #, provare a usare il tipo restituito bool più un parametro out come nel modello "TryGetValue". Anziché accettare i valori delle opzioni F # come parametri, è consigliabile usare l'overload del metodo o gli argomenti facoltativi.

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal: byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x: int, y: int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x: int) = x

member this.ParamOverload(x: int, y: int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a>Usare i tipi di interfaccia di raccolta .NET della \< chiave IEnumerable T \> e IDictionary \< , il valore \> per i parametri e i valori restituiti

Evitare l'uso di tipi di raccolta concreti, ad esempio matrici .NET `T[]` , tipi F # `list<T>` `Map<Key,Value>` e `Set<T>` tipi di raccolta concreti .NET, ad esempio `Dictionary<Key,Value>` . Le linee guida per la progettazione di librerie .NET offrono consigli utili per l'utilizzo di diversi tipi di raccolta, ad esempio `IEnumerable<T>` . In alcune circostanze, l'utilizzo di matrici ( `T[]` ) è accettabile in base alle prestazioni. Si noti in particolare che `seq<T>` è solo l'alias F # per `IEnumerable<T>` e quindi seq è spesso un tipo appropriato per un'API Vanilla .NET.

Anziché gli elenchi F #:

```fsharp
member this.PrintNames(names: string list) =
    ...
```

USA sequenze F #:

```fsharp
member this.PrintNames(names: seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a>Usare il tipo di unità come unico tipo di input di un metodo per definire un metodo di argomento zero o come unico tipo restituito per definire un metodo che restituisce void

Evitare altri usi del tipo di unità. Questi sono i seguenti:

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x: int) = ()
```

Questa operazione non è valida:

```fsharp
member this.WrongUnit( x: unit, z: int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a>Verificare la presenza di valori null nei limiti dell'API Vanilla .NET

Il codice di implementazione F # tende a avere un minor numero di valori null, a causa di modelli di progettazione non modificabili e di restrizioni sull'uso di valori letterali null per i tipi F #. Altri linguaggi .NET spesso utilizzano null come valore molto più spesso. Per questo motivo, il codice F # che sta esponendo un'API .NET Vanilla deve controllare i parametri per i valori null al limite dell'API e impedire che tali valori vengano propagati in modo più approfondito nel codice di implementazione F #. `isNull`È possibile usare la funzione o i criteri di ricerca per il `null` modello.

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a>Evitare di usare le tuple come valori restituiti

È invece preferibile restituire un tipo denominato che contiene i dati di aggregazione oppure utilizzare parametri out per restituire più valori. Sebbene le tuple e le tuple di struct esistano in .NET (incluso il supporto del linguaggio C# per le tuple struct), spesso non forniscono l'API ideale e prevista per gli sviluppatori .NET.

#### <a name="avoid-the-use-of-currying-of-parameters"></a>Evitare l'utilizzo del currying dei parametri

Usare invece le convenzioni di chiamata .NET `Method(arg1,arg2,…,argN)` .

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

Suggerimento: se si progettano le librerie per l'uso da qualsiasi linguaggio .NET, non esiste alcun sostituto per la programmazione di C# e Visual Basic sperimentale per garantire che le librerie "siano corrette" da questi linguaggi. È anche possibile usare strumenti come .NET Reflector e Visual Studio Visualizzatore oggetti per garantire che le librerie e la relativa documentazione vengano visualizzate come previsto per gli sviluppatori.

## <a name="appendix"></a>Appendice

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a>Esempio end-to-end di progettazione del codice F # per l'uso da parte di altri linguaggi .NET

Si consideri la classe seguente:

```fsharp
open System

type Point1(angle,radius) =
    new() = Point1(angle=0.0, radius=0.0)
    member x.Angle = angle
    member x.Radius = radius
    member x.Stretch(l) = Point1(angle=x.Angle, radius=x.Radius * l)
    member x.Warp(f) = Point1(angle=f(x.Angle), radius=x.Radius)
    static member Circle(n) =
        [ for i in 1..n -> Point1(angle=2.0*Math.PI/float(n), radius=1.0) ]
```

Il tipo F # derivato di questa classe è il seguente:

```fsharp
type Point1 =
    new : unit -> Point1
    new : angle:double * radius:double -> Point1
    static member Circle : n:int -> Point1 list
    member Stretch : l:double -> Point1
    member Warp : f:(double -> double) -> Point1
    member Angle : double
    member Radius : double
```

Esaminiamo il modo in cui questo tipo F # viene visualizzato in un programmatore usando un altro linguaggio .NET. Ad esempio, la "firma" di C# approssimata è la seguente:

```csharp
// C# signature for the unadjusted Point1 class
public class Point1
{
    public Point1();

    public Point1(double angle, double radius);

    public static Microsoft.FSharp.Collections.List<Point1> Circle(int count);

    public Point1 Stretch(double factor);

    public Point1 Warp(Microsoft.FSharp.Core.FastFunc<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

Ci sono alcuni aspetti importanti da notare sul modo in cui F # rappresenta i costrutti qui. Ad esempio:

* I metadati, ad esempio i nomi degli argomenti, sono stati conservati.

* I metodi F # che accettano due argomenti diventano metodi C# che accettano due argomenti.

* Funzioni ed elenchi diventano riferimenti ai tipi corrispondenti nella libreria F #.

Il codice seguente illustra come modificare il codice per tenere conto di questi elementi.

```fsharp
namespace SuperDuperFSharpLibrary.Types

type RadialPoint(angle:double, radius:double) =

    /// Return a point at the origin
    new() = RadialPoint(angle=0.0, radius=0.0)

    /// The angle to the point, from the x-axis
    member x.Angle = angle

    /// The distance to the point, from the origin
    member x.Radius = radius

    /// Return a new point, with radius multiplied by the given factor
    member x.Stretch(factor) =
        RadialPoint(angle=angle, radius=radius * factor)

    /// Return a new point, with angle transformed by the function
    member x.Warp(transform:Func<_,_>) =
        RadialPoint(angle=transform.Invoke angle, radius=radius)

    /// Return a sequence of points describing an approximate circle using
    /// the given count of points
    static member Circle(count) =
        seq { for i in 1..count ->
                RadialPoint(angle=2.0*Math.PI/float(count), radius=1.0) }
```

Il tipo F # derivato del codice è il seguente:

```fsharp
type RadialPoint =
    new : unit -> RadialPoint
    new : angle:double * radius:double -> RadialPoint
    static member Circle : count:int -> seq<RadialPoint>
    member Stretch : factor:double -> RadialPoint
    member Warp : transform:System.Func<double,double> -> RadialPoint
    member Angle : double
    member Radius : double
```

La firma C# è ora la seguente:

```csharp
public class RadialPoint
{
    public RadialPoint();

    public RadialPoint(double angle, double radius);

    public static System.Collections.Generic.IEnumerable<RadialPoint> Circle(int count);

    public RadialPoint Stretch(double factor);

    public RadialPoint Warp(System.Func<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

Le correzioni apportate per preparare questo tipo per l'uso come parte di una libreria Vanilla .NET sono le seguenti:

* Sono stati modificati diversi nomi: `Point1` , `n` , `l` e `f` sono diventati `RadialPoint` rispettivamente, `count` , `factor` e `transform` .

* È stato usato un tipo restituito di `seq<RadialPoint>` anziché `RadialPoint list` modificando una costruzione di un elenco usando `[ ... ]` la costruzione di una sequenza usando `IEnumerable<RadialPoint>` .

* Utilizzato il tipo delegato .NET `System.Func` anziché un tipo di funzione F #.

Questo rende molto più gradevole l'utilizzo nel codice C#.
