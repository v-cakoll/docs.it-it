---
title: Panoramica di F#
description: Esaminare alcune delle principali funzionalità del linguaggio in questa presentazione con esempi di codice di programmazione F#.
ms.date: 11/06/2018
ms.openlocfilehash: 4b3ec7fd2c42712440ea7d7045c560ab20390b45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61901728"
---
# <a name="tour-of-f"></a>Panoramica di F\#

Il modo migliore per informazioni su F# è per leggere e scrivere codice F#. Questo articolo verrà agire come un tour dettagliato alcune delle principali funzionalità del linguaggio F# e offrono alcuni frammenti di codice che è possibile eseguire nel computer. Per altre informazioni sull'impostazione di un ambiente di sviluppo, consultare [introduttiva](tutorials/getting-started/index.md).

Esistono due concetti primari in F#: tipi e funzioni.  Questa esercitazione verrà illustrate le funzionalità del linguaggio che rientrano in queste due concetti.

## <a name="executing-the-code-online"></a>L'esecuzione del codice online

Se non hai F# installato nel computer, è possibile eseguire tutti gli esempi in linea con il [REPL Fable](https://fable.io/repl/). Fable è un sottolinguaggio di F# che viene eseguita direttamente nel browser. Per visualizzare gli esempi che seguono in REPL, consultare **esempi > Scopri > Panoramica del F#**  nella barra dei menu a sinistra delle transazioni replica Fable

## <a name="functions-and-modules"></a>Funzioni e moduli

Le parti più importanti di qualsiasi programma F# vengono ***funzioni*** organizzato ***moduli***.  [Le funzioni](language-reference/functions/index.md) eseguiti in input per produrre output e sono organizzati sotto [moduli](language-reference/modules.md), che rappresentano il modo principale si raggruppano le cose in F#.  Vengono definite usando il [ `let` associazione](language-reference/functions/let-bindings.md), cui assegnare un nome di funzione e definire i relativi argomenti.

