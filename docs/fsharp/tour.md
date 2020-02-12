---
title: Panoramica di F#
description: Esaminare alcune delle principali funzionalità del linguaggio in questa presentazione con esempi di codice di programmazione F#.
ms.date: 02/09/2020
ms.openlocfilehash: ac2eef40e2dbc494e41a9760f0a70edb0f7ce399
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124572"
---
# <a name="tour-of-f"></a>Panoramica di F\#

Il modo migliore per informazioni su F# è per leggere e scrivere codice F#. Questo articolo verrà agire come un tour dettagliato alcune delle principali funzionalità del linguaggio F# e offrono alcuni frammenti di codice che è possibile eseguire nel computer. Per informazioni sulla configurazione di un ambiente di sviluppo, vedere [Introduzione](get-started/index.md).

Esistono due concetti primari in F#: tipi e funzioni.  In questa presentazione vengono enfatizzate le funzionalità del linguaggio che rientrano in questi due concetti.

## <a name="executing-the-code-online"></a>Esecuzione del codice online

Se non è stato F# installato nel computer, è possibile eseguire tutti gli esempi nel browser con [try F# su webassembly](https://tryfsharp.fsbolero.io/). Fable è un dialetto di F# che viene eseguito direttamente nel browser. Per visualizzare gli esempi che seguono in REPL, vedere **esempi > apprendere > Panoramica di F#**  nella barra dei menu a sinistra di Fable repl.

## <a name="functions-and-modules"></a>Funzioni e moduli

Le parti più importanti di qualsiasi F# programma sono ***funzioni*** organizzate in ***moduli***.  Le [funzioni](./language-reference/functions/index.md) eseguono operazioni sugli input per produrre output e sono organizzate in [moduli](./language-reference/modules.md), il modo principale per raggruppare gli elementi in F#.  Vengono definiti tramite il [binding`let`](./language-reference/functions/let-bindings.md), che assegna un nome alla funzione e ne definisce gli argomenti.

