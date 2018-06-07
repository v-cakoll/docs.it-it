---
title: 'Presentazione di F #'
description: 'Esaminare alcune delle funzionalità chiave di F # in questa presentazione con esempi di codice di linguaggio di programmazione.'
ms.date: 02/28/2018
ms.openlocfilehash: 63c38d59376a148c439482fcf47488fc72b7b8aa
ms.sourcegitcommit: d8bf4976eafe3289275be3811e7cb721bfff7e1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "34753487"
---
# <a name="tour-of-f"></a>Presentazione di F # #

Il modo migliore per imparare a F # è di lettura e scrittura di codice F #.  In questo articolo verrà fungono da illustrano alcune delle funzionalità chiave del linguaggio F # e offrono alcuni frammenti di codice che è possibile eseguire nel computer.  Per ulteriori informazioni sull'impostazione di un ambiente di sviluppo, consultare [Introduzione](tutorials/getting-started/index.md).

Esistono due concetti principali in F #: le funzioni e tipi.  Questa esercitazione verrà illustrate le funzionalità del linguaggio che rientrano in questi due concetti.

## <a name="functions-and-modules"></a>Funzioni e moduli

Gli elementi più importanti di qualsiasi programma F # sono ***funzioni*** organizzati in ***moduli***.  [Le funzioni](language-reference/functions/index.md) operare su input per produrre output e in cui sono organizzate [moduli](language-reference/modules.md), che sono il mezzo principale è raggruppare elementi in F #.  Sono definiti mediante il [ `let` associazione](language-reference/functions/let-bindings.md), che assegna un nome di funzione e definire i relativi argomenti.