[!code-fsharp[BasicFunctions](../../samples/snippets/fsharp/tour.fs#L101-L133)]

`let` le associazioni sono anche come associare un valore a un nome simile a una variabile in altri linguaggi.  `let` le associazioni sono ***non modificabile*** per impostazione predefinita, il che significa che una volta un valore o una funzione associata a un nome, non può essere modificata sul posto.  A differenza delle variabili in altre lingue, ovvero si tratta ***modificabile***, vale a dire i relativi valori possono essere modificati in qualsiasi punto nel tempo.  Se è necessaria un'associazione modificabile, è possibile usare `let mutable ...` sintassi.

[!code-fsharp[Immutability](../../samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a>I numeri, valori booleani e stringhe

Come un linguaggio .NET, F# supporta la stessa sottostante [i tipi primitivi](language-reference/primitive-types.md) che esistono in .NET.

Ecco come vari tipi numerici sono rappresentati in F#:

[!code-fsharp[Numbers](../../samples/snippets/fsharp/tour.fs#L49-L68)]

Ecco quali valori booleani ed esecuzione di base per la logica condizionale è simile a:

[!code-fsharp[Bools](../../samples/snippets/fsharp/tour.fs#L142-L152)]

Ed ecco quali basic [stringa](language-reference/strings.md) manipolazione è simile a:

[!code-fsharp[Strings](../../samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a>Tuple

[Le tuple](language-reference/tuples.md) sono un grande vantaggio in F#.  Sono un raggruppamento di valori senza nome, ma ordinati, che possono essere considerati come valori stessi.  Devono essere considerati come valori che vengono aggregati da altri valori.  Hanno diversi scopi, ad esempio comodamente la restituzione di più valori da una funzione o il raggruppamento dei valori per alcuni motivi di praticità ad hoc.

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L186-L203)]

A partire da F# 4.1, è anche possibile creare `struct` Tuple.  Questi anche interagire completamente con le tuple 7 # e Visual Basic 15 C, che sono anche `struct` tuple:

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L205-L218)]

È importante notare che perché `struct` le tuple sono tipi valore, non possono essere convertiti in modo implicito per fare riferimento le tuple, o viceversa.  È necessario convertire in modo esplicito tra una tupla di riferimento e struct.

## <a name="pipelines-and-composition"></a>Pipeline e composizione

Inviare tramite pipe gli operatori, ad esempio `|>` vengono usate spesso durante l'elaborazione dati in F#. Questi operatori sono funzioni che consentono di stabilire una "pipeline" delle funzioni in modo flessibile. Nell'esempio seguente illustra come è possibile sfruttare i vantaggi di questi operatori per compilare una semplice pipeline funzionale:

[!code-fsharp[Pipelines](../../samples/snippets/fsharp/tour.fs#L227-L282)]

L'esempio precedente reso l'utilizzo di numerose funzionalità di F#, tra cui funzioni di elaborazione di elenco, funzioni di prima classe, e [applicazione parziale](language-reference/functions/index.md#partial-application-of-arguments). Sebbene una conoscenza approfondita della ognuno di questi concetti può diventare piuttosto avanzata, dovrebbe essere chiaro con quanta facilità funzioni possono essere utilizzate per elaborare i dati durante la creazione di pipeline.

## <a name="lists-arrays-and-sequences"></a>Elenchi, matrici e sequenze

Elenchi, matrici e sequenze sono tre tipi di raccolta principale nella libreria di base F#.

[Elenca](language-reference/lists.md) sono raccolte ordinate e non modificabile di elementi dello stesso tipo.  Questi sono elenchi collegati singolarmente, ovvero che sono disponibili solo per l'enumerazione, ma una scelta insufficiente per l'accesso casuale e concatenazione se sono grandi.  Questa differenza di elenchi in altri linguaggi più diffusi, che in genere non utilizzano un elenco collegato singolarmente per rappresentare elenchi.

[!code-fsharp[Lists](../../samples/snippets/fsharp/tour.fs#L309-L359)]

[Le matrici](language-reference/arrays.md) sono di dimensioni fisse, *modificabile* raccolte di elementi dello stesso tipo.  Supportano l'accesso casuale veloce degli elementi e sono più veloci rispetto a F# perché tali elenchi sono contigui solo blocchi di memoria.

[!code-fsharp[Arrays](../../samples/snippets/fsharp/tour.fs#L368-L407)]

[Le sequenze](language-reference/sequences.md) sono una serie logica di elementi, tutti dello stesso tipo.  Si tratta di un tipo più generale di elenchi e matrici, in grado di essere il "visualizzazione" di qualsiasi serie logica di elementi.  Sono anche mettere in evidenza perché possono essere ***lazy***, il che significa che gli elementi possono essere calcolati solo quando sono necessari.

[!code-fsharp[Sequences](../../samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a>Funzioni ricorsive

L'elaborazione di raccolte o le sequenze di elementi avviene in genere con [ricorsione](language-reference/functions/index.md#recursive-functions) in F#.  Sebbene F# offre supporto per i cicli e programmazione imperativa, la ricorsione è preferibile perché risulta più semplice garantire la correttezza.

> [!NOTE]
> Nell'esempio seguente usa i criteri di ricerca tramite la `match` espressione.  Questo costrutto fondamentale è trattato più avanti in questo articolo.

[!code-fsharp[RecursiveFunctions](../../samples/snippets/fsharp/tour.fs#L461-L500)]

F# inoltre offre supporto completo per l'ottimizzazione chiamata Tail, che è possibile ottimizzare le chiamate ricorsive in modo che siano il più velocemente un costrutto di ciclo.

## <a name="record-and-discriminated-union-types"></a>Record e i tipi di unione discriminati

Record e i tipi di unione sono due tipi di dati fondamentali usati nel codice F# e sono in genere il modo migliore per rappresentare i dati in un programma F#.  Anche se ciò li rende simile alle classi in altri linguaggi, una delle loro differenze principali è la semantica di uguaglianza strutturale.  Ciò significa che sono confrontabili "in modo nativo" e verificarne l'uguaglianza è semplice: controllare solo se uno è uguale a altro.

[I record](language-reference/records.md) sono un'aggregazione di valori denominati, con i membri facoltativi (ad esempio metodi).  Se si ha familiarità con c# o Java, si dovrebbe risultare simile a oggetti poco o Pojo - solo con l'uguaglianza strutturale e meno conferimento.

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L507-L559)]

A partire da F# 4.1, si può anche rappresentare record come `struct`s.  Questa operazione viene eseguita con il `[<Struct>]` attributo:

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L561-L568)]

[Unioni discriminate (DUs)](language-reference/discriminated-unions.md) sono valori che può essere un numero di moduli denominati o case.  Dati archiviati nel tipo possono essere uno dei diversi valori distinti.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L575-L631)]

È anche possibile usare come DUs *unioni discriminate Case singolo*, alla assistenza tramite i tipi primitivi di modellazione del dominio.  Spesso, le stringhe e altri tipi primitivi vengono usati per rappresentare un elemento e vengono quindi assegnati un significato particolare.  Tuttavia, utilizzando solo la rappresentazione dei dati primitiva può comportare erroneamente assegnando un valore non corretto.  Che rappresenta ogni tipo di informazioni come un'unione case singolo distinta può imporre la correttezza in questo scenario.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L633-L654)]

Come illustrato nell'esempio precedente, per ottenere il valore sottostante in un case singolo unione discriminata, deve esplicitamente unwrap.

Inoltre, DUs supportano anche le definizioni ricorsiva, consentendo di rappresentare facilmente alberi e intrinsecamente dati ricorsivi.  Ad esempio, ecco come è possibile rappresentare un albero di ricerca binario con `exists` e `insert` funzioni.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L656-L683)]

Poiché DUs consentono di rappresentare la struttura ricorsiva dell'albero nel tipo di dati, opera su tale struttura ricorsiva è semplice e garantisce la correttezza.  È anche supportata in Criteri di ricerca, come illustrato di seguito.

Inoltre, è possibile rappresentare come DUs `struct`con il `[<Struct>]` attributo:

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L685-L696)]

Tuttavia, esistono due gli aspetti da tenere presenti quando si esegue questa operazione:

1. Uno struct di unità di database non può essere definito in modo ricorsivo.
2. Uno struct di unità di database deve avere nomi univoci per ognuno dei relativi case.

Impossibilità di seguire il codice precedente comporterà un errore di compilazione.

## <a name="pattern-matching"></a>Criteri di ricerca

[Criteri di corrispondenza](language-reference/pattern-matching.md) è la funzionalità del linguaggio F# che consente la correttezza per l'uso di tipi F#.  Negli esempi precedenti, si sarà probabilmente notato qualche `match x with ...` sintassi.  Questo costrutto consente al compilatore, che può comprendere la "forma" dei tipi di dati, per forzare per conto di tutti i casi possibili quando utilizza un tipo di dati tramite ciò che è noto come esaustivo criteri di ricerca.  Ciò è incredibilmente potente per la correttezza e prosegue senza soste utilizzabile per "solleva" che normalmente sarebbe un problema di runtime in fase di compilazione.

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L705-L742)]

Qualcosa si può notare è l'uso del `_` pattern.  Questo è noto come il [modello carattere jolly](language-reference/pattern-matching.md#wildcard-pattern), che è un concetto viene espresso indicando ", non mi preoccupo qualcosa What ' s".  Anche se utile, è possibile ignorare accidentalmente esaustivo criteri di ricerca e non è più vantaggioso si applicano le regole in fase di compilazione se non si presta attenzione nell'uso `_`.  Risulta particolarmente utile quando non si è interessati determinate parti di un tipo scomposto quando modello corrispondenza o la clausola finale quando si sono enumerati tutti i casi significativi in un'espressione di corrispondenza.

[Criteri attivi](language-reference/active-patterns.md) sono un altro costrutto potente da usare con criteri di ricerca.  Consentono di suddividere i dati di input in moduli personalizzati, scomporli nel sito di chiamata match pattern.  Possono anche essere parametrizzati, consentendo in tal modo per definire la partizione come una funzione.  Continuando l'esempio precedente per supportare i modelli attivi simile al seguente:

[!code-fsharp[ActivePatterns](../../samples/snippets/fsharp/tour.fs#L764-L786)]

## <a name="optional-types"></a>Tipi facoltativi

Un caso speciale di unione discriminata di tipi è il tipo di opzione, è pertanto utile che fa parte della libreria di base F#.

[Il tipo di opzione](language-reference/options.md) costituisce un tipo che rappresenta uno dei due casi: un valore o niente affatto.  Viene usato in qualsiasi scenario in cui un valore può o non può generare da un'operazione specifica.  In questo modo quindi tenere conto per entrambi i casi, rendendolo rappresentano un problema in fase di compilazione anziché a un problema di runtime.  Questi vengono spesso usati per le API in cui `null` viene usato per rappresentare "nothing", invece, eliminando così la necessità di preoccuparsi `NullReferenceException` in molte circostanze.

[!code-fsharp[Options](../../samples/snippets/fsharp/tour.fs#L789-L814)]

## <a name="units-of-measure"></a>Unità di misura

Una funzionalità univoca di sistema di tipi F# è la possibilità di fornire un contesto per i valori letterali numerici tramite unità di misura.

[Unità di misura](language-reference/units-of-measure.md) consentono di associare un tipo numerico a un'unità, ad esempio i contatori, e hanno funzioni eseguiti in unità anziché valori letterali numerici.  Ciò consente al compilatore di verificare che i tipi di valori letterali numerici passati ha senso in un determinato contesto, eliminando così gli errori di runtime associato con questo tipo di attività.

[!code-fsharp[UnitsOfMeasure](../../samples/snippets/fsharp/tour.fs#L817-L842)]

La libreria F# Core definisce molti tipi di unità di sistema internazionale di misura e le conversioni di unità.  Per altre informazioni, consultare il [Microsoft.FSharp.Data.UnitSystems.SI Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d).

## <a name="classes-and-interfaces"></a>Classi e interfacce

F# offre anche il supporto completo per le classi di .NET [interfacce](language-reference/interfaces.md), [classi astratte](language-reference/abstract-classes.md), [ereditarietà](language-reference/inheritance.md)e così via.

[Le classi](language-reference/classes.md) sono tipi che rappresentano gli oggetti .NET, che possono avere proprietà, metodi ed eventi come relativo [membri](language-reference/members/index.md).

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L845-L880)]

Definizione delle classi generiche è altrettanto semplice.

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L883-L908)]

Per implementare un'interfaccia, è possibile usare `interface ... with` sintassi o un [espressione oggetto](language-reference/object-expressions.md).

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L911-L934)]

## <a name="which-types-to-use"></a>Quali tipi di utilizzo

La presenza di classi, record, unioni discriminate e tuple conduce a una domanda importante: quale è opportuno utilizzare?  Come la maggior parte delle tutti gli elementi in uno scenario, la risposta varia a seconda delle circostanze.

Le tuple sono ideali per la restituzione di più valori da una funzione e l'utilizzo di un'aggregazione ad-hoc di valori sotto forma di valore stesso.

I record sono un "gradino sopra" da tuple, visto denominato etichette e il supporto per membri facoltativi.  Sono ideali per una rappresentazione informale di dati in transito tramite il programma.  Perché presentano l'uguaglianza strutturale, essi sono facili da usare con il confronto.

Unioni discriminate sono molti gli usi, ma il vantaggio principale consiste nel poter utilizzarli in combinazione con criteri di ricerca per conto di tutte le possibili "forme" che può avere un tipo di dati.  

Le classi sono ideali per un numero enorme di motivi, ad esempio quando è necessario rappresentare le informazioni e anche associare tali informazioni per la funzionalità.  Come regola generale, quando si dispone di funzionalità che concettualmente è collegata ad alcuni dati, uso di classi e i principi della programmazione orientata a oggetti rappresenta un enorme vantaggio.  Le classi sono anche il tipo di dati preferito quando si interagisce con c# e Visual Basic, poiché questi linguaggi usano classi per quasi tutte le funzioni.

## <a name="next-steps"></a>Passaggi successivi

Ora che si è visto alcune delle principali funzionalità del linguaggio, dovrebbe essere pronti a scrivere i primi programmi F#.  Consulta [introduttiva](tutorials/getting-started/index.md) per informazioni su come configurare l'ambiente di sviluppo e scrivere il codice.

I passaggi successivi per ottenere ulteriori possono essere qualsiasi, ma è consigliabile [Introduzione alla programmazione funzionale in F# ](introduction-to-functional-programming/index.md) per acquisire familiarità con concetti di programmazione funzionale.  Questi saranno essenziali nella creazione di applicazioni affidabili in F#.

Inoltre, consultare il [riferimenti al linguaggio F#](language-reference/index.md) per visualizzare una raccolta completa di contenuti concettuali su F#.