[!code-fsharp[BasicFunctions](~/samples/snippets/fsharp/tour.fs#L101-L133)]

le associazioni `let` sono anche il modo in cui si associa un valore a un nome, simile a una variabile in altre lingue.  per impostazione predefinita, le associazioni `let` non sono ***modificabili*** , il che significa che, una volta associato un valore o una funzione a un nome, non è possibile modificarlo sul posto.  Diversamente dalle variabili in altri linguaggi, che sono ***modificabili***, il che significa che i valori possono essere modificati in qualsiasi momento.  Se è necessaria un'associazione modificabile, è possibile usare `let mutable ...` sintassi.

[!code-fsharp[Immutability](~/samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a>Numeri, valori booleani e stringhe

Come linguaggio .NET, F# supporta gli stessi [tipi primitivi](language-reference/basic-types.md) sottostanti presenti in .NET.

Ecco come vari tipi numerici sono rappresentati in F#:

[!code-fsharp[Numbers](~/samples/snippets/fsharp/tour.fs#L49-L68)]

Di seguito sono riportati i valori booleani e la logica condizionale di base simile alla seguente:

[!code-fsharp[Bools](~/samples/snippets/fsharp/tour.fs#L142-L152)]

Di seguito è illustrata la manipolazione di base delle [stringhe](./language-reference/strings.md) :

[!code-fsharp[Strings](~/samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a>Tuple

Le [Tuple](./language-reference/tuples.md) rappresentano un grosso problema F#in.  Si tratta di un raggruppamento di valori senza nome, ma ordinati, che possono essere considerati come valori stessi.  È possibile considerarli come valori aggregati da altri valori.  Hanno molti utilizzi, ad esempio la restituzione di più valori da una funzione o il raggruppamento di valori per alcune comodità ad hoc.

[!code-fsharp[Tuples](~/samples/snippets/fsharp/tour.fs#L186-L203)]

È anche possibile creare `struct` Tuple.  Questi elementi interagiscono anche completamente con le tuple C# 7/Visual Basic 15, che sono anche `struct` Tuple:

[!code-fsharp[Tuples](~/samples/snippets/fsharp/tour.fs#L205-L218)]

È importante notare che poiché le tuple `struct` sono tipi valore, non possono essere convertite in modo implicito in tuple di riferimento o viceversa.  È necessario eseguire una conversione esplicita tra un riferimento e una tupla struct.

## <a name="pipelines-and-composition"></a>Pipeline e composizione

Gli operatori pipe come `|>` vengono ampiamente utilizzati durante l'elaborazione dei dati F#in. Questi operatori sono funzioni che consentono di stabilire "pipeline" di funzioni in modo flessibile. Nell'esempio seguente viene illustrato come sfruttare questi operatori per creare una semplice pipeline funzionale:

[!code-fsharp[Pipelines](~/samples/snippets/fsharp/tour.fs#L227-L282)]

Nell'esempio precedente sono state usate numerose funzionalità di F#, tra cui funzioni di elaborazione di elenchi, funzioni di prima classe e [applicazioni parziali](./language-reference/functions/index.md#partial-application-of-arguments). Sebbene una conoscenza approfondita di ognuno di questi concetti possa diventare un po' avanzata, è opportuno chiarire il modo in cui le funzioni possono essere usate per elaborare i dati durante la creazione di pipeline.

## <a name="lists-arrays-and-sequences"></a>Elenchi, matrici e sequenze

Elenchi, matrici e sequenze sono tre tipi di raccolta principale nella libreria di base F#.

Gli [elenchi](./language-reference/lists.md) sono insiemi ordinati e non modificabili di elementi dello stesso tipo.  Sono elenchi collegati singolarmente, il che significa che sono destinati a un'enumerazione, ma una scelta scarsa per l'accesso casuale e la concatenazione se sono di grandi dimensioni.  Diversamente dagli elenchi in altri linguaggi comuni, che in genere non usano un elenco collegato singolarmente per rappresentare gli elenchi.

[!code-fsharp[Lists](~/samples/snippets/fsharp/tour.fs#L309-L359)]

Le [matrici](./language-reference/arrays.md) sono raccolte *modificabili* di dimensioni fisse di elementi dello stesso tipo.  Supportano l'accesso casuale veloce degli elementi e sono più veloci rispetto a F# perché tali elenchi sono contigui solo blocchi di memoria.

[!code-fsharp[Arrays](~/samples/snippets/fsharp/tour.fs#L368-L407)]

Le [sequenze](./language-reference/sequences.md) sono una serie logica di elementi, tutti dello stesso tipo.  Si tratta di un tipo più generale rispetto a elenchi e matrici, in grado di essere la "visualizzazione" in qualsiasi serie logica di elementi.  Si distinguono anche perché possono essere ***Lazy***, il che significa che gli elementi possono essere calcolati solo quando sono necessari.

[!code-fsharp[Sequences](~/samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a>Funzioni ricorsive

L'elaborazione di raccolte o sequenze di elementi viene in genere eseguita con F#la [ricorsione](./language-reference/functions/index.md#recursive-functions) in.  Sebbene F# offre supporto per i cicli e programmazione imperativa, la ricorsione è preferibile perché risulta più semplice garantire la correttezza.

> [!NOTE]
> Nell'esempio seguente vengono usati i criteri di ricerca tramite l'espressione `match`.  Questo costrutto fondamentale è trattato più avanti in questo articolo.

[!code-fsharp[RecursiveFunctions](~/samples/snippets/fsharp/tour.fs#L461-L500)]

F# inoltre offre supporto completo per l'ottimizzazione chiamata Tail, che è possibile ottimizzare le chiamate ricorsive in modo che siano il più velocemente un costrutto di ciclo.

## <a name="record-and-discriminated-union-types"></a>Tipi di Unione record e discriminati

Record e i tipi di unione sono due tipi di dati fondamentali usati nel codice F# e sono in genere il modo migliore per rappresentare i dati in un programma F#.  Sebbene ciò li renda simili alle classi di altri linguaggi, una delle principali differenze consiste nel fatto che hanno semantica di uguaglianza strutturale.  Ciò significa che sono "a livello nativo" paragonabili e l'uguaglianza è semplice: è sufficiente verificare se una è uguale all'altra.

I [record](./language-reference/records.md) sono un'aggregazione di valori denominati, con membri facoltativi (ad esempio metodi).  Se si ha familiarità C# con o Java, questi dovrebbero essere simili a poco o POJO, solo con l'uguaglianza strutturale e meno cerimonia.

[!code-fsharp[Records](~/samples/snippets/fsharp/tour.fs#L507-L559)]

È inoltre possibile rappresentare i record come struct. Questa operazione viene eseguita con l'attributo `[<Struct>]`:

[!code-fsharp[Records](~/samples/snippets/fsharp/tour.fs#L561-L568)]

Le [unioni discriminate (DUs)](./language-reference/discriminated-unions.md) sono valori che possono essere costituiti da un numero di forme o case denominati.  I dati archiviati nel tipo possono essere uno dei diversi valori distinti.

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L575-L631)]

È anche possibile usare DUs come *unioni discriminate a caso singolo*, per semplificare la modellazione del dominio rispetto ai tipi primitivi.  Spesso, le stringhe e altri tipi primitivi vengono usati per rappresentare qualcosa e hanno quindi un significato particolare.  Tuttavia, l'utilizzo solo della rappresentazione primitiva dei dati può comportare l'assegnazione erronea di un valore errato.  In questo scenario, rappresentando ogni tipo di informazioni come un'Unione a singolo caso distinta è possibile applicare la correttezza.

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L633-L654)]

Come illustrato nell'esempio precedente, per ottenere il valore sottostante in un'unione discriminata a caso singolo, è necessario annullare in modo esplicito il wrapping.

Inoltre, DUs supporta anche le definizioni ricorsive, consentendo di rappresentare facilmente gli alberi e i dati ricorsivi intrinsecamente.  Ad esempio, di seguito viene illustrato come è possibile rappresentare un albero di ricerca binario con funzioni `exists` e `insert`.

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L656-L683)]

Poiché gli elementi DUs consentono di rappresentare la struttura ricorsiva dell'albero nel tipo di dati, l'utilizzo di questa struttura ricorsiva è semplice e garantisce la correttezza.  È anche supportata in criteri di ricerca, come illustrato di seguito.

Inoltre, è possibile rappresentare DUs come `struct`s con l'attributo `[<Struct>]`:

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L685-L696)]

Quando si esegue questa operazione, è tuttavia necessario tenere presente due aspetti fondamentali:

1. Un struct DU non può essere definito in modo ricorsivo.
2. Un struct DU deve avere nomi univoci per ogni case.

Se non si segue, il risultato precedente comporterà un errore di compilazione.

## <a name="pattern-matching"></a>Criteri di ricerca

[Criteri di ricerca è la](./language-reference/pattern-matching.md) funzionalità del linguaggio che consente la correttezza per il F# funzionamento sui F# tipi.  Negli esempi precedenti è probabile che si sia notato un po' di `match x with ...` sintassi.  Questo costrutto consente al compilatore, che può comprendere la "forma" dei tipi di dati, di tenere conto di tutti i casi possibili quando si usa un tipo di dati tramite il tipo di criteri di ricerca esaustivo.  Questo è incredibilmente potente per correttezza e può essere usato in modo intelligente per "sollevare" ciò che normalmente costituisce un problema di runtime in fase di compilazione.

[!code-fsharp[PatternMatching](~/samples/snippets/fsharp/tour.fs#L705-L742)]

Un elemento notato è l'uso del modello di `_`.  Questo è noto come [modello con caratteri jolly](./language-reference/pattern-matching.md#wildcard-pattern), che è un modo per indicare che non è rilevante.  Sebbene sia pratico, è possibile ignorare accidentalmente i criteri di ricerca esaustivi e non trarre più vantaggio dalle imposte in fase di compilazione se non si presta attenzione a usare `_`.  Si tratta di una scelta ottimale quando non si è interessati a determinate parti di un tipo scomposto quando si verificano criteri di ricerca o alla clausola finale dopo aver enumerato tutti i case significativi in un'espressione di criteri di ricerca.

Nell'esempio seguente, il `_` caso viene usato quando un'operazione di analisi ha esito negativo.

[!code-fsharp[PatternMatching](~/samples/snippets/fsharp/tour.fs#L744-L762)]

I [criteri attivi](./language-reference/active-patterns.md) sono un altro costrutto potente da usare con i criteri di ricerca.  Consentono di partizionare i dati di input in moduli personalizzati, decomponendo i dati nel sito di chiamata di corrispondenza dei modelli.  Possono anche essere parametrizzati, consentendo così di definire la partizione come una funzione.  L'espansione dell'esempio precedente per supportare i modelli attivi è simile alla seguente:

[!code-fsharp[ActivePatterns](~/samples/snippets/fsharp/tour.fs#L764-L786)]

## <a name="optional-types"></a>Tipi facoltativi

Un caso speciale di unione discriminata di tipi è il tipo di opzione, è pertanto utile che fa parte della libreria di base F#.

[Il tipo di opzione](./language-reference/options.md) è un tipo che rappresenta uno dei due casi seguenti: un valore o nulla.  Viene usato in qualsiasi scenario in cui un valore può essere o meno derivato da una determinata operazione.  In questo modo, è necessario tenere conto di entrambi i casi, rendendolo un problema in fase di compilazione piuttosto che un problema in fase di esecuzione.  Questi vengono spesso usati nelle API in cui `null` viene usato per rappresentare "Nothing", evitando in tal modo la necessità di preoccuparsi `NullReferenceException` in molte circostanze.

[!code-fsharp[Options](~/samples/snippets/fsharp/tour.fs#L789-L814)]

## <a name="units-of-measure"></a>Unità di misura

Una funzionalità univoca di sistema di tipi F# è la possibilità di fornire un contesto per i valori letterali numerici tramite unità di misura.

Le [unità di misura](./language-reference/units-of-measure.md) consentono di associare un tipo numerico a un'unità, ad esempio contatori, e hanno funzioni che eseguono operazioni su unità anziché valori letterali numerici.  Ciò consente al compilatore di verificare che i tipi di valori letterali numerici passati abbiano senso in un determinato contesto, eliminando così gli errori di runtime associati a tale tipo di lavoro.

[!code-fsharp[UnitsOfMeasure](~/samples/snippets/fsharp/tour.fs#L817-L842)]

La libreria F# Core definisce molti tipi di unità di sistema internazionale di misura e le conversioni di unità.  Per altre informazioni, vedere lo [spazio dei nomi Microsoft.FSharp.Data.UnitSystems.si](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d).

## <a name="classes-and-interfaces"></a>Classi e interfacce

F#dispone inoltre di supporto completo per le classi .NET, le [interfacce](./language-reference/interfaces.md), [le classi astratte](./language-reference/abstract-classes.md), l' [ereditarietà](./language-reference/inheritance.md)e così via.

[Le classi](./language-reference/classes.md) sono tipi che rappresentano oggetti .NET che possono avere proprietà, metodi ed eventi come [membri](./language-reference/members/index.md).

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L845-L880)]

Anche la definizione di classi generiche è molto semplice.

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L883-L908)]

Per implementare un'interfaccia, è possibile utilizzare la sintassi `interface ... with` o un' [espressione di oggetto](./language-reference/object-expressions.md).

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L911-L934)]

## <a name="which-types-to-use"></a>Tipi da usare

La presenza di classi, record, unioni discriminate e Tuple comporta una domanda importante: quale è consigliabile usare?  Come la maggior parte della vita, la risposta dipende dalle circostanze.

Le tuple sono ottime per la restituzione di più valori da una funzione e l'uso di un'aggregazione ad hoc di valori come valore stesso.

I record sono "step up" da tuple, con etichette denominate e supporto per i membri facoltativi.  Sono ottime per la rappresentazione dei dati in transito nel programma.  Poiché presentano un'uguaglianza strutturale, è facile da usare con il confronto.

Le unioni discriminate dispongono di molti utilizzi, ma il vantaggio principale è quello di poterle usare insieme ai criteri di ricerca per tenere conto di tutte le possibili "forme" che possono avere i dati.  

Le classi sono ottime per un numero elevato di motivi, ad esempio quando è necessario rappresentare le informazioni e associare tali informazioni alla funzionalità.  Come regola generale, quando si hanno funzionalità che sono concettualmente legate ad alcuni dati, l'uso di classi e dei principi della programmazione orientata a oggetti costituisce un grande vantaggio.  Le classi sono anche il tipo di dati preferito quando si C# interoperano con e Visual Basic, in quanto questi linguaggi utilizzano le classi per quasi tutti gli elementi.

## <a name="next-steps"></a>Passaggi successivi

Ora che si è visto alcune delle principali funzionalità del linguaggio, dovrebbe essere pronti a scrivere i primi programmi F#.  Per informazioni su come configurare l'ambiente di sviluppo e scrivere codice, vedere [Introduzione](get-started/index.md) .

I passaggi successivi per saperne di più possono essere quelli desiderati, ma è consigliabile [Introduzione alla programmazione funzionale F# in](./introduction-to-functional-programming/index.md) per acquisire familiarità con i concetti fondamentali di programmazione funzionale.  Questi saranno essenziali nella creazione di applicazioni affidabili in F#.

Consultare anche le [ F# ](./language-reference/index.md) informazioni di riferimento sul linguaggio per visualizzare una raccolta completa di contenuti concettuali F#in.
