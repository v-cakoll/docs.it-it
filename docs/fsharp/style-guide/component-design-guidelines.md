---
title: Indicazioni per la progettazione di componente F#
description: Scopri le linee guida per la scrittura di componenti di F# destinati all'utilizzo da altri chiamanti.
ms.date: 05/14/2018
ms.openlocfilehash: 446cba0f810af9517b655ef5741ddf7a919676d5
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "43488287"
---
# <a name="f-component-design-guidelines"></a>Indicazioni per la progettazione di componente F#

Questo documento è un set di linee guida di progettazione di componenti per F# di programmazione, in base a F# componente linee guida di progettazione, v14, Microsoft Research, e [un'altra versione](https://fsharp.org/specs/component-design-guidelines/) originariamente curata e gestito da F# Software Foundation.

Questo documento presuppone che si abbia familiarità con la programmazione F#. Si ringraziano community di F# per i relativi contributi e commenti e suggerimenti utili su varie versioni di questa Guida.

## <a name="overview"></a>Panoramica

Vengono esaminati alcuni dei problemi relativi alla progettazione del componente F# e codifica. Un componente può significare che gli elementi seguenti:

* Un livello di progetto F# con utenti esterni all'interno di tale progetto.
* Una libreria destinata all'utilizzo tra limiti di assembly dal codice F#.
* Una libreria destinata all'utilizzo da qualsiasi linguaggio .NET attraverso i limiti di assembly.
* Una libreria destinata alla distribuzione tramite un repository dei pacchetti, ad esempio [NuGet](https://nuget.org).

Seguono le tecniche descritte in questo articolo il [cinque principi del buon codice F#](index.md#five-principles-of-good-f-code)e pertanto utilizzano entrambi funzionali e oggetti di programmazione come appropriato.

Indipendentemente dalla metodologia, la finestra di progettazione di componenti e la libreria deve affrontare alcuni problemi pratici e banale durante il tentativo di creare un'API più facilmente utilizzabile dagli sviluppatori. Attenta applicazione dei [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/index.md) verrà volgere è per la creazione di un set coerente di API che sono piacevole da utilizzare.

## <a name="general-guidelines"></a>Indicazioni generali

Esistono alcune indicazioni universali che si applicano a librerie F#, indipendentemente dal fatto i destinatari per la libreria.

### <a name="learn-the-net-library-design-guidelines"></a>Altre linee guida di progettazione di .NET della libreria

Indipendentemente dal tipo di F# codifica si sta eseguendo, è utile per avere una conoscenza del [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/index.md). La maggior parte delle altre F# e ai programmatori di .NET verranno avere familiarità con queste linee guida e prevede che il codice .NET di conformarsi a essi.

Linee guida di progettazione di .NET della libreria fornite indicazioni generali sulla denominazione, la progettazione di classi e interfacce, progettazione di membri (proprietà, metodi, eventi, e così via) e altro ancora e sono un utile punto prima di riferimento per un'ampia gamma di materiale sussidiario di progettazione.

### <a name="add-xml-documentation-comments-to-your-code"></a>Aggiungere commenti in formato documentazione XML nel codice

Documentazione XML nelle API pubbliche assicurarsi che gli utenti possono ottenere eccezionali Intellisense e informazioni rapide durante l'utilizzo di questi tipi e membri e Abilita creazione di documentazione dei file per la libreria. Vedere le [della documentazione XML](../language-reference/xml-documentation.md) sui vari tag xml che può essere usato per altri markup all'interno di commenti xmldoc.

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo : otherPoint:Point -> float
```

È possibile usare entrambi la versione abbreviata commenti in formato XML (`/// comment`), o commenti in formato XML standard (`///<summary>comment</summary>`).

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a>È consigliabile usare file di firma esplicita (. fsi) per la libreria stabile e componente API

Con le firme espliciti ai file in una libreria F# viene fornito un riepilogo dell'API pubblica, che consente di garantire che si conosce l'area pubblica completa della libreria, nonché offre una netta separazione tra documentazione pubblica e interni conciso dettagli di implementazione. Si noti che i file delle firme aggiungono attrito per modificare l'API pubblica, tramite la richiesta di modifiche da apportare nei file di implementazione e la firma. Di conseguenza, i file di firma in genere solo da introdurre quando un'API ha diventano solidificata e non è più previsto cambi in modo significativo.

### <a name="always-follow-best-practices-for-using-strings-in-net"></a>Seguire sempre le procedure consigliate per l'uso delle stringhe in .NET

Seguire [procedure consigliate per l'uso di stringhe in .NET](../../standard/base-types/best-practices-strings.md) indicazioni. In particolare, indicare sempre esplicitamente *finalità relative alla lingua* nella conversione e confronto di stringhe (dove applicabile).

## <a name="guidelines-for-f-facing-libraries"></a>Linee guida per F#-rivolta librerie

In questa sezione vengono offerti suggerimenti per lo sviluppo di pubbliche F#-rivolta alle librerie. vale a dire, le librerie che espone le API pubbliche che devono essere utilizzati dagli sviluppatori di F#. Esistono diverse indicazioni di progettazione di librerie applicabile in particolare a F#. In assenza di indicazioni specifiche che seguono, linee guida di progettazione di .NET della libreria sono le indicazioni di fallback.

### <a name="naming-conventions"></a>Convenzioni di denominazione

#### <a name="use-net-naming-and-capitalization-conventions"></a>Usare le convenzioni di denominazione e l'uso delle maiuscole .NET

La tabella seguente rispetta le convenzioni di denominazione e l'uso delle maiuscole .NET. Esistono piccole aggiunte per includere anche i costrutti F#.

| Costrutto | Case | Parte | Esempi | Note |
|-----------|------|------|----------|-------|
| Tipi concreti | PascalCase | Sostantivo / aggettivali | Elenco, Double, complesso | Tipi concreti sono strutture, classi, enumerazioni, delegati, record e unioni. Anche se i nomi dei tipi sono in genere in minuscoli in OCaml, F# ha adottato lo schema di denominazione .NET per i tipi.
| DLL           | PascalCase |                 | Fabrikam.Core.dll |  |
| Tag di unione     | PascalCase | Sostantivo | Alcuni casi, aggiungere, operazione riuscita | Non usare un prefisso nelle API pubbliche. Se lo si desidera usare un prefisso quando interni, ad esempio ' ' digitare team = TAlpha | TBeta | TDelta. ' ' |
| event          | PascalCase | Verbo | ValueChanged / ValueChanging |  |
| Eccezioni     | PascalCase |      | WebException | Nome deve terminare con "Exception". |
| Campo          | PascalCase | Sostantivo | CurrentName  | |
| Tipi interfaccia |  PascalCase | Sostantivo / aggettivali | IDisposable | Nome deve iniziare con "I". |
| Metodo |  PascalCase |  Verbo | ToString | |
| Spazio dei nomi | PascalCase | | FSharp | In genere usano `<Organization>.<Technology>[.<Subnamespace>]`, eliminare anche se l'organizzazione se la tecnologia è indipendente dell'organizzazione. |
| Parametri | camelCase | Sostantivo |  typeName, trasformazione, intervallo | |
| lasciare i valori (interni) | camelCase o PascalCase | Sostantivo / verbo |  getValue, myTable |
| lasciare i valori (esterno) | camelCase o PascalCase | Sostantivo/verbo  | List. map, Dates.Today | i valori di associazione let sono pubblici spesso quando si seguono i modelli di progettazione funzionali tradizionale. Tuttavia, in genere usano la notazione Pascal quando l'identificatore può essere utilizzato da altri linguaggi .NET. |
| Proprietà  | PascalCase  | Sostantivo / aggettivali  | IsEndOfFile, colore di sfondo  | Le proprietà booleane in genere l'utilizzo è e può e deve essere affermativa perché, come illustrato IsEndOfFile, non IsNotEndOfFile.

#### <a name="avoid-abbreviations"></a>Evitare le abbreviazioni

Linee guida di .NET sconsiglia l'uso di abbreviazioni (ad esempio, "utilizzare `OnButtonClick` anziché `OnBtnClick`"). Le abbreviazioni comuni, ad esempio `Async` per "Asincrono", è consentito. Questa indicazione viene ignorata in alcuni casi per la programmazione funzionale; ad esempio, `List.iter` Usa un'abbreviazione per "eseguire l'iterazione". Per questo motivo, uso di abbreviazioni tende a essere tollerati da un livello superiore in F#-a-programmazione in F#, ma comunque generalmente devono essere evitati in Progettazione del componente pubblico.

#### <a name="avoid-casing-name-collisions"></a>Evitare conflitti di nomi di maiuscole e minuscole

Linee guida di .NET si supponga che maiuscole e minuscole da solo non può essere utilizzata per distinguere i conflitti di nomi, poiché alcune lingue di client (ad esempio, Visual Basic) sono tra maiuscole e minuscole.

#### <a name="use-acronyms-where-appropriate"></a>Usare gli acronimi dove appropriato

Gli acronimi quali XML non sono abbreviazioni e vengono ampiamente usati nelle librerie .NET in formato minuscolo (Xml). Devono essere usati solo acronimi ben conosciuti e ampiamente riconosciuti.

#### <a name="use-pascalcase-for-generic-parameter-names"></a>Usano la notazione Pascal per i nomi di parametro generico

Per i nomi dei parametri generici nelle API pubbliche, tra cui per F# usano la notazione Pascal-rivolta librerie. In particolare, usare nomi quale `T`, `U`, `T1`, `T2` arbitrari parametri generici e se nomi specifici siano significativi, quindi per F#-librerie affiancate utilizzano nomi quale `Key`, `Value`, `Arg`(ma non, ad esempio, `TKey`).

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a>Usare PascalCase o camelCase per le funzioni pubbliche e i valori nei moduli di F#

camelCase viene usato per le funzioni pubbliche che sono progettate per essere usato non qualificato (ad esempio, `invalidArg`) e per le "funzioni di raccolta standard" (ad esempio, List. Map). In entrambi i casi, i nomi delle funzioni funzionano in modo simile le parole chiave nel linguaggio.

### <a name="object-type-and-module-design"></a>Oggetto, tipo e modulo di progettazione

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a>Usare gli spazi dei nomi o moduli per includere i tipi e i moduli

Ogni file F# in un componente deve iniziare con una dichiarazione dello spazio dei nomi o una dichiarazione di modulo.

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

Come indicato di seguito sono riportate le differenze tra l'uso di moduli e spazi dei nomi per organizzare il codice di primo livello:

* Gli spazi dei nomi possono estendersi su più file
* Gli spazi dei nomi non può contenere funzioni F#, a meno che non sono all'interno di un modulo interno
* Il codice di qualsiasi modulo specificato deve essere contenuto in un singolo file
* Moduli di primo livello possono contenere funzioni F# senza la necessità di un modulo interno

La scelta tra uno spazio dei nomi di primo livello o un modulo riguarda la forma compilata del codice e pertanto verrà la visualizzazione di altri linguaggi .NET devono API eventualmente essere usato di fuori del codice F#.

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a>Usare i metodi e proprietà per le operazioni intrinseche per i tipi di oggetto

Quando si lavora con gli oggetti, è consigliabile assicurarsi che possa essere utilizzata funzionalità viene implementata come metodi e proprietà per quel tipo.

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

La maggior parte delle funzionalità per un determinato membro non debba necessariamente essere implementata in tale membro, ma deve essere la parte di tale funzionalità può essere utilizzata.

#### <a name="use-classes-to-encapsulate-mutable-state"></a>Usare le classi per incapsulare lo stato modificabile

In F#, questo deve solo essere eseguita in cui che lo stato non è già incapsulato da un altro costrutto di linguaggio, ad esempio una chiusura, l'espressione di sequenza o calcolo asincrono.

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a>Usare le interfacce per raggruppare le operazioni correlate

Usare i tipi di interfaccia per rappresentare una serie di operazioni. Ciò è preferibile ad altre opzioni, ad esempio tuple di funzioni o i record delle funzioni.

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

In alternativa a:

```fsharp
type Serializer<'T> = {
    Serialize : bool -> 'T -> string
    Deserialize : bool -> string -> 'T
}
```

Le interfacce sono concetti di prima classe in .NET, che è possibile usare per ottenere la cosa Funtori normalmente verrebbero visualizzate. Inoltre, possono essere utilizzati per codificare tipi esistenziali nel programma, che non può essere i record delle funzioni.

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a>Usare un modulo per le funzioni di gruppo che agiscono sulle raccolte

Quando si definisce un tipo di raccolta, si consiglia di fornire un set standard di operazioni, ad esempio `CollectionType.map` e `CollectionType.iter`) per i nuovi tipi di raccolta.

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

Se si include un modulo di questo tipo, seguire le convenzioni di denominazione standard per le funzioni disponibili in FSharp. Core.

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a>Usare un modulo per le funzioni di gruppo per le funzioni comuni, canoniche, soprattutto in matematica e le librerie DSL

Ad esempio, `Microsoft.FSharp.Core.Operators` aperti automaticamente: raccolta di funzioni di primo livello (ad esempio `abs` e `sin`) fornito da FSharp.

Analogamente, una raccolta delle statistiche potrebbe includere un modulo con le funzioni `erf` e `erfc`, in cui questo modulo è progettato per essere automaticamente o in modo esplicito aperto.

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a>È consigliabile usare RequireQualifiedAccess e attentamente applicare attributi AutoOpen

Aggiunta di `[<RequireQualifiedAccess>]` attributo a un modulo indica che il modulo non può essere aperta e che i riferimenti agli elementi del modulo richiedono esplicita completo di accesso. Ad esempio, il `Microsoft.FSharp.Collections.List` modulo dispone di questo attributo.

Ciò è utile quando le funzioni e i valori nel modulo hanno nomi che possono entrare in conflitto con i nomi di altri moduli. Richiedere l'accesso completo può aumentare notevolmente la manutenibilità a lungo termine e capacità evolutiva di una libreria.

Aggiunta di `[<AutoOpen>]` attributo su un modulo, verrà aperto il modulo quando viene aperto lo spazio dei nomi che lo contiene. Il `[<AutoOpen>]` attributo può anche essere applicato a un assembly per indicare un modulo che viene aperto automaticamente quando viene fatto riferimento all'assembly.

Ad esempio, una raccolta di statistiche **MathsHeaven.Statistics** potrebbe contenere una `module MathsHeaven.Statistics.Operators` contenenti funzioni `erf` e `erfc`. È ragionevole contrassegnare questo modulo come `[<AutoOpen>]`. Ciò significa `open MathsHeaven.Statistics` verrà anche aprire questo modulo e visualizzare i nomi `erf` e `erfc` nell'ambito. Usa un'altra buona `[<AutoOpen>]` è per i moduli contenenti i metodi di estensione.

Utilizzo eccessivo di `[<AutoOpen>]` lead inquinato gli spazi dei nomi e l'attributo deve essere utilizzata con cautela. Per le librerie specifiche in domini specifici, uso attento di `[<AutoOpen>]` può portare a una migliore utilizzabilità.

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a>Si consiglia di definire i membri di operatore sulle classi in cui è appropriato usare operatori noti

In alcuni casi classi vengono utilizzate per la modellazione matematici costrutti come vettori. Quando il dominio in fase di modellazione include operatori noti, vengono definiti come membri intrinseci per la classe è utile.

```fsharp
type Vector(x:float) =

    member v.X = x

    static member (*) (vector:Vector, scalar:float) = Vector(vector.X * scalar)

    static member (+) (vector1:Vector, vector2:Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

Questo materiale sussidiario corrisponde alle linee guida generali di .NET per questi tipi. Tuttavia, può essere inoltre importante in F# di codifica poiché in questo modo questi tipi da utilizzare in combinazione con le funzioni F# e i metodi con vincoli di membro, ad esempio List. sumBy.

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a>È consigliabile usare CompiledName per fornire una. Nome descrittivo del NET per altri consumer di linguaggio .NET

In alcuni casi si potrebbe voler assegnare un nome in uno stile per i consumer di F# (ad esempio un membro statico in caratteri minuscoli in modo che venga visualizzato come se fosse una funzione associata al modulo), ma hanno uno stile diverso per il nome quando viene compilato in un assembly. È possibile usare il `[<CompiledName>]` attributo per fornire uno stile diverso per F# non codice che utilizza l'assembly.

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

Usando `[<CompiledName>]`, è possibile usare le convenzioni di denominazione .NET per F# non consumer dell'assembly.

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a>Usare metodi (overload) per le funzioni membro, se in questo modo viene fornita un'API più semplice

L'overload di metodo è un potente strumento per la semplificazione di un'API che potrebbe essere necessario eseguire una funzionalità simile, ma con diverse opzioni o argomenti.

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

In F#, è più comune per eseguire l'overload di un numero di argomenti anziché i tipi degli argomenti.

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a>Se la progettazione di questi tipi è probabile che si evolvono, nascondere le rappresentazioni dei record e i tipi di unione

Evitare di rivelare concrete rappresentazioni degli oggetti. Ad esempio, la rappresentazione di concreto <xref:System.DateTime> valori non è stato rivelato dall'API esterno, pubblico di progettazione di librerie di .NET. In fase di esecuzione, Common Language Runtime sa l'implementazione di commit che verrà usato in tutta l'esecuzione. Tuttavia, codice compilato non stesso prelevare le dipendenze alla relativa rappresentazione in concreta.

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a>Evitare l'utilizzo dell'ereditarietà dell'implementazione per l'estensibilità

In F#, viene usato raramente ereditarietà dell'implementazione. Inoltre, le gerarchie di ereditarietà sono spesso complessi e difficili da modificare quando arrivano nuovi requisiti. Implementazione dell'ereditarietà è ancora presente in F# per la compatibilità e rari casi in cui è la soluzione migliore per risolvere un problema, ma tecniche alternative devono essere ricercate nei programmi F# quando si progetta per il polimorfismo, ad esempio di implementazione dell'interfaccia.

### <a name="function-and-member-signatures"></a>Firme di funzione e membro

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a>Usare le tuple per i valori restituiti quando viene restituito un numero ridotto di più valori non correlati

Ecco un buon esempio di uso di una tupla in un tipo restituito:

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

Per restituire i tipi che contengono molti componenti, o se i componenti sono correlati a una singola entità identificabili, valutare l'uso di un tipo denominato anziché una tupla.

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a>Usare `Async<T>` per la programmazione asincrona in base ai limiti API F#

Se vi è un'operazione sincrona corrispondente denominata `Operation` che restituisce un `T`, quindi l'operazione asincrona deve essere denominato `AsyncOperation` se il valore restituito `Async<T>` oppure `OperationAsync` se restituisce `Task<T>`. Per i tipi .NET comunemente utilizzati che espongono i metodi Begin/End, è consigliabile usare `Async.FromBeginEnd` scrivere metodi di estensione come un'interfaccia per fornire il F# async modello di programmazione per le API .NET.

```fsharp
type SomeType =
    member this.Compute(x:int) : int =
        ...
    member this.AsyncCompute(x:int) : Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a>Eccezioni

Visualizzare [gestione degli errori](conventions.md#error-management) per apprendere l'utilizzo appropriato di eccezioni, i risultati e le opzioni.

### <a name="extension-members"></a>Membri di estensione

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a>Applicare con attenzione i membri di estensione F# in F#-a-F# componenti

Membri di estensione F# dovrebbero in genere essere utilizzati solo per le operazioni che si trovano nella chiusura di operazioni intrinseche associate a un tipo nella maggior parte delle relative modalità d'uso. Un utilizzo comune consiste nel fornire API che sono più a F# idiomatiche per diversi tipi di .NET:

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a>Tipi di unione

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a>Usare le unioni discriminate invece di gerarchie di classi per i dati di struttura ad albero

Strutture ad albero sono definiti in modo ricorsivo. È difficile con ereditarietà, ma con unioni discriminate elegante.

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

Che rappresenta i dati di struttura ad albero con unioni discriminate consente anche di trarre vantaggio da exhaustiveness nei criteri di ricerca.

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a>Usare `[<RequireQualifiedAccess>]` su tipi di unione i cui nomi case non sono sufficientemente univoci

Si potrebbe trovare in un dominio in cui lo stesso nome è il nome migliore per scopi diversi, ad esempio case di unione discriminata. È possibile usare `[<RequireQualifiedAccess>]` per risolvere l'ambiguità di nomi dei casi per evitare di attivare confusi errori a causa di shadowing dipendenti per l'ordinamento delle `open` istruzioni

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a>Consente di nascondere le rappresentazioni delle unioni discriminate di API compatibili binarie se la progettazione di questi tipi è probabile che si evolvono

Le unioni tipi si basano su F# corrispondenza form per un modello di programmazione conciso. Come accennato in precedenza, è consigliabile evitare di rivelare le rappresentazioni di dati concreti se la progettazione di questi tipi è probabile che si evolvono.

Ad esempio, può essere nascosta la rappresentazione di un'unione discriminata con una dichiarazione privata o interna, oppure usando un file della firma.

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

Se si rivelano le unioni discriminate indiscriminatamente, può risultare difficile da versione libreria senza causare interruzioni nel codice utente. Si consiglia di rivelare uno o più criteri attivi per consentire la corrispondenza dei valori del tipo in uso.

Criteri attivi forniscono un modo alternativo per fornire i consumer di F# con criteri di ricerca si evita di esporre direttamente i tipi di unione F#.

### <a name="inline-functions-and-member-constraints"></a>Le funzioni inline e i vincoli di membro

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a>Definire generici algoritmi numerici utilizzando le funzioni inline con vincoli membro implicito e risolti in modo statico tipi generici

I vincoli di membro aritmetico e vincoli del confronto F# sono uno standard per la programmazione in F#. Si consideri il codice di esempio seguente:

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

Il tipo di questa funzione è come segue:

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

Si tratta di una funzione appropriata per un'API pubblica in una libreria matematica.

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a>Evitare l'utilizzo di vincoli relativi ai membri per simulare le classi di tipo e Duck Typing digitando

È possibile simulare "siete digitando" usando i vincoli di membro F#. Tuttavia, i membri che rendono utilizzano questa non in generale da usare in F#-a-progetti di libreria F#. Questo avviene perché le progettazioni di libreria in base ai vincoli impliciti sconosciuti o non standard tendono a causare problemi nel codice utente diventi flessibile e sono associati al modello di un framework specifico.

Inoltre, è probabile che un uso massiccio di vincoli relativi ai membri in questo modo può comportare tempi di compilazione molto lunghi.

### <a name="operator-definitions"></a>Definizioni dell'operatore

#### <a name="avoid-defining-custom-symbolic-operators"></a>Evitare di definire gli operatori simbolici personalizzati

Gli operatori personalizzati sono essenziali in alcune situazioni e sono estremamente utili notazionale dispositivi all'interno di un corpo di grandi dimensioni del codice di implementazione. Per i nuovi utenti di una libreria, le funzioni denominate sono spesso più facile da usare. Inoltre, operatori simbolici personalizzati possono essere difficili al documento e utenti trovarla più difficile per la ricerca della Guida sugli operatori, a causa di limitazioni esistenti nei motori di ricerca e dell'IDE.

Di conseguenza, si consiglia di pubblicare la funzionalità come funzioni denominate e i membri e inoltre esporre operatori per questa funzionalità solo se i vantaggi notazionale superano la documentazione e i costi cognitivi di prevedere.

### <a name="units-of-measure"></a>Unità di misura

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a>Usare con attenzione le unità di misura per motivi di sicurezza di tipo aggiunto nel codice F#

Informazioni di tipizzazione aggiuntive per le unità di misura viene cancellate quando viene visualizzato da altri linguaggi .NET. Tenere presente che la reflection, strumenti e componenti .NET verranno visualizzati i tipi-sans-unità. Ad esempio, verranno visualizzato c# consumatori `float` anziché `float<kg>`.

### <a name="type-abbreviations"></a>Abbreviazioni dei tipi

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a>Usare con attenzione le abbreviazioni dei tipi per semplificare il codice F#

La reflection, strumenti e componenti .NET non visualizzeranno i nomi abbreviati per i tipi. Utilizzo significativo di abbreviazioni dei tipi può inoltre effettuare un dominio vengono visualizzati più complessa di quanto effettivamente è, quale operazione potrebbe confondere gli utenti.

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a>Evitare le abbreviazioni dei tipi per i tipi pubblici di cui i membri e le proprietà devono essere intrinsecamente diversi rispetto a quelli disponibili nel tipo di cui è in corso abbreviato

In questo caso, il tipo viene abbreviato rivela troppe operazioni sulla rappresentazione di tipo effettivo da definire. Al contrario, prendere in considerazione l'abbreviazione in un tipo di classe o un'unione discriminata case singolo di wrapping (oppure, quando le prestazioni sono essenziali, è consigliabile usare un tipo struct per eseguire il wrapping l'abbreviazione).

Ad esempio, è tentato di definire una mappa a più come un caso speciale di una mappa di F#, ad esempio:

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

Tuttavia, le operazioni di notazione con punto logico per questo tipo non sono le stesse operazioni su una mappa, ad esempio, è ragionevole che l'operatore di ricerca siano mappati. [key] Restituisce un elenco vuoto se la chiave non è presente nel dizionario, anziché generare un'eccezione.

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a>Linee guida per le raccolte per l'utilizzo in altri linguaggi .NET

Durante la progettazione di librerie per l'uso di altri linguaggi .NET, è importante rispettare le [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/index.md). In questo documento, queste librerie sono contrassegnate come "vanilla" librerie di .NET, invece di F#-facing librerie che utilizzano F# costruisce senza alcuna restrizione. Progettazione di librerie .NET "vanilla" significa che fornisce le API di familiari e idiomatiche coerente con il resto di .NET Framework, riducendo al minimo l'uso di F#-costrutti specifici nell'API pubblica. Le regole sono illustrate nelle sezioni seguenti.

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a>Namespace e il tipo di progettazione (per le librerie per l'utilizzo in altri linguaggi .NET)

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a>Applicare le convenzioni di denominazione .NET per l'API pubblica dei componenti

Prestare particolare attenzione all'uso di nomi abbreviati e linee guida di maiuscole/minuscole di .NET.

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a>Usare gli spazi dei nomi, tipi e membri della struttura organizzativa primaria per i componenti

Tutti i file che contiene la funzionalità pubblica devono iniziare con un `namespace` dichiarazione e l'unica entità pubblici negli spazi dei nomi devono essere tipi. Non usare i moduli di F#.

Usare i moduli non pubblici per contenere il codice di implementazione, utilità tipi e funzioni di utilità.

I tipi statici devono essere Preferiti a moduli, poiché consentono un'ottica evolutiva future dell'API usare overload e altri concetti di progettazione di API .NET che non possono essere usati all'interno di moduli di F#.

Ad esempio, al posto dell'API pubblica seguente:

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

Si consideri invece:

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a>Usare i tipi di record F# in vanilla API .NET se non si evoluzione la progettazione dei tipi

I tipi di record F# compilate in una classe .NET semplice. Questi sono adatti per alcuni tipi semplici e stabili per le API. È consigliabile usare la `[<NoEquality>]` e `[<NoComparison>]` attributi per eliminare la generazione automatica delle interfacce. Anche evitare di usare campi modificabili record vanilla API .NET come questi espone un campo pubblico. Valutare sempre se una classe fornisce un'opzione più flessibile per evoluzione futura dell'API.

Ad esempio, il codice F# seguente espone l'API pubblica a un consumer in c#:

F#:

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing : int
        SecondThing : string }
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

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a>Nascondere la rappresentazione dei tipi unione F# in vanilla API .NET

Tipi di unione F# non usati comunemente nei limiti dei componenti, anche per F#-a-F# di codifica. Si tratta di un dispositivo di implementazione eccellenti quando usata internamente all'interno di componenti e librerie.

Quando si progetta un'API .NET di vanilla, prendere in considerazione se si nasconde la rappresentazione di un tipo di unione tramite una dichiarazione privata o un file della firma.

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

Si potrebbero aumentare anche tipi che utilizzano internamente una rappresentazione in forma unione con i membri per fornire un desiderato. API rivolte NET.

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

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a>Progettazione interfaccia utente grafica e altri componenti tramite i modelli di progettazione di framework

Sono disponibili molti framework differenti all'interno di .NET, ad esempio WinForms, WPF e ASP.NET. Convenzioni di denominazione e progettazione per ognuno devono essere utilizzate se si progettano i componenti per l'utilizzo in tali Framework. Ad esempio, per la programmazione WPF, adottare i modelli di progettazione WPF per le classi che si sta progettando. Per i modelli di programmazione dell'interfaccia utente, usare modelli di progettazione, ad esempio eventi e le raccolte basato sulla notifica, ad esempio quelli disponibili in <xref:System.Collections.ObjectModel>.

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a>Progettazione di oggetti e membri (per le librerie per l'utilizzo in altri linguaggi .NET)

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a>Usare l'attributo CLIEvent per esporre gli eventi .NET

Costruire una `DelegateEvent` con una specifica di .NET tipo che accetta un oggetto delegato e `EventArgs` (anziché un' `Event`, che usa solo il `FSharpHandler` tipo per impostazione predefinita), in modo che gli eventi vengono pubblicati in modo familiare per altri linguaggi .NET.

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x:int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a>Esponi le operazioni asincrone come metodi che restituiscono le attività .NET

Le attività vengono usate in .NET per rappresentare i calcoli asincroni attivi. Le attività sono in genere meno composizionale rispetto a F# `Async<T>` oggetti, poiché rappresentano le attività "già in esecuzione" e non possono essere composti insieme nei modi che eseguire la composizione di parallel, o che nasconde la propagazione dei segnali di annullamento e le altre parametri di contestuali.

Tuttavia, nonostante ciò, i metodi che restituiscono le attività sono la rappresentazione della programmazione asincrona in .NET standard.

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int) : Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

Sarà spesso anche vuole accettare un token di annullamento esplicito:

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x:int) : Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a>Usare i tipi di delegati di .NET anziché dei tipi di funzione F#

In questo caso "tipi di funzione F#" significa che i tipi di "freccia" come `int -> int`.

Anziché il seguente:

```fsharp
member this.Transform(f:int->int) =
    ...
```

Eseguire questa operazione:

```fsharp
member this.Transform(f:Func<int,int>) =
    ...
```

Viene visualizzato il tipo di funzione F# come `class FSharpFunc<T,U>` per altri linguaggi .NET ed è meno adatto per le funzionalità del linguaggio e gli strumenti che supportano i tipi delegati. Durante la creazione di un metodo di ordine superiore destinate a .NET Framework 3.5 o versione successiva, il `System.Func` e `System.Action` i delegati sono le API a destra per la pubblicazione per consentire agli sviluppatori .NET di usare queste API in modo semplice. (Quando la destinazione è .NET Framework 2.0, i tipi delegati definiti dal sistema sono più limitati, è consigliabile usare tipi delegato predefinito, ad esempio `System.Converter<T,U>` o definizione di un tipo delegato specifico.)

D'altra parte, i delegati di .NET non siano naturali per F#-rivolta librerie (vedere la sezione successiva in F#-rivolta librerie). Di conseguenza, una strategia di implementazione comune quando si sviluppano i metodi di ordine superiore per vanilla librerie .NET consiste nel creare tutto l'implementazione che usa tipi di funzione F# e quindi creare l'API pubblica uso dei delegati come un'interfaccia thin sopra l'effettivo F# implementazione.

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a>Usare il modello TryGetValue invece di restituire i valori delle opzioni F# e preferiscono l'overload di metodo all'esecuzione di valori delle opzioni F# come argomenti

Modelli comuni di utilizzo per il tipo di opzione F# per le API sono preferibili implementato in vanilla tecniche di progettazione API .NET con .NET standard. Invece di restituire un valore di opzione di F#, è consigliabile usare il tipo restituito bool oltre a un parametro out come il modello "TryGetValue". E anziché adottare valori delle opzioni F# come parametri, è consigliabile usare l'overload di metodo o argomenti facoltativi.

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal : byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x : int, y : int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x : int) = x

member this.ParamOverload(x : int, y : int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a>Usare l'interfaccia di raccolta .NET i tipi di IEnumerable\<T\> e IDictionary\<chiave, valore\> per i parametri e valori restituiti

Evitare l'utilizzo di tipi, ad esempio le matrici .NET di raccolta concreti `T[]`, i tipi F# `list<T>`, `Map<Key,Value>` e `Set<T>`, e i tipi di raccolta concreti .NET, ad esempio `Dictionary<Key,Value>`. Linee guida di progettazione di .NET della libreria sono ottimo suggerimento relative all'utilizzo di diversi tipi di raccolta, ad esempio `IEnumerable<T>`. Utilizzato per scopi di matrici (`T[]`) è accettabile in alcune circostanze, per motivi di prestazioni. Si noti che in particolare `seq<T>` è solo di F# alias di `IEnumerable<T>`, ed è pertanto seq spesso un tipo appropriato per un normale API .NET.

Invece di elenchi F#:

```fsharp
member this.PrintNames(names : string list) =
    ...
```

Usare le sequenze di F#:

```fsharp
member this.PrintNames(names : seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a>Usare il tipo di unità come l'unico tipo di input di un metodo per definire un metodo specificato dall'argomento di zero o come unico tipo per definire un metodo che restituisce void restituito

Evitare di altri utilizzi del tipo di unità. Si tratta di una buona:

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x : int) = ()
```

Si tratta di una non valido:

```fsharp
member this.WrongUnit( x:unit, z:int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a>Verificare la presenza di valori null in "vanilla" dei limiti delle API .NET

Codice di implementazione F# tende ad avere un minor numero di valori null, a causa di limitazioni sull'utilizzo di valori letterali null mobili per i tipi F# e modelli di progettazione non modificabile. Altri linguaggi .NET utilizzano spesso null come un valore molto più frequentemente. Per questo motivo, codice F# che espone un'API .NET di vanilla deve controllare i parametri i valori null in corrispondenza del limite di API e impedire che tali valori pervengono più approfondito il codice di implementazione F#. Il `isNull` funzione o criteri di ricerca nel `null` modello può essere usato.

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

Preferire invece la restituzione di un tipo denominato che contiene i dati aggregati o tramite i parametri out per restituire più valori. Anche se esistono le tuple e le tuple struct in .NET, incluso supporto del linguaggio c# per le tuple struct, vengono in genere non fornirà l'API ideale e previsto per gli sviluppatori .NET.

#### <a name="avoid-the-use-of-currying-of-parameters"></a>Evitare l'uso di currying dei parametri

Usare invece le convenzioni di chiamata .NET ``Method(arg1,arg2,…,argN)``.

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

Suggerimento: Se si sta progettando le librerie per l'utilizzo in qualsiasi linguaggio .NET, non è alcuna sostituzione di effettivamente eseguite alcune sperimentale in c# e Visual Basic programming per garantire che le librerie "aspetto destra" da questi linguaggi. È anche possibile usare strumenti, ad esempio .NET Reflector e il Visualizzatore oggetti di Visual Studio per garantire che le librerie e la relativa documentazione vengono visualizzati come previsto per gli sviluppatori.

## <a name="appendix"></a>Appendice

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a>Esempio end-to-end di progettazione di codice F# per l'uso da altri linguaggi .NET

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

Il tipo F# derivato di questa classe è il seguente:

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

Diamo un'occhiata a come viene visualizzato questo tipo di F# per un programmatore che utilizza un altro linguaggio .NET. Ad esempio, approssimativo c# "firma" è come segue:

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

Esistono alcuni aspetti importanti da notare il modo in F# rappresenta costrutti qui. Ad esempio:

* I metadati, ad esempio i nomi degli argomenti sono stato mantenuto.

* Metodi di F# che accettano due argomenti diventano c# i metodi che accettano due argomenti.

* Funzioni e gli elenchi diventano i riferimenti ai tipi corrispondenti nella libreria di F#.

Il codice seguente viene illustrato come modificare il codice per tenere conto di queste operazioni.

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

Il tipo F# dedotto del codice è il seguente:

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

La firma c# è ora come indicato di seguito:

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

Le correzioni apportate per preparare questo tipo per l'uso come parte di una libreria .NET "vanilla" sono i seguenti:

* Regolato diversi nomi: `Point1`, `n`, `l`, e `f` è diventato `RadialPoint`, `count`, `factor`, e `transform`, rispettivamente.

* Utilizzato un tipo restituito `seq<RadialPoint>` invece di `RadialPoint list` modificando una costruzione elenco utilizzando `[ ... ]` a una sequenza di costruzione utilizzando `IEnumerable<RadialPoint>`.

* Utilizzare il tipo di delegato .NET `System.Func` invece di un tipo di funzione F#.

Questo rende molto accattivante utilizzare nel codice c#.