[!code-fsharp[BasicFunctions](../../samples/snippets/fsharp/tour.fs#L101-L133)]

`let` le associazioni sono anche viene illustrato come associare un valore a un nome simile a una variabile in altri linguaggi.  `let` le associazioni sono ***immutabile*** per impostazione predefinita, il che significa che una volta un valore o una funzione è associato a un nome, non può essere modificata sul posto.  Ciò si differenzia variabili in altri linguaggi, che sono ***modificabile***, vale a dire i relativi valori possono essere modificati in qualsiasi punto nel tempo.  Se è necessaria un'associazione modificabile, è possibile utilizzare `let mutable ...` sintassi.

[!code-fsharp[Immutability](../../samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a>Numeri, valori booleani e stringhe

Come un linguaggio .NET, F # supporta sottostante stesso [tipi primitivi](language-reference/primitive-types.md) che esiste in .NET.

Ecco come diversi tipi numerici sono rappresentati in F #:

[!code-fsharp[Numbers](../../samples/snippets/fsharp/tour.fs#L49-L68)]

Ecco i valori booleani e logica condizionale di base di eseguire il seguente aspetto:

[!code-fsharp[Bools](../../samples/snippets/fsharp/tour.fs#L142-L152)]

Di seguito è quali basic [stringa](language-reference/strings.md) modifica il seguente aspetto:

[!code-fsharp[Strings](../../samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a>Tuple

[Tuple](language-reference/tuples.md) sono un grande vantaggio in F #.  Si tratta di un raggruppamento di valori senza nome, ma ordinati, che possono essere considerati come valori stessi.  Devono essere considerati come valori che vengono aggregati da altri valori.  Hanno diversi scopi, ad esempio in modo appropriato la restituzione di più valori da una funzione o il raggruppamento dei valori per alcuni motivi di praticità ad hoc.

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L186-L203)]

A partire da F # 4.1, è inoltre possibile creare `struct` Tuple.  Questi anche interagire pienamente con C# 7/Visual Basic 15 tuple, che sono anche `struct` tuple:

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L205-L218)]

È importante notare che poiché `struct` le tuple sono di tipi di valore, non possono essere convertiti in modo implicito per fare riferimento le tuple, o viceversa.  È necessario convertire in modo esplicito tra una tupla di riferimento e struct.

## <a name="pipelines-and-composition"></a>Le pipeline e composizione

Inviare tramite pipe gli operatori, ad esempio `|>` si utilizzano diffusamente durante l'elaborazione dati in F #. Questi operatori sono funzioni che consentono di stabilire "pipeline" delle funzioni in modo flessibile. Nell'esempio seguente illustra come è possibile sfruttare questi operatori per compilare una semplice pipeline funzionale:

[!code-fsharp[Pipelines](../../samples/snippets/fsharp/tour.fs#L227-L282)]

L'esempio precedente apportata usare molte funzionalità di F #, incluse le funzioni l'elaborazione di elenco, le funzioni di prima classe, e [applicazione parziale](language-reference/functions/index.md#partial-application-of-arguments). Anche se una conoscenza approfondita di ognuno di questi concetti può diventare piuttosto avanzata, dovrebbe essere chiaro come facilmente utilizzare funzioni per elaborare i dati durante la compilazione di pipeline.

## <a name="lists-arrays-and-sequences"></a>Elenchi, matrici e sequenze

Elenchi, matrici e sequenze sono tre tipi di raccolta primaria nella libreria di base F #.

[Elenca](language-reference/lists.md) sono ordinate, non modificabile raccolte di elementi dello stesso tipo.  Sono gli elenchi collegati singolarmente, pertanto che sono disponibili solo per l'enumerazione, ma una scelta insufficiente per l'accesso continuo casuale e concatenazione se sono di grandi dimensioni.  Questa differenza di elenchi in altri linguaggi, che in genere non utilizzano un elenco collegato singolarmente per rappresentare elenchi.

[!code-fsharp[Lists](../../samples/snippets/fsharp/tour.fs#L309-L359)]

[Le matrici](language-reference/arrays.md) sono a dimensione fissa *modificabile* raccolte di elementi dello stesso tipo.  Supportano l'accesso casuale veloce degli elementi e sono più veloci rispetto a F # perché tali elenchi sono contigui solo blocchi di memoria.

[!code-fsharp[Arrays](../../samples/snippets/fsharp/tour.fs#L368-L407)]

[Le sequenze](language-reference/sequences.md) sono una serie logica di elementi, tutte dello stesso tipo.  Si tratta di un tipo più generale di elenchi e matrici, in grado di essere la "visualizzazione" in una serie logica di elementi.  Sono anche evidenziati perché possono essere ***lazy***, il che significa che gli elementi possono essere calcolati solo quando sono necessari.

[!code-fsharp[Sequences](../../samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a>Funzioni ricorsive

L'elaborazione di raccolte o le sequenze di elementi avviene in genere con [ricorsione](language-reference/functions/index.md#recursive-functions) in F #.  Sebbene F # offre supporto per i cicli e programmazione imperativa, la ricorsione è preferibile perché è più semplice garantire la correttezza.

>[!NOTE]
Nell'esempio seguente si avvalgono di criteri di ricerca tramite la `match` espressione.  Questo costrutto fondamentale è trattato più avanti in questo articolo.

[!code-fsharp[RecursiveFunctions](../../samples/snippets/fsharp/tour.fs#L461-L500)]

F # dispone inoltre il supporto completo per l'ottimizzazione chiamata Tail, che rappresenta un modo per ottimizzare le chiamate ricorsive in modo che siano il più velocemente un costrutto di ciclo.

## <a name="record-and-discriminated-union-types"></a>Record e i tipi di unioni discriminate

Record e i tipi di unione sono due tipi di dati più importanti utilizzati nel codice F # e sono in genere il modo migliore per rappresentare i dati in un programma F #.  Sebbene ciò le rende simili alle classi in altri linguaggi, uno di loro differenze principali è la semantica di uguaglianza strutturale.  Ciò significa che sono confrontabili "in modo nativo" e verificarne l'uguaglianza è semplice: controllare solo se una è uguale a altra.

[Record](language-reference/records.md) sono un'aggregazione di valori denominati, con membri facoltativi (ad esempio metodi).  Se si ha familiarità con c# o Java, questi dovrebbe risultare simili a POCOs o POJOs - solo con l'uguaglianza strutturale e meno conferimento delle chiavi.

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L507-L559)]

A partire da F # 4.1, si possono anche rappresentare record come `struct`s.  Questa operazione viene eseguita con il `[<Struct>]` attributo:

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L561-L568)]

[Unioni discriminate (DUs)](language-reference/discriminated-unions.md) sono valori che può essere un numero di moduli denominati o case.  Dati archiviati nel tipo possono essere uno dei diversi valori distinti.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L575-L631)]

È inoltre possibile utilizzare DUs come *unioni discriminate Case singolo*, per facilitare la modellazione su tipi primitivi di dominio.  Spesso, stringhe e altri tipi primitivi vengono utilizzati per rappresentare un elemento e pertanto hanno un significato particolare.  Tuttavia, utilizzando solo la rappresentazione di base dei dati può risultare erroneamente l'assegnazione di un valore non corretto.  Che rappresenta ogni tipo di informazioni come unione case singolo distinta può forzare la correttezza in questo scenario.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L633-L654)]

Come illustrato nell'esempio precedente, per ottenere il valore sottostante in un singolo case discriminata unione, è necessario in modo esplicito unwrap.

DUs inoltre supportano inoltre le definizioni di ricorsive, che consente di rappresentare facilmente alberi e intrinsecamente dati ricorsivi.  Ad esempio, ecco come è possibile rappresentare un albero di ricerca binario con `exists` e `insert` funzioni.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L656-L683)]

Poiché DUs consentono di rappresentare la struttura ricorsiva dell'albero nel tipo di dati, opera su tale struttura ricorsiva è semplice e garantisce la correttezza.  È inoltre supportato nei criteri di ricerca, come illustrato di seguito.

Inoltre, è possibile rappresentare DUs come `struct`con il `[<Struct>]` attributo:

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L685-L696)]

Tuttavia, esistono due aspetti da tenere presenti quando si esegue questa operazione:

1. Uno struct DU non può essere definito in modo ricorsivo.
2. Uno struct DU deve avere nomi univoci per ognuno dei relativi case.

L'impossibilità di seguire il precedente comporterà un errore di compilazione.

## <a name="pattern-matching"></a>Criteri di ricerca

[Corrispondenza di schema](language-reference/pattern-matching.md) è la funzionalità del linguaggio F # che consente la correttezza per l'uso di tipi F #.  Negli esempi precedenti, è possibile notare una netta `match x with ...` sintassi.  Questo costrutto consente al compilatore, che è in grado di riconoscere la "forma" tipi di dati, per forzare l'utilizzo di account per tutti i casi possibili quando si utilizza un tipo di dati tramite l'operazione nota come esaustivo criteri di ricerca.  Questo è incredibilmente potente per la correttezza e può essere usato modo intelligente per "accuratezza" che normalmente sarebbe un problema di runtime in fase di compilazione.

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L705-L739)]

È inoltre possibile utilizzare la sintassi abbreviata `function` costrutto per criteri di ricerca, che è utile quando si scrivono funzioni che rendono l'utilizzo di [applicazione parziale](language-reference/functions/index.md#partial-application-of-arguments):

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L741-L759)]

Si è notato consiste nell'utilizzare il `_` modello.  Questo è noto come il [jolly](language-reference/pattern-matching.md#wildcard-pattern), che costituisce un modo per informare "Non è importante che cos'è un elemento".  Sebbene utile, è possibile ignorare accidentalmente esaustivo criteri di ricerca e non è più vantaggioso si applicano le regole in fase di compilazione se non si è attenzione nell'utilizzo di `_`.  Risulta particolarmente utile quando non si è interessati determinate parti di un tipo scomposto quando modello corrispondente, o della clausola finale quando si enumerati tutti i casi significativi in un'espressione di corrispondenza.

[Criteri attivi](language-reference/active-patterns.md) sono un altro costrutto potente da utilizzare come criterio di ricerca.  Questo modo è possibile partizionare i dati di input in moduli personalizzati, li scomposizione nel sito di chiamata di corrispondenza di modello.  Essi possono anche essere con parametri, consentendo in tal modo per definire la partizione come una funzione.  Espansione di esempio precedente per il supporto di criteri attivi simile al seguente:

[!code-fsharp[ActivePatterns](../../samples/snippets/fsharp/tour.fs#L761-L783)]

## <a name="optional-types"></a>Tipi di parametro facoltativi

Un caso speciale di tipi di unione discriminata è il tipo di opzione, questa opzione è utile in modo che è una parte della libreria di base F #.

[Il tipo di opzione](language-reference/options.md) è un tipo che rappresenta uno dei due casi: un valore o nulla affatto.  Viene usato in qualsiasi scenario in cui un valore può o non può generare da un'operazione specifica.  In questo modo quindi di account per entrambi i casi, rendendolo un problema in fase di compilazione anziché di un problema di runtime.  Questi sono spesso utilizzati nelle API in cui `null` viene utilizzata per rappresentare "nothing", invece, eliminando così la necessità di ricorrere `NullReferenceException` in molte circostanze.

[!code-fsharp[Options](../../samples/snippets/fsharp/tour.fs#L791-L811)]

## <a name="units-of-measure"></a>Unità di misura

Una funzionalità univoca di sistema di tipi F # è la possibilità di fornire contesto per i valori letterali numerici tramite unità di misura.

[Unità di misura](language-reference/units-of-measure.md) consentono di associare un tipo numerico a una singola unità, ad esempio metri, e hanno funzioni svolgere il lavoro sulle unità anziché valori letterali numerici.  In questo modo il compilatore di verificare che i tipi di valori letterali numerici passati senso in un determinato contesto, eliminando così gli errori di runtime associato a questo tipo di lavoro.

[!code-fsharp[UnitsOfMeasure](../../samples/snippets/fsharp/tour.fs#L818-L839)]

La libreria di base F # definisce molti tipi di unità di isolamento e conversioni di unità.  Per ulteriori informazioni, consultare il [Microsoft.FSharp.Data.UnitSystems.SI Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d).

## <a name="classes-and-interfaces"></a>Classi e interfacce

F # contiene inoltre il supporto completo per le classi .NET, [interfacce](language-reference/interfaces.md), [classi astratte](language-reference/abstract-classes.md), [ereditarietà](language-reference/inheritance.md)e così via.

[Le classi](language-reference/classes.md) sono tipi che rappresentano gli oggetti .NET, che può avere proprietà, metodi ed eventi come relativo [membri](language-reference/members/index.md).

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L848-L877)]

È inoltre molto semplice definizione di classi generiche.

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L884-L905)]

Per implementare un'interfaccia, è possibile utilizzare `interface ... with` sintassi o [espressione oggetto](language-reference/object-expressions.md).

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L912-L931)]

## <a name="which-types-to-use"></a>Quali tipi di utilizzo

La presenza di tuple, record, unioni discriminate e classi comporta una domanda più importante: quale deve essere usata?  Ad esempio la maggior parte delle tutti gli elementi di vita, la risposta varia a seconda delle circostanze.

Le tuple sono ideali per la restituzione di più valori da una funzione e l'utilizzo di un'aggregazione ad hoc di valori come un valore stesso.

I record sono un "step up" da tuple, con denominato etichette e il supporto per membri facoltativi.  Costituiscono la soluzione ottimale per una rappresentazione basso-conferimento delle chiavi di dati in transito tramite il programma.  Perché hanno l'uguaglianza strutturale, sono facili da utilizzare con il confronto.

Unioni discriminate sono diversi modi, ma il vantaggio principale è in grado di utilizzarli in combinazione con criteri di ricerca per tenere conto delle possibili "forme" che può avere un tipo di dati.  

Le classi sono ideali per un elevato numero di motivi, ad esempio quando è necessario rappresentare le informazioni e anche associare tali informazioni per la funzionalità.  Come regola generale, quando si dispone di funzionalità che è concettualmente collegata ad alcuni dati, utilizzando le classi e i principi della programmazione orientata a oggetti è un grande vantaggio.  Classi sono anche il tipo di dati preferito per l'interazione con c# e Visual Basic, come questi linguaggi usare classi per quasi tutte le funzioni.

## <a name="next-steps"></a>Passaggi successivi

Ora che si è visto, alcune delle principali funzionalità del linguaggio, dovrebbe essere pronti per la scrittura di programmi F # prima!  Estrarre [Introduzione](tutorials/getting-started/index.md) per informazioni su come configurare l'ambiente di sviluppo e di scrivere codice.

I passaggi successivi per l'apprendimento più possono essere scelto liberamente, ma è consigliabile [funzioni come valori di prima classe](introduction-to-functional-programming/functions-as-first-class-values.md) <!--[Introduction to Functional Programming in F#](introduction-to-functional-programming/index.md)--> per acquisire familiarità con concetti di programmazione funzionale.  Questi saranno essenziali per la creazione di programmi affidabili in F #.

Inoltre, estrarre il [riferimenti al linguaggio F #](language-reference/index.md) per visualizzare un insieme completo di contenuto concettuale in F #.
