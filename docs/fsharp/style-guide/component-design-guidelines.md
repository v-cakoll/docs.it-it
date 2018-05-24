---
title: 'Indicazioni per la progettazione di componenti F #'
description: 'Altre linee guida per la scrittura di F # componenti destinati al consumo ad altri chiamanti.'
ms.date: 05/14/2018
ms.openlocfilehash: 7e71710b1bc2fe3e8d7a5a091513a1432650dc04
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2018
---
# <a name="f-component-design-guidelines"></a>Indicazioni per la progettazione di componenti F #

Questo documento è un set di linee guida di progettazione di componenti per F # di programmazione, in base a F # componente linee guida di progettazione, v14, Microsoft Research, e [un'altra versione](https://fsharp.org/specs/component-design-guidelines/) originariamente risposta curata relativa e gestiti da F # Software Foundation.

Questo documento presuppone che si ha familiarità con la programmazione F #. Un ringraziamento community F # per i relativi contributi e commenti e suggerimenti utili su varie versioni di questa Guida.

## <a name="overview"></a>Panoramica

Questo documento vengono esaminati alcuni dei problemi relativi alla progettazione di componenti di F # e di codifica. Un componente può significare degli elementi seguenti:

* Un livello nel progetto F # con utenti esterni all'interno di tale progetto.
* Una libreria destinata all'utilizzo tra limiti di assembly da codice F #.
* Una libreria destinata all'utilizzo da qualsiasi linguaggio .NET tra limiti di assembly.
* Una libreria destinata alla distribuzione tramite un repository di pacchetti, ad esempio [NuGet](https://nuget.org).

Seguono le tecniche descritte in questo articolo il [cinque principi di codice F # buona](index.md#five-principles-of-good-f-code)e utilizzano entrambi funzionale e programmazione come appropriato dell'oggetto.

Indipendentemente dalla metodologia, la finestra di progettazione di componenti e la libreria è rivolto numerosi problemi pratici e semplice quando si prova a creare un'API che è più facilmente utilizzabile dagli sviluppatori. Applicazione attenta del [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/index.md) verrà guidare è per la creazione di un set coerente di API che sono piacevole utilizzare.

## <a name="general-guidelines"></a>Indicazioni generali

Vi sono alcune linee guida universale che si applicano a librerie F #, indipendentemente dai destinatari per la libreria.

### <a name="learn-the-net-library-design-guidelines"></a>Altre linee guida di progettazione di libreria .NET

Indipendentemente dal tipo di F # la generazione di codice vengono eseguite, è utile per avere una conoscenza del [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/index.md). La maggior parte delle altre F # programmatori di .NET verranno avere familiarità con queste linee guida e prevede che il codice .NET sia conforme a essi.

La finestra di progettazione libreria .NET indicazioni generali relative alla denominazione, Progettazione classi e interfacce, progettazione di membri (proprietà, metodi, eventi, e così via) e altro ancora e sono un utile punto di riferimento per un'ampia gamma di indicazioni di progettazione.

### <a name="add-xml-documentation-comments-to-your-code"></a>Aggiungere commenti di documentazione XML al codice

Documentazione XML nelle API pubbliche assicurarsi che gli utenti possono ottenere Intellisense e informazioni rapide quando utilizzando questi tipi e membri e la documentazione di compilazione enable file per la libreria. Vedere la [documentazione XML](../language-reference/xml-documentation.md) sui vari tag xml che può essere utilizzato per il markup aggiuntive all'interno di commenti xmldoc.

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo : otherPoint:Point -> float
```

È possibile utilizzare i commenti XML forma breve (`/// comment`), o commenti XML standard (`///<summary>comment</summary>`).

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a>Provare a utilizzare file di firma esplicita (. fsi) per la libreria stabile e componente API

Utilizzo dei file di firme esplicita in una libreria F # viene fornito un riepilogo conciso dell'API pubblica, che contribuisce a garantire che si conosce la superficie pubblica completa della libreria, nonché fornisce una netta separazione tra documentazione pubblica e interni dettagli di implementazione. Si noti che i file di firma aggiungono attrito alla modifica dell'API pubblica, tramite la richiesta di modifiche da apportare nei file di implementazione e la firma. Di conseguenza, i file di firma devono in genere essere introdotto solo quando un'API ha diventano solidificata e non è più previsto per modificare in modo significativo.

### <a name="always-follow-best-practices-for-using-strings-in-net"></a>Sempre seguire le procedure consigliate per l'utilizzo di stringhe in .NET

Seguire [procedure consigliate per l'uso di stringhe in .NET](../../standard/base-types/best-practices-strings.md) informazioni aggiuntive. In particolare, sempre esplicitamente *finalità relative alla lingua* nella conversione e confronto di stringhe (dove applicabile).

## <a name="guidelines-for-f-facing-libraries"></a>Linee guida per F #-rivolti verso librerie

In questa sezione vengono offerti suggerimenti per lo sviluppo di F # pubblico-affiancate alle librerie. vale a dire, le librerie che espone le API pubbliche che devono essere utilizzati dagli sviluppatori di F #. Sono disponibili numerosi consigli di progettazione di librerie applicabile in particolare a F #. In mancanza di indicazioni specifiche che seguono, la finestra di progettazione libreria .NET sono le linee guida di fallback.

### <a name="naming-conventions"></a>Convenzioni di denominazione

#### <a name="use-net-naming-and-capitalization-conventions"></a>Utilizzare le convenzioni di denominazione e l'uso delle maiuscole .NET

Nella tabella seguente è conforme alle convenzioni di denominazione e l'uso delle maiuscole .NET. Esistono piccole aggiunte includere inoltre costrutti di F #.

| Costrutto | Case | Parte | Esempi | Note |
|-----------|------|------|----------|-------|
| Tipi concreti | PascalCase | Sostantivo / frasario | Elenco, Double, complesso | Tipi concreti sono strutture, classi, enumerazioni, delegati, i record e unioni. Anche se i nomi dei tipi sono in genere in lettere minuscole in OCaml, F # ha adottato lo schema di denominazione per i tipi .NET.
| DLL           | PascalCase |                 | Fabrikam.Core.dll |  |
| Tag di unione     | PascalCase | sostantivo | In alcuni casi, aggiungere, operazione riuscita | Non utilizzare un prefisso nelle API pubbliche. Se lo si desidera utilizzare un prefisso interno, ad esempio ' ' digitare team = TAlpha | TBeta | TDelta. ' ' |
| event          | PascalCase | Verbo | ValueChanged / ValueChanging |  |
| Eccezioni     | PascalCase |      | WebException | Nome deve terminare con "Exception". |
| Campo          | PascalCase | sostantivo | CurrentName  | |
| Tipi interfaccia |  PascalCase | Sostantivo / frasario | IDisposable | Nome deve iniziare con "I". |
| Metodo |  PascalCase |  Verbo | ToString | |
| Spazio dei nomi | PascalCase | | Microsoft.FSharp.Core | In genere utilizzare `<Organization>.<Technology>[.<Subnamespace>]`, eliminare anche se l'organizzazione se la tecnologia è indipendente dell'organizzazione. |
| Parametri | camelCase | sostantivo |  typeName, trasformazione, intervallo | |
| consentire i valori (interni) | camelCase o PascalCase | Sostantivo / verbo |  getValue, myTable |
| consentire i valori (esterna) | camelCase o PascalCase | Sostantivo/verbo  | List. map, Dates.Today | i valori associati a let sono pubblici spesso quando segue i modelli di progettazione funzionale tradizionale. Tuttavia, in genere PascalCase quando usare l'identificatore può essere utilizzato da altri linguaggi .NET. |
| Proprietà  | PascalCase  | Sostantivo / frasario  | IsEndOfFile, colore di sfondo  | Le proprietà booleane in genere l'utilizzo è e può e deve essere affermativa perché, come in IsEndOfFile, non IsNotEndOfFile.

#### <a name="avoid-abbreviations"></a>Evitare le abbreviazioni

Linee guida di .NET se ne sconsiglia l'utilizzo di abbreviazioni (ad esempio, "usare `OnButtonClick` anziché `OnBtnClick`"). Le abbreviazioni comuni, ad esempio `Async` per "Asincrono", sono tollerata. Questa linea guida viene ignorata in alcuni casi per la programmazione funzionale; ad esempio, `List.iter` Usa un'abbreviazione per "eseguire l'iterazione". Per questo motivo, tramite le abbreviazioni tende a essere espresso con maggiore precisione in F #-a-programmazione F #, ma ancora in genere sconsigliato nella progettazione di componenti pubblici.

#### <a name="avoid-casing-name-collisions"></a>Evitare conflitti di nomi di maiuscole/minuscole

Linee guida di .NET sostengono maiuscole e minuscole da solo non può essere utilizzato per risolvere l'ambiguità conflitti di nomi, poiché alcune lingue client (ad esempio, Visual Basic) sono tra maiuscole e minuscole.

#### <a name="use-acronyms-where-appropriate"></a>Gli acronimi dove appropriato

Gli acronimi, ad esempio XML non sono abbreviazioni e vengono ampiamente utilizzati nelle librerie .NET nel formato minuscolo (Xml). Devono essere utilizzati solo acronimi noti, ampiamente riconosciuti.

#### <a name="use-pascalcase-for-generic-parameter-names"></a>Utilizzare PascalCase per i nomi di parametro generico

Utilizzare PascalCase per i nomi di parametro generico nelle API pubbliche, tra cui per F #-rivolti verso librerie. In particolare, utilizzare nomi quale `T`, `U`, `T1`, `T2` per i parametri generici arbitrari e nomi specifici ha senso, quindi per F #-librerie affiancate utilizzano nomi quale `Key`, `Value`, `Arg`(ma non ad esempio, `TKey`).

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a>Utilizzare PascalCase o camelCase per le funzioni pubbliche e i valori nei moduli di F #

camelCase viene utilizzato per le funzioni pubbliche che sono progettate per essere usati non qualificato (ad esempio, `invalidArg`) e per le funzioni"raccolta standard" (ad esempio, List. Map). In entrambi questi casi, i nomi delle funzioni si comportano molto come parole chiave del linguaggio.

### <a name="object-type-and-module-design"></a>Progettazione di oggetto, tipo e modulo

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a>Usare gli spazi dei nomi o i moduli per includere i tipi e i moduli

Ogni file F # in un componente deve iniziare con una dichiarazione dello spazio dei nomi o in una dichiarazione di modulo.

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

Le differenze tra l'utilizzo di moduli e gli spazi dei nomi per organizzare il codice al livello superiore sono come segue:

* Spazi dei nomi può estendersi su più file
* Spazi dei nomi non può contenere funzioni F # a meno che non siano all'interno di un modulo interno
* Il codice di qualsiasi modulo specificato deve essere contenuto in un singolo file
* Moduli di primo livello possono contenere funzioni F # senza la necessità di un modulo interno

La scelta tra un livello superiore dello spazio dei nomi o modulo riguarda il form compilato del codice e pertanto verrà la visualizzazione da parte di altri linguaggi .NET devono dell'API infine essere utilizzata all'esterno del codice F #.

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a>Utilizzare i metodi e proprietà per le operazioni intrinseche per i tipi di oggetto

Quando si lavora con gli oggetti, è consigliabile verificare che la funzionalità può essere utilizzata viene implementata come metodi e proprietà per quel tipo.

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

La maggior parte delle funzionalità per un determinato membro non debba necessariamente essere implementata in tale membro, ma deve essere parte del consumo di tali funzionalità.

#### <a name="use-classes-to-encapsulate-mutable-state"></a>Usare le classi per incapsulare lo stato modificabile

In F #, solo deve essere eseguita in cui che lo stato non è già incapsulato da un altro costrutto di linguaggio, ad esempio una chiusura, l'espressione di sequenza o calcolo asincrono.

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a>Utilizzare le interfacce per raggruppare le operazioni correlate

Per rappresentare un set di operazioni, utilizzare i tipi di interfaccia. Si tratta di Preferiti ad altre opzioni, ad esempio le tuple di funzioni o i record delle funzioni.

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

A:

```fsharp
type Serializer<'T> = {
    Serialize : bool -> 'T -> string
    Deserialize : bool -> string -> 'T
}
```

Le interfacce sono concetti di primaria importanza in .NET, è possibile utilizzare per ottenere ciò che Funtori verrebbero normalmente fornito è. Inoltre, possono essere utilizzati per codificare tipi esistenziali nel programma, che non può essere record delle funzioni.

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a>Usa un modulo alle funzioni di gruppo che agiscono sulle raccolte

Quando si definisce un tipo di raccolta, si consiglia di fornire un set standard di operazioni come `CollectionType.map` e `CollectionType.iter`) per i nuovi tipi di raccolta.

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

Se si include un modulo di questo tipo, seguire le convenzioni di denominazione standard per le funzioni trovate in FSharp. Core.

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a>Usa un modulo alle funzioni di gruppo per le funzioni comuni e canoniche, soprattutto nelle librerie DSL e matematiche

Ad esempio `Microsoft.FSharp.Core.Operators` è una raccolta di funzioni di primo livello aperta automaticamente (ad esempio `abs` e `sin`) fornite da FSharp.

Analogamente, una raccolta di statistiche potrebbe includere un modulo con funzioni `erf` e `erfc`, in cui questo modulo è progettato per essere in modo esplicito o automaticamente aperto.

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a>È consigliabile usare RequireQualifiedAccess e attentamente applicare attributi AutoOpen

Aggiunta di `[<RequireQualifiedAccess>]` attributo a un modulo indica che il modulo non può essere aperta e che i riferimenti agli elementi del modulo richiedono esplicita qualificato l'accesso. Ad esempio, il `Microsoft.FSharp.Collections.List` modulo dispone di questo attributo.

Ciò è utile quando le funzioni e valori nel modulo hanno nomi che sono probabile che sia in conflitto con i nomi di altri moduli. Che richiedono l'accesso completo può aumentare notevolmente la facilità di gestione a lungo termine ed evolvability di una libreria.

Aggiunta di `[<AutoOpen>]` attributo su un modulo, il modulo verrà aperto quando viene aperto lo spazio dei nomi che lo contiene. Il `[<AutoOpen>]` attributo può anche essere applicato a un assembly per indicare un modulo che viene aperto automaticamente quando l'assembly viene fatto riferimento.

Ad esempio, una raccolta di statistiche **MathsHeaven.Statistics** potrebbe contenere un `module MathsHeaven.Statistics.Operators` contenenti funzioni `erf` e `erfc`. È ragionevole contrassegnare questo modulo come `[<AutoOpen>]`. Ciò significa `open MathsHeaven.Statistics` inoltre, verranno aprire questo modulo e visualizzare i nomi `erf` e `erfc` nell'ambito. Buona un altro uso di `[<AutoOpen>]` è per i moduli che contiene i metodi di estensione.

Utilizzo eccessivo di `[<AutoOpen>]` lead inquinati gli spazi dei nomi e l'attributo deve essere utilizzata con cautela. Per raccolte specifiche in domini specifici, l'utilizzo razionale di `[<AutoOpen>]` può portare a una migliore utilizzabilità.

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a>Si consiglia di definire i membri di operatore sulle classi in cui è appropriata utilizzando operatori noti

In alcuni casi classi vengono utilizzate per la modellazione matematici costrutti come vettori. Quando il dominio da modellare dispone di operatori noti, è utile definendole come membri intrinseci alla classe.

```fsharp
type Vector(x:float) =

    member v.X = x

    static member (*) (vector:Vector, scalar:float) = Vector(vector.X * scalar)

    static member (+) (vector1:Vector, vector2:Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

Questo materiale sussidiario corrisponde a informazioni aggiuntive generali .NET per questi tipi. Tuttavia, può essere inoltre importante in F # di codifica poiché in questo modo questi tipi da utilizzare in combinazione con le funzioni F # e i metodi con vincoli di membro, ad esempio List. sumBy.

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a>Provare a usare CompiledName per fornire una. Nome descrittivo di rete per altri consumer di linguaggio .NET

In alcuni casi potrebbe essere necessario specificare un nome significativo in uno stile per i consumer di F # (ad esempio un membro statico in lettere minuscole, in modo che venga visualizzato come se fosse una funzione associata a modulo), ma hanno uno stile diverso per il nome quando viene compilato in un assembly. È possibile utilizzare il `[<CompiledName>]` attributo per fornire uno stile diverso per il codice F # non utilizzano l'assembly.

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

Tramite `[<CompiledName>]`, è possibile utilizzare le convenzioni di denominazione .NET per F # non consumer dell'assembly.

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a>Utilizzare metodi (overload) per le funzioni membro, se in questo modo viene fornita un'API semplice

L'overload di metodo è un potente strumento per la semplificazione di un'API che potrebbe essere necessario eseguire una funzionalità simile, ma con diverse opzioni o argomenti.

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

In F #, è più comune per eseguire l'overload di un numero di argomenti anziché tipi di argomenti.

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a>Se la progettazione di questi tipi è probabile che si evolvono nascondere le rappresentazioni di record e i tipi di unione

Evitare di rivelare concrete rappresentazioni di oggetti. Ad esempio, la rappresentazione concreta di <xref:System.DateTime> valori non venga rivelata dall'API di pubblico, esterno del progetto di libreria .NET. In fase di esecuzione, Common Language Runtime sa l'implementazione del commit che verrà utilizzato in tutta l'esecuzione. Tuttavia, codice compilato non stesso prelevare le dipendenze sulla rappresentazione concreta.

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a>Evitare l'utilizzo dell'ereditarietà dell'implementazione per l'estensibilità

In F #, viene raramente utilizzata l'implementazione dell'ereditarietà. Inoltre, le gerarchie di ereditarietà sono spesso complessi e difficili da modificare all'arrivano di nuovi requisiti. Implementazione dell'ereditarietà continua a esistere in F # per la compatibilità e rari casi in cui è la soluzione migliore per risolvere un problema, ma tecniche alternative devono essere cercate nei programmi F # quando si progetta il polimorfismo, ad esempio l'implementazione dell'interfaccia.

### <a name="function-and-member-signatures"></a>Firme di funzione e membro

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a>Utilizzano le tuple per i valori restituiti quando viene restituito un numero ridotto di più valori non correlati

Di seguito è un buon esempio dell'utilizzo di una tupla in un tipo restituito:

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

Per restituire i tipi che contengono molti componenti o in cui i componenti sono correlati a una singola entità personali, è consigliabile usare un tipo denominato anziché una tupla.

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a>Utilizzare `Async<T>` per la programmazione asincrona in base ai limiti API F #

Se vi è un'operazione sincrona corrispondente denominata `Operation` che restituisce un `T`, l'operazione asincrona deve essere denominata `AsyncOperation` se non viene restituita `Async<T>` oppure `OperationAsync` se restituisce `Task<T>`. Per i tipi .NET comunemente utilizzati che espongono metodi Begin/End, è consigliabile utilizzare `Async.FromBeginEnd` scrivere metodi di estensione come facciata per fornire il F # async modello di programmazione per le API .NET.

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

Eccezioni sono costituite dalle eccezionali in .NET. vale a dire, essi non viene eseguito spesso in fase di esecuzione. In questo caso, le informazioni che contengono sono importanti. Le eccezioni sono un concetto di prima classe di .NET; core IT pertanto indicato di seguito che appropriato l'applicazione delle eccezioni deve essere utilizzati come parte della progettazione dell'interfaccia di un componente.

#### <a name="follow-the-net-guidelines-for-exceptions"></a>Seguire le linee guida di .NET per le eccezioni

Il [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/exceptions.md) consulenza eccellente sull'utilizzo delle eccezioni nel contesto della programmazione .NET. Alcune di queste istruzioni sono i seguenti:

* Non utilizzare le eccezioni per il normale flusso di controllo. Sebbene questa tecnica viene spesso utilizzata in lingue quali OCaml, è soggetta a bug e può risultare inefficiente su .NET. Al contrario, provare a restituire un `None` valore per indicare un errore che è un problema comune o previsto dell'opzione.

* Documentare le eccezioni generate dai componenti quando viene utilizzata una funzione in modo non corretto.

* Dove possibile, utilizzare eccezioni esistenti degli spazi dei nomi System. Evitare <xref:System.ApplicationException>, anche se.

* Non generare <xref:System.Exception> quando lo sarà escluse per il codice utente. Ciò include evitare l'uso di `failwith`, `failwithf`, che sono funzioni utili per l'utilizzo in script e per il codice in fase di sviluppo, ma deve essere rimossa dal codice di libreria F # a favore di generazione di un tipo di eccezione più specifico.

* Uso `nullArg`, `invalidArg`, e `invalidOp` come meccanismo di generare <xref:System.ArgumentNullException>, <xref:System.ArgumentException>, e <xref:System.InvalidOperationException> quando appropriato.

#### <a name="consider-using-option-values-for-return-types-when-failure-is-not-an-exceptional-scenario"></a>Provare a utilizzare i valori delle opzioni per i tipi restituiti quando un errore non è uno scenario eccezionale

L'approccio di .NET per le eccezioni è che deve essere "eccezioni". vale a dire, dovranno essere eseguite raramente. Tuttavia, alcune operazioni (ad esempio, la ricerca di una tabella) potrebbero non riuscire con frequenza. I valori delle opzioni F # sono un ottimo modo per rappresentare i tipi restituiti di queste operazioni. Queste operazioni tradizionalmente iniziano con il prefisso di nome "try":

```fsharp
// bad: throws exception if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// bad: returns -1 if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// good: returns None if no element meets criteria
member this.TryFindFirstIndex(pred : 'T -> bool) : int option =
    ...
```

### <a name="extension-members"></a>Membri di estensione

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a>Applicare con attenzione i membri di estensione F # in F #-a-F # componenti

Membri di estensione F # in genere esclusivamente per operazioni che trovano nella chiusura di operazioni intrinseche associate a un tipo nella maggior parte delle relative modalità d'uso. Un utilizzo comune consiste nel fornire le API che sono più idiomatiche a F # per vari tipi di .NET:

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

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a>Utilizzare le unioni discriminate anziché gerarchie di classi per i dati di struttura ad albero

Strutture ad albero sono definiti in modo ricorsivo. È difficile con ereditarietà ma elegante con unioni discriminate.

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

Rappresentazione ad albero dei dati con le unioni discriminate consente inoltre di trarre vantaggio da exhaustiveness nei criteri di ricerca.

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a>Utilizzare `[<RequireQualifiedAccess>]` sui tipi di unione i cui nomi case non sono sufficientemente univoci

Potrebbe essere necessario in un dominio in cui lo stesso nome è il nome migliore per scopi diversi, ad esempio case di unione discriminata. È possibile utilizzare `[<RequireQualifiedAccess>]` per risolvere le ambiguità nei nomi dei casi per evitare di causare confusi errori a causa di shadowing dipendente da ordine della `open` istruzioni

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a>Consente di nascondere le rappresentazioni delle unioni discriminate per le API compatibile binarie se la progettazione di questi tipi è probabile che si evolvono

Tipi di unioni si basano su F # corrispondenza form per un modello di programmazione conciso. Come accennato in precedenza, è consigliabile evitare di rivelare le rappresentazioni di dati concreti se la progettazione di questi tipi è probabile che si evolvono.

Ad esempio, la rappresentazione di un'unione discriminata può essere nascosto utilizzando una dichiarazione privata o interna, oppure utilizzando un file della firma.

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

Se si rivelano le unioni discriminate indiscriminatamente, può risultare difficile versione libreria senza interrompere il codice utente. Si consiglia di rivelare uno o più criteri attivi per consentire la corrispondenza dei valori del tipo in uso.

Criteri attivi forniscono un modo alternativo per fornire i consumer di F # con criteri di ricerca si evita di esporre direttamente i tipi di unione F #.

### <a name="inline-functions-and-member-constraints"></a>Funzioni inline e vincoli di membro

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a>Definire algoritmi generici numerici utilizzando le funzioni inline con vincoli di membro implicito e i tipi generici risolti staticamente

Membro aritmetico i vincoli e F # confronto sono standard per la programmazione F #. Si consideri il codice di esempio seguente:

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

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a>Evitare di utilizzare i vincoli di membro per simulare le classi di tipo e duck digitando

È possibile simulare "siete digitando" usando i vincoli di membro F #. Tuttavia, i membri che rendono l'utilizzo di questo generale in non deve essere usato in F #-a-progettazioni libreria F #. Questo avviene perché le progettazioni di libreria in base a vincoli impliciti sconosciuti o non standard tendono a causare problemi nel codice utente diventano flessibile e collegati al modello di un particolare framework.

Inoltre, è probabile che un uso massiccio di vincoli di membro in questo modo può comportare tempi di compilazione molto lunghi.

### <a name="operator-definitions"></a>Definizioni di operatore

#### <a name="avoid-defining-custom-symbolic-operators"></a>Evitare di definire gli operatori simbolici personalizzati

Gli operatori personalizzati sono essenziali in alcune situazioni e sono estremamente utili dispositivi notazionale in gran parte del codice di implementazione. Per i nuovi utenti di una libreria, denominate funzioni sono spesso più facile da utilizzare. Inoltre, gli operatori simbolici personalizzati possono essere difficili da documento e gli utenti riscontrano più difficile per la ricerca della Guida sugli operatori, a causa di limitazioni esistenti nei motori di ricerca e IDE.

Di conseguenza, si consiglia di pubblicare la funzionalità come funzioni denominate e i membri e inoltre esporre operatori per questa funzionalità solo se i vantaggi di annotazione che superano la documentazione e costo cognitivo contenente vincoli.

### <a name="units-of-measure"></a>Unità di misura

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a>Attentamente utilizzare unità di misura per motivi di sicurezza di tipo aggiunto nel codice F #

Informazioni di tipizzazione aggiuntive per le unità di misura viene cancellate quando visualizzati da altri linguaggi .NET. Tenere presente che la reflection, strumenti e componenti .NET verranno visualizzati i tipi di reti SAN unità. Ad esempio, verrà visualizzato c# consumer `float` anziché `float<kg>`.

### <a name="type-abbreviations"></a>Abbreviazioni dei tipi

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a>Usare con attenzione le abbreviazioni di tipo per semplificare il codice F #

La reflection, strumenti e componenti .NET non visualizzeranno i nomi abbreviati per i tipi. Utilizzo significativo di abbreviazioni dei tipi può inoltre effettuare un dominio vengono visualizzati più complessa di quanto effettivamente, che potrebbe confondere i consumer.

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a>Evitare le abbreviazioni di tipo per cui i membri e le proprietà devono essere intrinsecamente diversi a quelli disponibili in tipo da abbreviare i tipi pubblici

In questo caso, il tipo da abbreviare rivela troppo sulla rappresentazione del tipo effettivo in fase di definizione. Al contrario, provare a disposizione l'abbreviazione in un tipo di classe o un'unione discriminata case singolo (oppure, quando le prestazioni sono essenziali, provare a usare un tipo di struct per eseguire il wrapping l'abbreviazione).

Ad esempio, risulta vantaggioso per definire una multi-mappa come un caso speciale di una mappa di F #, ad esempio:

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

Tuttavia, le operazioni di notazione con punto logico per questo tipo non sono le stesse operazioni su una mappa, ad esempio, è ragionevole che l'operatore di ricerca siano mappati. [chiave] restituito l'elenco vuoto se la chiave non è presente nel dizionario, anziché generare un'eccezione.

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a>Linee guida per le librerie per usarle da altri linguaggi .NET

Quando si progettano le librerie per usarle da altri linguaggi .NET, è importante rispettare la [indicazioni per la progettazione di librerie .NET](../../standard/design-guidelines/index.md). In questo documento, queste librerie sono contrassegnate come vaniglia librerie .NET, a differenza di F #-rivolti verso librerie che utilizzano F # costruisce senza alcuna restrizione. Progettazione di librerie .NET vaniglia significa che fornisce le API di acquisire familiare e idiomatiche coerente con il resto di .NET Framework riducendo al minimo l'utilizzo di F #-costrutti specifici nell'API pubblica. Le regole sono illustrate nelle sezioni seguenti.

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a>Progettazione Namespace e tipo (per le librerie per l'utilizzo da parte di altri linguaggi .NET)

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a>Applicare le convenzioni di denominazione .NET per l'API pubblica i componenti di

Prestare particolare attenzione all'uso di nomi abbreviati e linee guida di maiuscole/minuscole di .NET.

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a>Usare gli spazi dei nomi, tipi e membri come la struttura organizzativa primaria per i componenti

Tutti i file che contiene la funzionalità pubblica devono iniziare con un `namespace` dichiarazione e l'unica entità pubblici negli spazi dei nomi devono essere tipi. Non usare i moduli di F #.

Usare i moduli non pubblici per contenere il codice di implementazione, tipi di utilità e funzioni di utilità.

I tipi statici devono essere Preferiti moduli, quanto in questo modo per future evoluzione dell'API per utilizzare l'overload e altri concetti di progettazione di API .NET che non possono essere utilizzati all'interno di moduli di F #.

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

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a>Utilizzare i tipi di record F # in vaniglia API .NET se la progettazione dei tipi non evolvere

I tipi di record F # possono essere compilate in una classe .NET semplice. Questi sono adatti per alcuni tipi semplici, stabili per le API. È consigliabile usare la `[<NoEquality>]` e `[<NoComparison>]` gli attributi per eliminare la generazione automatica di interfacce. Evitare anche i campi modificabili record vaniglia API .NET come questi espone un campo pubblico. Considerare sempre se una classe fornisce un'opzione più flessibile per evoluzione futura dell'API.

Ad esempio, il seguente codice F # espone l'API pubblica a un consumer in c#:

F #:

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

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a>Nascondere la rappresentazione di tipi unione F # in vaniglia API .NET

Tipi di unione F # non vengono comunemente utilizzati tra i limiti dei componenti, anche per F #-a-F # la generazione di codice. Si tratta di un dispositivo di implementazione eccellente quando utilizzato internamente nell'ambito dei componenti e le librerie.

Quando si progetta un vaniglia API .NET, è consigliabile nascondere la rappresentazione di un tipo di unione con una dichiarazione privata o un file della firma.

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

È inoltre possono integrare i tipi che utilizzano internamente una rappresentazione in forma unione con i membri per fornire un desiderato. API con connessione di rete.

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

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a>Progettazione grafica e altri componenti mediante i modelli di progettazione di framework

Sono disponibili numerosi Framework diversi all'interno di .NET, ad esempio Windows Form, WPF e ASP.NET. Convenzioni di denominazione e di progettazione per ogni devono essere utilizzate se si progettano i componenti per l'utilizzo di questi Framework. Ad esempio, per la programmazione WPF, adottare i modelli di progettazione WPF per le classi che si sta progettando. Per i modelli di programmazione dell'interfaccia utente, usare i modelli di progettazione, ad esempio gli eventi e le raccolte basato sulla notifica, ad esempio quelli disponibili in <xref:System.Collections.ObjectModel>.

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a>Progettazione di oggetti e membri (per le librerie per l'utilizzo da parte di altri linguaggi .NET)

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a>Usare l'attributo CLIEvent per esporre gli eventi di .NET

Costruire un `DelegateEvent` con una specifica di .NET tipo delegato System. che accetta un oggetto e `EventArgs` (anziché un' `Event`, che utilizza solo il `FSharpHandler` tipo per impostazione predefinita), in modo che gli eventi vengono pubblicati in modo familiare ad altri linguaggi .NET.

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

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a>Esporre operazioni asincrone dei metodi che restituiscono le attività di .NET

Le attività vengono utilizzate in .NET per rappresentare i calcoli asincroni attivi. Le attività sono in genere meno compositiva rispetto a F # `Async<T>` oggetti, poiché rappresentano le attività "già in esecuzione" e non può essere composto da insieme in modi che eseguire la composizione parallele o cui nascondere la propagazione dei segnali di annullamento e le altre parametri di scelta rapida.

Tuttavia, nonostante ciò, i metodi che restituiscono le attività sono la rappresentazione standard della programmazione asincrona in .NET.

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int) : Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

Sarà spesso si desidera anche accettare un token di annullamento esplicito:

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x:int) : Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a>Utilizzare i tipi delegati di .NET anziché i tipi F # (funzione)

Di seguito "tipi di funzione F #" indicano i tipi "freccia" quali `int -> int`.

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

Il tipo di funzione F # viene visualizzato come `class FSharpFunc<T,U>` ad altri linguaggi .NET, senza che sia meno idoneo alla funzionalità del linguaggio e gli strumenti che supportano i tipi delegati. Durante la creazione di un metodo di ordine superiore destinati a .NET Framework 3.5 o versione successiva, il `System.Func` e `System.Action` i delegati sono le API per la pubblicazione per consentire agli sviluppatori di .NET utilizzare queste API in modo semplice a destra. (Quando la destinazione è .NET Framework 2.0, i tipi delegati definiti dal sistema sono più limitati, provare a utilizzare i tipi delegati predefiniti, ad esempio `System.Converter<T,U>` o definizione di un tipo delegato specifico.)

Sul lato di scorrimento, i delegati di .NET non sono naturali per F #-rivolti verso librerie (vedere la sezione successiva in F #-rivolti verso librerie). Di conseguenza, una strategia di implementazione comune quando si sviluppano i metodi di ordine superiore per le librerie .NET vaniglia consiste nel creare tutti l'implementazione tramite tipi di funzioni F # e quindi l'API pubblica mediante delegati come facciata thin sopra effettivo F # implementazione.

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a>Utilizzare il modello di TryGetValue anziché restituire i valori delle opzioni F # e preferisce overload ad accettare i valori dell'opzione F # come argomenti

Modelli comuni di utilizzo per il tipo di opzione F # per le API sono migliori implementato in vaniglia tecniche di progettazione API .NET usando .NET standard. Anziché restituire un valore dell'opzione F #, provare a utilizzare il tipo restituito bool oltre a un parametro out come il modello "TryGetValue". E, anziché utilizzare valori di opzione F # come parametri, è consigliabile utilizzare l'overload di metodo o argomenti facoltativi.

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

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a>Utilizzare l'interfaccia di raccolta .NET tipi IEnumerable\<T\> e IDictionary\<chiave, valore\> per i parametri e valori restituiti

Evitare l'utilizzo di tipi di raccolta concreti, ad esempio matrici .NET `T[]`, i tipi F # `list<T>`, `Map<Key,Value>` e `Set<T>`, e tipi di raccolta concreta .NET come `Dictionary<Key,Value>`. La finestra di progettazione libreria .NET sono buoni consigli relative all'utilizzo di diversi tipi di raccolta, ad esempio `IEnumerable<T>`. Utilizzato per scopi di matrici (`T[]`) è accettabile in alcuni casi, per motivi di prestazioni. Si noti che in particolare `seq<T>` è semplicemente F # alias per `IEnumerable<T>`, e pertanto seq è spesso un tipo appropriato per un vaniglia API .NET.

Invece di F # Elenca:

```fsharp
member this.PrintNames(names : string list) =
    ...
```

Usare le sequenze di F #:

```fsharp
member this.PrintNames(names : seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a>Utilizzare il tipo di unità come unico tipo di input di un metodo per definire un metodo con argomenti di zero o come l'unico tipo per definire un metodo che restituisce void restituito

Evitare di altri utilizzi del tipo di unità. Si tratta buona:

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x : int) = ()
```

Si tratta non valida:

```fsharp
member this.WrongUnit( x:unit, z:int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a>Verificare la presenza di valori null nei limiti di vaniglia API .NET

Codice di implementazione di F # tenderà ad avere meno valori null, a causa di limitazioni sull'utilizzo di valori letterali null per i tipi F # e modelli di progettazione non modificabile. Altri linguaggi .NET utilizzano null come valore molto più frequente. Per questo motivo, codice F # che espone un'API .NET di vaniglia deve controllare i parametri per i valori null in corrispondenza del limite di API e impedire che questi valori pervengono più profondo il codice di implementazione di F #. Il `isNull` funzione o criteri di ricerca nel `null` modello può essere usato.

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a>Evitare di utilizzare le tuple come valori restituiti

Invece, preferire la restituzione di un tipo denominato che contiene i dati aggregati o tramite i parametri out per restituire più valori. Anche se tuple e tuple struct esistano in .NET (incluso il supporto di linguaggio c# per le tuple struct), spesso non fornirà del ideale e previsto dell'API per gli sviluppatori di .NET.

#### <a name="avoid-the-use-of-currying-of-parameters"></a>Evitare l'utilizzo di currying dei parametri

In alternativa, utilizzare le convenzioni di chiamata .NET ``Method(arg1,arg2,…,argN)``.

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

Suggerimento: Se si sta progettando le librerie per usarle da qualsiasi linguaggio .NET, quindi non è alternativo pratica alcuni sperimentale in c# e Visual Basic di programmazione per garantire che le librerie "all'aspetto a destra" da questi linguaggi. È anche possibile utilizzare strumenti quali Reflector .NET e Visual Studio Visualizzatore per garantire che le librerie e la relativa documentazione vengono visualizzati come previsto per gli sviluppatori.

## <a name="appendix"></a>Appendice

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a>Esempio end-to-end di progettazione di codice F # per l'utilizzo da altri linguaggi .NET

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

Esaminiamo un aspetto di questo tipo di F # a un programmatore che utilizza un altro linguaggio .NET. Ad esempio, approssimativo c# "firma" è come segue:

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

Esistono alcuni aspetti importanti da notare in modo F # rappresenta costrutti qui. Ad esempio:

* I metadati, ad esempio i nomi degli argomenti sono stato mantenuto.

* Metodi di F # che accettano due argomenti diventano c# i metodi che accettano due argomenti.

* Funzioni e gli elenchi diventano i riferimenti ai tipi corrispondenti nella libreria F #.

Il codice seguente viene illustrato come modificare il codice per tener conto di queste operazioni.

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

La firma c# viene ora come indicato di seguito:

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

Le correzioni apportate preparare questo tipo per l'uso come parte di una libreria .NET vaniglia sono i seguenti:

* Rettificato diversi nomi: `Point1`, `n`, `l`, e `f` è diventato `RadialPoint`, `count`, `factor`, e `transform`, rispettivamente.

* Utilizzato un tipo restituito `seq<RadialPoint>` invece di `RadialPoint list` modificando un elenco della costruzione utilizzando `[ ... ]` a una sequenza di costruzione utilizzando `IEnumerable<RadialPoint>`.

* Utilizzare il tipo di delegato .NET `System.Func` anziché un tipo di funzione F #.

Questo rende molto coloro utilizzare nel codice c#.
