---
title: F#linee guida di progettazione componenti
description: Le linee guida per la scrittura di informazioni su F# componenti destinati all'utilizzo da altri chiamanti.
ms.date: 05/14/2018
ms.openlocfilehash: bc8d4908912c4630f649ba30593d43a557278efa
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145673"
---
# <a name="f-component-design-guidelines"></a>F#linee guida di progettazione componenti

Questo documento è un set di linee guida di progettazione di componenti per F# programmazione, in base il F# linee guida di progettazione di componenti, v14, Microsoft Research, e [un'altra versione](https://fsharp.org/specs/component-design-guidelines/) originariamente curata e gestito dal F# Software Foundation.

Questo documento presuppone una familiarità con F# programmazione. Molti grazie ai F# community per i relativi contributi e commenti e suggerimenti utili su varie versioni di questa Guida.

## <a name="overview"></a>Panoramica

Questo documento vengono esaminati alcuni dei problemi correlati a F# componente progettazione e codifica. Un componente può significare che gli elementi seguenti:

* Un livello all'interno di F# progetto con gli utenti esterni all'interno di tale progetto.
* Una libreria destinata all'utilizzo da F# codice attraverso i limiti di assembly.
* Una libreria destinata all'utilizzo da qualsiasi linguaggio .NET attraverso i limiti di assembly.
* Una libreria destinata alla distribuzione tramite un repository dei pacchetti, ad esempio [NuGet](https://nuget.org).

Seguono le tecniche descritte in questo articolo il [cinque principi buone F# codice](index.md#five-principles-of-good-f-code)e pertanto utilizzano entrambi funzionali e oggetti di programmazione come appropriato.

Indipendentemente dalla metodologia, la finestra di progettazione di componenti e la libreria deve affrontare alcuni problemi pratici e banale durante il tentativo di creare un'API più facilmente utilizzabile dagli sviluppatori. Attenta applicazione dei [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/index.md) verrà volgere è per la creazione di un set coerente di API che sono piacevole da utilizzare.

## <a name="general-guidelines"></a>Indicazioni generali

Esistono alcune indicazioni universali che si applicano a F# le librerie, indipendentemente dai destinatari per la libreria.

### <a name="learn-the-net-library-design-guidelines"></a>Altre linee guida di progettazione di .NET della libreria

Indipendentemente dal tipo di F# scrittura di codice si esegue, è utile per avere una conoscenza del [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/index.md). Maggior parte degli altri F# , i programmatori di .NET verranno avere familiarità con queste linee guida e prevede che il codice .NET di conformarsi a essi.

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

Usa le firme esplicita ai file in un F# libreria fornisce un riepilogo dell'API pubblica, che consente di assicurarsi di conoscere il pubblico completo superficie della libreria, nonché offre una netta separazione tra documentazione pubblica e interno dettagli di implementazione. Si noti che i file delle firme aggiungono attrito per modificare l'API pubblica, tramite la richiesta di modifiche da apportare nei file di implementazione e la firma. Di conseguenza, i file di firma in genere solo da introdurre quando un'API ha diventano solidificata e non è più previsto cambi in modo significativo.

### <a name="always-follow-best-practices-for-using-strings-in-net"></a>Seguire sempre le procedure consigliate per l'uso delle stringhe in .NET

Seguire [procedure consigliate per l'uso di stringhe in .NET](../../standard/base-types/best-practices-strings.md) indicazioni. In particolare, indicare sempre esplicitamente *finalità relative alla lingua* nella conversione e confronto di stringhe (dove applicabile).

## <a name="guidelines-for-f-facing-libraries"></a>Linee guida per F#-con le librerie di connessione

In questa sezione vengono offerti suggerimenti per lo sviluppo di pubbliche F#-rivolta alle librerie. vale a dire, le librerie che espone le API pubbliche che devono essere utilizzati da F# gli sviluppatori. Esistono diverse indicazioni di progettazione di librerie applicabile in particolare per F#. In assenza di indicazioni specifiche che seguono, linee guida di progettazione di .NET della libreria sono le indicazioni di fallback.

### <a name="naming-conventions"></a>Convenzioni di denominazione

#### <a name="use-net-naming-and-capitalization-conventions"></a>Usare le convenzioni di denominazione e l'uso delle maiuscole .NET

La tabella seguente rispetta le convenzioni di denominazione e l'uso delle maiuscole .NET. Esistono piccole aggiunte per includere anche F# costrutti di.

| Costrutto | Case | Parte | Esempi | Note |
|-----------|------|------|----------|-------|
| Tipi concreti | PascalCase | Sostantivo / aggettivali | Elenco, Double, complesso | Tipi concreti sono strutture, classi, enumerazioni, delegati, record e unioni. Anche se i nomi dei tipi sono in genere in minuscoli in OCaml, F# ha adottato lo schema di denominazione .NET per i tipi.
| DLL           | PascalCase |                 | Fabrikam.Core.dll |  |
| Tag di unione     | PascalCase | Sostantivo | Alcuni casi, aggiungere, operazione riuscita | Non usare un prefisso nelle API pubbliche. Se lo si desidera usare un prefisso quando interni, ad esempio `digitare team = TAlpha | TBeta | TDelta.` |
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

Linee guida di .NET sconsiglia l'uso di abbreviazioni (ad esempio, "utilizzare `OnButtonClick` anziché `OnBtnClick`"). Le abbreviazioni comuni, ad esempio `Async` per "Asincrono", è consentito. Questa indicazione viene ignorata in alcuni casi per la programmazione funzionale; ad esempio, `List.iter` Usa un'abbreviazione per "eseguire l'iterazione". Per questo motivo, uso di abbreviazioni tende a essere tollerati da un livello superiore in F#- a -F# programmazione, ma comunque generalmente devono essere evitati in Progettazione del componente pubblico.

#### <a name="avoid-casing-name-collisions"></a>Evitare conflitti di nomi di maiuscole e minuscole

Linee guida di .NET si supponga che maiuscole e minuscole da solo non può essere utilizzata per distinguere i conflitti di nomi, poiché alcune lingue di client (ad esempio, Visual Basic) sono tra maiuscole e minuscole.

#### <a name="use-acronyms-where-appropriate"></a>Usare gli acronimi dove appropriato

Gli acronimi quali XML non sono abbreviazioni e vengono ampiamente usati nelle librerie .NET in formato minuscolo (Xml). Devono essere usati solo acronimi ben conosciuti e ampiamente riconosciuti.

#### <a name="use-pascalcase-for-generic-parameter-names"></a>Usano la notazione Pascal per i nomi di parametro generico

Usano la notazione Pascal per i nomi dei parametri generici nelle API pubbliche, inclusi per F#-con le librerie di connessione. In particolare, usare nomi quale `T`, `U`, `T1`, `T2` arbitrari parametri generici e se nomi specifici siano significativi, quindi F#-librerie affiancate utilizzano nomi quale `Key`, `Value`, `Arg` (ma non, ad esempio, `TKey`).

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a>Usare PascalCase o camelCase per le funzioni pubbliche e i valori in F# i moduli

camelCase viene usato per le funzioni pubbliche che sono progettate per essere usato non qualificato (ad esempio, `invalidArg`) e per le "funzioni di raccolta standard" (ad esempio, List. Map). In entrambi i casi, i nomi delle funzioni funzionano in modo simile le parole chiave nel linguaggio.

### <a name="object-type-and-module-design"></a>Oggetto, tipo e modulo di progettazione

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a>Usare gli spazi dei nomi o moduli per includere i tipi e i moduli

Ogni F# file in un componente deve iniziare con una dichiarazione dello spazio dei nomi o una dichiarazione di modulo.

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
* Non può contenere spazi dei nomi F# funzioni a meno che non sono all'interno di un modulo interno
* Il codice di qualsiasi modulo specificato deve essere contenuto in un singolo file
* Moduli di primo livello possono contenere F# funzioni senza la necessità di un modulo interno

La scelta tra uno spazio dei nomi di primo livello o un modulo riguarda la forma compilata del codice e pertanto verrà la visualizzazione di altri linguaggi .NET devono API infine essere utilizzata all'esterno di F# codice.

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

Questo materiale sussidiario corrisponde alle linee guida generali di .NET per questi tipi. Tuttavia, può essere inoltre importante in F# codifica poiché in questo modo questi tipi da utilizzare in combinazione con F# funzioni e metodi con vincoli di membro, ad esempio List. sumBy.

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a>È consigliabile usare CompiledName per fornire una. Nome descrittivo del NET per altri consumer di linguaggio .NET

In alcuni casi si potrebbe voler assegnare un nome in uno stile per F# consumer (ad esempio un membro statico in caratteri minuscoli in modo che venga visualizzato come se fosse una funzione associata al modulo), ma hanno uno stile diverso per il nome quando viene compilato in un assembly. È possibile usare la `[<CompiledName>]` attributo per fornire uno stile diverso per non F# codice che utilizza l'assembly.

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

Usando `[<CompiledName>]`, è possibile usare convenzioni di denominazione .NET per non F# consumer dell'assembly.

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

In F#, viene usato raramente ereditarietà dell'implementazione. Inoltre, le gerarchie di ereditarietà sono spesso complessi e difficili da modificare quando arrivano nuovi requisiti. Implementazione dell'ereditarietà è ancora presente F# per la compatibilità e rari casi in cui è la soluzione migliore per risolvere un problema, ma tecniche alternative devono essere cercate nel F# programmi durante la progettazione per il polimorfismo, ad esempio di interfaccia implementazione.

### <a name="function-and-member-signatures"></a>Firme di funzione e membro

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a>Usare le tuple per i valori restituiti quando viene restituito un numero ridotto di più valori non correlati

Ecco un buon esempio di uso di una tupla in un tipo restituito:

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

Per restituire i tipi che contengono molti componenti, o se i componenti sono correlati a una singola entità identificabili, valutare l'uso di un tipo denominato anziché una tupla.

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a>Uso `Async<T>` per async programming in F# dei limiti delle API

Se vi è un'operazione sincrona corrispondente denominata `Operation` che restituisce un `T`, quindi l'operazione asincrona deve essere denominato `AsyncOperation` se il valore restituito `Async<T>` oppure `OperationAsync` se restituisce `Task<T>`. Per i tipi .NET comunemente utilizzati che espongono i metodi Begin/End, è consigliabile usare `Async.FromBeginEnd` scrivere metodi di estensione come un'interfaccia per fornire i F# modello di programmazione asincroni per le API .NET.

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

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a>Applicare con attenzione F# i membri di estensione in F#- a -F# componenti

F#membri di estensione devono in genere essere utilizzati solo per le operazioni che si trovano nella chiusura di operazioni intrinseche associate a un tipo nella maggior parte delle relative modalità d'uso. Un utilizzo comune consiste nel fornire le API che sono più idiomatiche per F# per diversi tipi di .NET:

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

Le unioni tipi si basano sulla F# criteri di ricerca di form per un modello di programmazione conciso. Come accennato in precedenza, è consigliabile evitare di rivelare le rappresentazioni di dati concreti se la progettazione di questi tipi è probabile che si evolvono.

Ad esempio, può essere nascosta la rappresentazione di un'unione discriminata con una dichiarazione privata o interna, oppure usando un file della firma.

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

Se si rivelano le unioni discriminate indiscriminatamente, può risultare difficile da versione libreria senza causare interruzioni nel codice utente. Si consiglia di rivelare uno o più criteri attivi per consentire la corrispondenza dei valori del tipo in uso.

Criteri attivi forniscono un modo alternativo per specificare F# utenti con criteri di ricerca evitando l'esposizione di F# direttamente i tipi di unione.

### <a name="inline-functions-and-member-constraints"></a>Le funzioni inline e i vincoli di membro

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a>Definire generici algoritmi numerici utilizzando le funzioni inline con vincoli membro implicito e risolti in modo statico tipi generici

I vincoli di membro aritmetico e F# vincoli del confronto sono standard per F# di programmazione. Si consideri il codice di esempio seguente:

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

È possibile simulare l'utilizzo di "duck typing" F# vincoli di membro. Tuttavia, i membri che rendono utilizzano questa non in generale da usare in F#- a -F# le progettazioni di libreria. Questo avviene perché le progettazioni di libreria in base ai vincoli impliciti sconosciuti o non standard tendono a causare problemi nel codice utente diventi flessibile e sono associati al modello di un framework specifico.

Inoltre, è probabile che un uso massiccio di vincoli relativi ai membri in questo modo può comportare tempi di compilazione molto lunghi.

### <a name="operator-definitions"></a>Definizioni dell'operatore

#### <a name="avoid-defining-custom-symbolic-operators"></a>Evitare di definire gli operatori simbolici personalizzati

Gli operatori personalizzati sono essenziali in alcune situazioni e sono estremamente utili notazionale dispositivi all'interno di un corpo di grandi dimensioni del codice di implementazione. Per i nuovi utenti di una libreria, le funzioni denominate sono spesso più facile da usare. Inoltre, operatori simbolici personalizzati possono essere difficili al documento e utenti trovarla più difficile per la ricerca della Guida sugli operatori, a causa di limitazioni esistenti nei motori di ricerca e dell'IDE.

Di conseguenza, si consiglia di pubblicare la funzionalità come funzioni denominate e i membri e inoltre esporre operatori per questa funzionalità solo se i vantaggi notazionale superano la documentazione e i costi cognitivi di prevedere.

### <a name="units-of-measure"></a>Unità di misura

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a>Usare con attenzione le unità di misura per motivi di sicurezza di tipo aggiunto in F# codice

Informazioni di tipizzazione aggiuntive per le unità di misura viene cancellate quando viene visualizzato da altri linguaggi .NET. Tenere presente che la reflection, strumenti e componenti .NET verranno visualizzati i tipi-sans-unità. Ad esempio, verranno visualizzato c# consumatori `float` anziché `float<kg>`.

### <a name="type-abbreviations"></a>Abbreviazioni dei tipi

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a>Usare con attenzione le abbreviazioni dei tipi per semplificare la F# codice

La reflection, strumenti e componenti .NET non visualizzeranno i nomi abbreviati per i tipi. Utilizzo significativo di abbreviazioni dei tipi può inoltre effettuare un dominio vengono visualizzati più complessa di quanto effettivamente è, quale operazione potrebbe confondere gli utenti.

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a>Evitare le abbreviazioni dei tipi per i tipi pubblici di cui i membri e le proprietà devono essere intrinsecamente diversi rispetto a quelli disponibili nel tipo di cui è in corso abbreviato

In questo caso, il tipo viene abbreviato rivela troppe operazioni sulla rappresentazione di tipo effettivo da definire. Al contrario, prendere in considerazione l'abbreviazione in un tipo di classe o un'unione discriminata case singolo di wrapping (oppure, quando le prestazioni sono essenziali, è consigliabile usare un tipo struct per eseguire il wrapping l'abbreviazione).

Ad esempio, è tentato di definire una mappa più come un caso speciale di un F# esegue il mapping, ad esempio:

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

Tuttavia, le operazioni di notazione con punto logico per questo tipo non sono le stesse operazioni su una mappa, ad esempio, è ragionevole che l'operatore di ricerca siano mappati. [key] Restituisce un elenco vuoto se la chiave non è presente nel dizionario, anziché generare un'eccezione.

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a>Linee guida per le raccolte per l'utilizzo in altri linguaggi .NET

Durante la progettazione di librerie per l'uso di altri linguaggi .NET, è importante rispettare le [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/index.md). In questo documento, queste librerie sono contrassegnate come "vanilla" librerie di .NET, in contrapposizione a F#-per le raccolte che usano F# costruisce senza alcuna restrizione. Progettazione di librerie .NET "vanilla" significa fornire familiari e idiomatiche API coerente con il resto di .NET Framework, riducendo al minimo l'uso di F#-costrutti specifici nell'API pubblica. Le regole sono illustrate nelle sezioni seguenti.

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

Tutti i file che contiene la funzionalità pubblica devono iniziare con un `namespace` dichiarazione e l'unica entità pubblici negli spazi dei nomi devono essere tipi. Non usare F# i moduli.

Usare i moduli non pubblici per contenere il codice di implementazione, utilità tipi e funzioni di utilità.

I tipi statici devono essere Preferiti a moduli, poiché consentono un'ottica evolutiva future dell'API usare overload e altri concetti di progettazione di API .NET che non possono essere usati all'interno di F# i moduli.

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

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a>Usare F# tipi di record nell'API .NET di vanilla se non si evoluzione la progettazione dei tipi

F#tipi di record è compilata in una classe .NET semplice. Questi sono adatti per alcuni tipi semplici e stabili per le API. È consigliabile usare la `[<NoEquality>]` e `[<NoComparison>]` attributi per eliminare la generazione automatica delle interfacce. Anche evitare di usare campi modificabili record vanilla API .NET come questi espone un campo pubblico. Valutare sempre se una classe fornisce un'opzione più flessibile per evoluzione futura dell'API.

Il seguente, ad esempio, F# codice espone l'API pubblica a un C# consumer:

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

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a>Nascondere la rappresentazione di F# tipi di unione in vanilla API .NET

F#tipi di unione non usati comunemente nei limiti dei componenti, anche per F#- a -F# scrittura di codice. Si tratta di un dispositivo di implementazione eccellenti quando usata internamente all'interno di componenti e librerie.

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

Le attività vengono usate in .NET per rappresentare i calcoli asincroni attivi. Le attività sono in genere meno composizionale rispetto a F# `Async<T>` oggetti, poiché rappresentano le attività "già in esecuzione" e non possono essere combinate insieme nei modi che eseguire la composizione di parallel, o che nasconde la propagazione di segnali di annullamento e altri parametri contestuali.

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

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a>Usare tipi di delegati di .NET al posto di F# tipi di funzione

In questo caso "F# tipi di funzione" significa che i tipi di "freccia" come `int -> int`.

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

Il F# tipo di funzione viene visualizzato come `class FSharpFunc<T,U>` ad altri linguaggi .NET ed è meno adatto per le funzionalità del linguaggio e gli strumenti che supportano i tipi delegati. Durante la creazione di un metodo di ordine superiore destinate a .NET Framework 3.5 o versione successiva, il `System.Func` e `System.Action` i delegati sono le API a destra per la pubblicazione per consentire agli sviluppatori .NET di usare queste API in modo semplice. (Quando la destinazione è .NET Framework 2.0, i tipi delegati definiti dal sistema sono più limitati, è consigliabile usare tipi delegato predefinito, ad esempio `System.Converter<T,U>` o definizione di un tipo delegato specifico.)

D'altra parte, non siano naturali per i delegati di .NET F#-con le librerie di connessione (vedere la sezione successiva in F#-rivolta librerie). Di conseguenza, una strategia di implementazione comune durante lo sviluppo di metodi di ordine superiore per vanilla librerie .NET consiste nel creare tutti l'implementazione tramite F# tipi di funzione e quindi creare l'API pubblica uso dei delegati come un'interfaccia thin sopra l'effettivo F#implementazione.

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a>Usare il modello TryGetValue invece di restituire F# i valori delle opzioni e preferiscono l'overload dei metodi di acquisizione F# i valori come argomenti delle opzioni

Modelli comuni di utilizzo per il F# tipo di opzione per le API sono preferibili implementato in vanilla tecniche di progettazione API .NET con .NET standard. Invece di restituire un F# valore dell'opzione, è possibile usare il tipo restituito bool oltre a un parametro out come il modello "TryGetValue". E invece di acquisizione F# i valori come parametri di opzione, è possibile usare gli argomenti del metodo overload o facoltativi.

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

Evitare l'utilizzo di tipi, ad esempio le matrici .NET di raccolta concreti `T[]`, F# tipi `list<T>`, `Map<Key,Value>` e `Set<T>`, e i tipi di raccolta concreti .NET, ad esempio `Dictionary<Key,Value>`. Linee guida di progettazione di .NET della libreria sono ottimo suggerimento relative all'utilizzo di diversi tipi di raccolta, ad esempio `IEnumerable<T>`. Utilizzato per scopi di matrici (`T[]`) è accettabile in alcune circostanze, per motivi di prestazioni. Si noti che in particolare `seq<T>` è solo per il F# alias di `IEnumerable<T>`, e pertanto spesso seq è un tipo appropriato per un normale API .NET.

Invece di F# Elenca:

```fsharp
member this.PrintNames(names : string list) =
    ...
```

Usare F# sequenze:

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

F#codice di implementazione tende ad avere un minor numero di valori null, a causa di modelli di progettazione non modificabile e limitazioni sull'utilizzo di valori letterali null mobili per F# tipi. Altri linguaggi .NET utilizzano spesso null come un valore molto più frequentemente. Per questo motivo, F# codice che espone un'API .NET di vanilla deve controllare i parametri i valori null in corrispondenza del limite di API e impedire questi valori verso più approfondita in di F# il codice di implementazione. Il `isNull` funzione o criteri di ricerca nel `null` modello può essere usato.

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

Suggerimento: Se si sta progettando le librerie per l'utilizzo in qualsiasi linguaggio .NET, quindi non resta altro per effettivamente eseguite alcune sperimentale C# e per garantire che le librerie "aspetto destra" da questi linguaggi di programmazione Visual Basic. È anche possibile usare strumenti, ad esempio .NET Reflector e il Visualizzatore oggetti di Visual Studio per garantire che le librerie e la relativa documentazione vengono visualizzati come previsto per gli sviluppatori.

## <a name="appendix"></a>Appendice

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a>Esempio end-to-end di progettazione F# codice per l'uso da altri linguaggi .NET

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

Il derivato F# tipo di questa classe è il seguente:

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

Diamo un'occhiata a come questo F# tipo viene visualizzato a un programmatore che utilizza un altro linguaggio .NET. Ad esempio, approssimativo c# "firma" è come segue:

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

Esistono alcuni aspetti importanti da notare su come F# costrutti di rappresenta qui. Ad esempio:

* I metadati, ad esempio i nomi degli argomenti sono stato mantenuto.

* F#i metodi che accettano due argomenti diventi C# i metodi che accettano due argomenti.

* Funzioni e gli elenchi diventano i riferimenti ai tipi corrispondenti di F# library.

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

Il derivato F# è di tipo del codice come indicato di seguito:

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

* Il tipo di delegato di .NET usata `System.Func` anziché un F# tipo di funzione.

Questo rende molto accattivante utilizzare nel codice c#.
