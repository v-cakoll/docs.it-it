---
title: Novità di C# 7.0 - Guida a C#
description: Panoramica delle nuove funzionalità nella versione 7.0 del linguaggio C#.
ms.date: 12/21/2016
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: 0646eaa999579e5347007dd71defcc643c19c7f9
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/22/2019
ms.locfileid: "56665082"
---
# <a name="whats-new-in-c-70"></a>Novità di C# 7.0

C# 7.0 aggiunge diverse nuove funzionalità al linguaggio C#:
* [Variabili `out`](#out-variables)
    - È possibile dichiarare valori `out` inline come argomenti al metodo in cui vengono usati.
* [Tuple](#tuples)
    - È possibile creare tipi leggeri e senza nome che contengono più campi pubblici. I compilatori e gli strumenti dell'IDE comprendono la semantica di questi tipi.
* [Variabili discard](#discards)
    - Le variabili discard sono variabili temporanee di sola scrittura usate nelle assegnazioni quando non si è interessati al valore assegnato. Sono particolarmente utili per la decostruzione di tuple e tipi definiti dall'utente, nonché per la chiamata di metodi con i parametri `out`.
* [Criteri di ricerca](#pattern-matching)
    - È possibile creare una logica di salto condizionato basata su tipi e valori arbitrari dei membri di tali tipi.
* [Variabili locali e valori restituiti `ref`](#ref-locals-and-returns)
    - Le variabili locali del metodo e i valori restituiti possono essere riferimenti ad altre opzioni di memorizzazione.
* [Funzioni locali](#local-functions)
    - È possibile annidare funzioni all'interno di altre funzioni per limitarne l'ambito e visibilità.
* [Più membri con corpo di espressione](#more-expression-bodied-members)
    - L'elenco dei membri che possono essere creati con le espressioni è cresciuto.
* [Espressioni `throw`](#throw-expressions)
    - È possibile generare eccezioni in costrutti di codice che in precedenza non erano consentiti poiché `throw` era un'istruzione. 
* [Tipi restituiti asincroni generalizzati](#generalized-async-return-types)
    - I metodi dichiarati con il modificatore `async` possono restituire altri tipi oltre a `Task` e `Task<T>`.
* [Miglioramenti della sintassi dei valori letterali numerici](#numeric-literal-syntax-improvements)
    - Nuovi token migliorano la leggibilità delle costanti numeriche.

Tutte le funzionalità sono descritte nelle sezioni rimanenti di questo argomento. Per ogni funzionalità verranno illustrati i concetti di base e si apprenderà la sintassi. Si noterà che alcuni scenari di esempio in cui viene usata la nuova funzionalità aumentano la produttività dello sviluppatore. 

## <a name="out-variables"></a>Variabili `out`

La sintassi esistente che supporta i parametri `out` è stata migliorata in questa versione.  

In precedenza era necessario separare la dichiarazione della variabile out e la relativa inizializzazione in due istruzioni diverse:

[!code-csharp[OutVariableOldStyle](../../../samples/snippets/csharp/new-in-7/program.cs#03_OutVariableOldStyle "classic out variable declaration")]

Ora è possibile dichiarare le variabili `out` nell'elenco di argomenti di una chiamata al metodo, anziché scrivere un'istruzione di dichiarazione separata:

[!code-csharp[OutVariableDeclarations](../../../samples/snippets/csharp/new-in-7/program.cs#01_OutVariableDeclarations "Out variable declarations")]

Si consiglia di specificare il tipo della variabile `out` per maggiore chiarezza, come illustrato in precedenza. Il linguaggio tuttavia supporta l'uso di una variabile locale tipizzata in modo implicito:

[!code-csharp[OutVarVariableDeclarations](../../../samples/snippets/csharp/new-in-7/program.cs#02_OutVarVariableDeclarations "Implicitly typed Out variable")]

* Il codice è più facile da leggere. 
    - Si dichiara la variabile out nel punto in cui viene usata, non in una riga precedente.
* Non è necessario assegnare un valore iniziale.
    - Dichiarando la variabile `out` nel punto in cui viene usata in una chiamata al metodo, non è possibile usarla accidentalmente prima che venga assegnata.

L'uso più comune di questa funzionalità è il modello `Try`. In questo modello un metodo restituisce un valore `bool` che indica l'esito positivo o negativo e una variabile `out` che indica il risultato se il metodo ha esito positivo.

Quando si usa la dichiarazione di variabile `out` la variabile dichiarata "fuoriesce" nell'ambito esterno dell'istruzione if. In questo modo è possibile usare la variabile in un secondo momento:

```csharp
if (!int.TryParse(input, out int result))
{    
    return null;
}

return result;
```

## <a name="tuples"></a>Tuple

> [!NOTE]
> Le nuove funzionalità delle tuple richiedono i tipi <xref:System.ValueTuple>.
> È necessario aggiungere il pacchetto NuGet [ `System.ValueTuple` ](https://www.nuget.org/packages/System.ValueTuple/) per usarlo nelle piattaforme che non includono i tipi.
>
> È simile ad altre funzionalità del linguaggio basate sui tipi resi disponibili nel framework. Alcuni esempi sono `async` e `await`, basati sull'interfaccia `INotifyCompletion`, e LINQ, basato su `IEnumerable<T>`. Tuttavia, il meccanismo di distribuzione sta cambiando perché .NET sta diventando più indipendente dalla piattaforma. .NET Framework potrebbe non essere sempre distribuito secondo la stessa cadenza del compilatore del linguaggio. Quando nuove funzionalità del linguaggio si basano su nuovi tipi, tali tipi saranno disponibili come pacchetti NuGet al momento della distribuzione delle funzionalità del linguaggio. Una volta che questi nuovi tipi vengono aggiunti all'API standard .NET e distribuiti come parte del framework, il requisito del pacchetto NuGet viene rimosso.

C# offre una sintassi completa per le classi e gli struct usati per spiegare la finalità della progettazione. In alcuni casi tale sintassi richiede ulteriore lavoro con vantaggi minimi. Spesso è possibile scrivere metodi che richiedono una struttura semplice contenente più di un elemento dati. Per supportare questi scenari, sono state aggiunte *tuple* a C#. Le tuple sono strutture di dati leggere che contengono più campi per rappresentare i membri dati.
I campi non vengono convalidati e non è possibile definire i propri metodi

> [!NOTE]
> Le tuple erano già disponibili prima di C# 7.0, ma in modo poco efficiente e senza supporto del linguaggio.
> Questo significava poter fare riferimento agli elementi delle tuple solo come `Item1`, `Item2` e così via. C# 7.0 introduce il supporto del linguaggio per le tuple, che consente nomi semantici per i campi di una tupla con tipi di tupla nuovi e più efficienti.

È possibile creare una tupla assegnando un valore a ogni membro:

[!code-csharp[UnnamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#04_UnnamedTuple "Unnamed tuple")]

L'assegnazione consente di creare una tupla i cui membri sono `Item1` e `Item2`, che è possibile usare in modo analogo a <xref:System.Tuple>. È possibile modificare la sintassi per creare una tupla che fornisce nomi semantici per ognuno dei membri della tupla:

[!code-csharp[NamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#05_NamedTuple "Named tuple")]

La tupla `namedLetters` contiene campi detti `Alpha` e `Beta`. Tali nomi esistono solo in fase di compilazione e non vengono mantenuti, ad esempio, quando si esamina la tupla tramite reflection in fase di esecuzione.

In un'assegnazione di tupla è anche possibile specificare i nomi dei campi sul lato destro dell'assegnazione:

[!code-csharp[ImplicitNamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#06_ImplicitNamedTuple "Implicitly named tuple")]

È possibile specificare nomi per i campi sia a sinistra che a destra dell'assegnazione:

[!code-csharp[NamedTupleConflict](../../../samples/snippets/csharp/new-in-7/program.cs#07_NamedTupleConflict "Named tuple conflict")]

La riga precedente genera un avviso, `CS8123`, che indica che i nomi sul lato destro dell'assegnazione, `Alpha` e `Beta`, vengono ignorati perché sono in conflitto con i nomi sul lato sinistro, `First` e `Second`.

Gli esempi precedenti illustrano la sintassi di base per dichiarare le tuple. Le tuple sono particolarmente utili come tipi restituiti per i metodi `private` e `internal`. Le tuple forniscono una sintassi semplice per consentire a tali metodi di restituire più valori distinti: Si salva il lavoro di creazione di una `class` o uno `struct` che definisce il tipo restituito. Non è necessario creare un nuovo tipo.

La creazione di una tupla è più efficiente e più produttiva.
È una sintassi più semplice e leggera per definire una struttura dei dati che contiene più di un valore. Il metodo di esempio riportato di seguito restituisce i valori minimo e massimo trovati in una sequenza di interi:

[!code-csharp[TupleReturningMethod](../../../samples/snippets/csharp/new-in-7/program.cs#08_TupleReturningMethod "Tuple returning method")]

Usare le tuple in questo modo offre diversi vantaggi:

* Si salva il lavoro di creazione di una `class` o uno `struct` che definisce il tipo restituito. 
* Non è necessario creare un nuovo tipo.
* L'ottimizzazione del linguaggio consente di evitare la chiamata ai metodi <xref:System.Tuple.Create``1(``0)>.

La dichiarazione per il metodo specifica i nomi per i campi della tupla restituita. Quando si chiama il metodo, il valore restituito è una tupla i cui campi sono `Max` e `Min`:

[!code-csharp[CallingTupleMethod](../../../samples/snippets/csharp/new-in-7/program.cs#09_CallingTupleMethod "Calling a tuple returning method")]

Può rendersi necessario decomprimere i membri di una tupla che sono stati restituiti da un metodo.  In questo caso è possibile dichiarare variabili separate per ogni valore nella tupla. Questa operazione è detta *decostruzione* della tupla:

[!code-csharp[CallingWithDeconstructor](../../../samples/snippets/csharp/new-in-7/program.cs#10_CallingWithDeconstructor "Deconstructing a tuple")]

È anche possibile specificare una decostruzione simile per qualsiasi tipo in .NET. L'operazione si esegue scrivendo un metodo `Deconstruct` come membro della classe. Tale metodo `Deconstruct` specifica un set di argomenti `out` per ognuna delle proprietà da estrarre. Considerare questa classe `Point` che specifica un metodo di decostruzione che estrae le coordinate `X` e `Y`:

[!code-csharp[PointWithDeconstruction](../../../samples/snippets/csharp/new-in-7/point.cs#11_PointWithDeconstruction "Point with deconstruction method")]
 
È possibile estrarre i singoli campi assegnando un oggetto `Point` a una tupla:

[!code-csharp[DeconstructPoint](../../../samples/snippets/csharp/new-in-7/program.cs#12_DeconstructPoint "Deconstruct a point")]

Non si è vincolati dai nomi definiti nel metodo `Deconstruct`. È possibile rinominare le variabili di estrazione come parte dell'assegnazione:  

[!code-csharp[DeconstructNames](../../../samples/snippets/csharp/new-in-7/program.cs#13_DeconstructNames "Deconstruct with new names")]

Informazioni più approfondite sulle tuple sono disponibili nell'[argomento relativo ai tipi di tuple](../tuples.md).

## <a name="discards"></a>Variabili discard

Spesso durante lo decostruzione di una tupla o la chiamata di un metodo con parametri `out`, si è costretti a definire una variabile con un valore non significativo e che non si intende usare. C# aggiunge il supporto delle *variabili discard* per gestire questo scenario. Una variabile discard è una variabile di sola scrittura il cui nome è `_` (carattere di sottolineatura). È possibile assegnare tutti i valori che non occorre mantenere alla singola variabile. Una variabile discard è simile a una variabile non assegnata. Con l'eccezione dell'istruzione di assegnazione, la variabile discard non può essere usata nel codice.

Le variabili discard sono supportate negli scenari seguenti:

* Per la decostruzione di tuple o tipi definiti dall'utente.

* Per la chiamata di metodi con parametri [out](../language-reference/keywords/out-parameter-modifier.md).

* In operazioni con criteri di ricerca con le istruzioni [is](../language-reference/keywords/is.md) e [switch](../language-reference/keywords/switch.md).

* Come identificatore autonomo quando si vuole identificare in modo esplicito il valore di un'assegnazione come variabile discard.

L'esempio seguente definisce un metodo `QueryCityDataForYears` che restituisce una tupla con 6 elementi che contiene i dati di una città per due anni diversi. La chiamata del metodo nell'esempio è interessata solo ai due valori di popolazione restituiti dal metodo e quindi gestisce i valori rimanenti nella tupla come variabili discard quando decostruisce la tupla.

[!code-csharp[Tuple-discard](../../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

Per altre informazioni, vedere [Variabili discard](../discards.md).

## <a name="pattern-matching"></a>Criteri di ricerca

L'uso dei *criteri di ricerca* consente di implementare l'invio dei metodi per le proprietà diverse dal tipo di un oggetto. Probabilmente si ha già familiarità con l'invio dei metodi basato sul tipo di un oggetto. Nella programmazione orientata agli oggetti i metodi virtuali e di override offrono la sintassi del linguaggio per implementare l'invio dei metodi basato sul tipo di un oggetto. Le classi di base e derivate consentono diverse implementazioni. Le espressioni di criteri di ricerca estendono questo concetto in modo che sia possibile implementare facilmente modelli di invio simili per i tipi e gli elementi di dati che non sono correlati attraverso una gerarchia di ereditarietà. 

I criteri di ricerca supportano le espressioni `is` e le espressioni `switch`. Ognuno consente di esaminare un oggetto e le relative proprietà per determinare se l'oggetto soddisfa il criterio ricercato. Usare la parola chiave `when` per specificare regole aggiuntive per il modello.

### <a name="is-expression"></a>Espressione `is`

L'espressione con criterio `is` estende il noto [operatore `is`](../language-reference/keywords/is.md#pattern-matching-with-is) per l'esecuzione di query su un oggetto oltre il relativo tipo.

Iniziamo con uno scenario semplice a cui verranno aggiunte delle funzionalità per spiegare in che modo le espressioni di criteri di ricerca semplificano gli algoritmi usati con i tipi non correlati. Si inizierà con un metodo che calcola la somma di un numero di tirate di dadi:

[!code-csharp[SumDieRolls](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#14_SumDieRolls "Sum die rolls")]

È possibile vedere rapidamente che è necessario trovare la somma delle tirate di dadi dove alcune delle tirate sono fatte con più dadi. Parte della sequenza di input può essere costituita da più risultati anziché un singolo numero:

[!code-csharp[SumDieRollsWithGroups](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#15_SumDieRollsWithGroups "Sum die rolls with groups")]

L'espressione con il criterio `is` funziona piuttosto bene in questo scenario. Come parte del controllo del tipo, si scrive un'inizializzazione delle variabili. In questo modo viene creata una nuova variabile del tipo di runtime convalidato.

Man mano che questi scenari vengono estesi, si può scoprire che si stanno compilando più istruzioni `if` e `else if`. Quando la situazione diventa difficile da gestire, probabilmente si vorrà passare alle espressioni con il criterio `switch`.

### <a name="switch-statement-updates"></a>Aggiornamenti dell'istruzione `switch`

L'*espressione di ricerca* ha una sintassi familiare, basata sull'istruzione `switch` che fa già parte del linguaggio C#. Supponiamo di convertire il codice esistente in modo da usare un'espressione di ricerca prima di aggiungere nuovi casi: 

[!code-csharp[SumUsingSwitch](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#16_SumUsingSwitch "Sum using switch")]

Le espressioni di ricerca hanno una sintassi leggermente diversa dalle espressioni `is`, in cui si dichiara il tipo e la variabile all'inizio dell'espressione `case`.

Le espressioni di ricerca supportano anche le costanti. Ciò consente di risparmiare tempo eseguendo il factoring dei casi semplici:

[!code-csharp[SwitchWithConstants](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#17_SwitchWithConstants "Switch with constants")]

Il codice riportato sopra aggiunge casi per `0` come caso speciale di `int` e `null` come caso speciale quando non vi è alcun input. Questo esempio dimostra un nuovo importante aspetto delle espressioni con criterio switch: l'ordine delle espressioni `case` ora viene tenuto in considerazione. Il caso `0` deve essere visualizzato prima del caso `int` generale. In caso contrario, il primo criterio di corrispondenza sarebbe il caso `int`, anche se il valore è `0`. Se le espressioni di ricerca vengono accidentalmente ordinate in modo tale che un caso successivo sia già stato gestito, il compilatore applica un contrassegno e genera un errore.

Questo stesso comportamento abilita il caso speciale per una sequenza di input vuota.
Come si può vedere, il caso per un oggetto `IEnumerable` con elementi deve apparire prima del caso `IEnumerable` generale.

Questa versione ha inoltre aggiunto un caso `default`. Il caso `default` viene sempre valutato per ultimo, indipendentemente dall'ordine in cui appare nell'origine. Per questo motivo, la convenzione è inserire il caso `default` per ultimo.

Infine, si aggiungerà un ultimo `case` per un nuovo stile di dado. Alcuni giochi usano dadi percentili per rappresentare intervalli di numeri più ampi. 

> [!NOTE]
> Due dadi percentili a 10 facce possono rappresentare qualsiasi numero da 0 a 99. Un dado ha le facce etichettate con `00`, `10`, `20`,... `90`. L'altro dado ha le facce etichettate con `0`, `1`, `2`, ... `9`. Sommare i valori dei due dadi e si potrà avere qualsiasi numero compreso tra 0 e 99.

Per aggiungere questo tipo di dado alla raccolta, per prima cosa definire un tipo per rappresentare il dado percentile. La proprietà `TensDigit` archivia i valori `0`, `10`, `20` fino a `90`:

[!code-csharp[18_PercentileDice](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#18_PercentileDice "Percentile Die type")]

Aggiungere quindi un'espressione di ricerca `case` per il nuovo tipo:

[!code-csharp[SwitchWithNewTypes](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#19_SwitchWithNewTypes "Include Percentile Die type")]

La nuova sintassi per le espressioni di criteri di ricerca, più chiara e concisa, semplifica la creazione degli algoritmi di invio basati sul tipo di un oggetto o su altre proprietà. Le espressioni di criteri di ricerca abilitano questi costrutti per i tipi di dati non correlati per ereditarietà.

Altre informazioni sui criteri di ricerca sono disponibili nell'argomento dedicato ai [criteri di ricerca in C#](../pattern-matching.md).

## <a name="ref-locals-and-returns"></a>Variabili locali e valori restituiti per riferimento

Questa funzionalità abilita algoritmi che usano e restituiscono riferimenti a variabili definite altrove. Un esempio è lavorare con matrici di grandi dimensioni e trovare un'unica posizione con determinate caratteristiche. Un metodo restituirebbe due indici per una singola posizione nella matrice:

[!code-csharp[FindReturningIndices](../../../samples/snippets/csharp/new-in-7/MatrixSearch.cs#20_FindReturningIndices "Find returning indices")]

Esistono molti problemi con questo codice. Prima di tutto, è un metodo pubblico che restituisce una tupla. Il linguaggio la supporta, ma sono preferibili i tipi definiti dall'utente (classi o struct) per le API pubbliche.

In secondo luogo, questo metodo restituisce gli indici all'elemento nella matrice.
Ciò induce i chiamanti a scrivere codice che usa tali indici per dereferenziare la matrice e modificare un singolo elemento:

[!code-csharp[UpdateItemFromIndices](../../../samples/snippets/csharp/new-in-7/program.cs#21_UpdateItemFromIndices "Update Item From Indices")]

È più opportuno scrivere un metodo che restituisce un *riferimento* all'elemento della matrice che si vuole modificare. Nelle versioni precedenti questa operazione era possibile solo usando codice unsafe e restituendo un puntatore a un oggetto `int`.

Verrà ora analizzata una serie di modifiche per illustrare la funzionalità delle variabili locali ref e la procedura di creazione di un metodo che restituisce un riferimento all'archiviazione interna.
Si apprenderanno inoltre le regole per i valori restituiti ref e le variabili locali ref che consentono di evitare usi impropri della funzionalità.

Iniziare modificando la dichiarazione di metodo `Find` in modo che restituisca un oggetto `ref int` anziché una tupla. Quindi, modificare l'istruzione return in modo che restituisca il valore memorizzato nella matrice anziché i due indici:

```csharp
// Note that this won't compile. 
// Method declaration indicates ref return,
// but return statement specifies a value return.
public static ref int Find2(int[,] matrix, Func<int, bool> predicate)
{
    for (int i = 0; i < matrix.GetLength(0); i++)
        for (int j = 0; j < matrix.GetLength(1); j++)
            if (predicate(matrix[i, j]))
                return matrix[i, j];
    throw new InvalidOperationException("Not found");
}
```

Quando si dichiara che un metodo restituisce una variabile `ref` è inoltre necessario aggiungere la parola chiave `ref` a ogni istruzione return. Ciò indica la restituzione per riferimento e consente agli sviluppatori che leggono il codice di ricordare in seguito che il metodo restituisce per riferimento:

[!code-csharp[FindReturningRef](../../../samples/snippets/csharp/new-in-7/MatrixSearch.cs#22_FindReturningRef "Find returning by reference")]

Ora che il metodo restituisce un riferimento al valore integer della matrice, è necessario modificare il punto in cui viene chiamato.  La dichiarazione `var` significa che `valItem` è ora un oggetto `int` anziché una tupla:

[!code-csharp[AssignRefReturnToValue](../../../samples/snippets/csharp/new-in-7/program.cs#23_AssignRefReturnToValue "Assign ref return to value")]

La seconda istruzione `WriteLine` nell'esempio precedente stampa il valore `42`, non `24`. La variabile `valItem` è `int`, non `ref int`. La parola chiave `var` consente al compilatore di specificare il tipo, ma non di aggiungere in modo implicito il modificatore `ref`. Il valore a cui fa riferimento `ref return` viene invece *copiato* nella variabile sul lato sinistro dell'assegnazione. La variabile non è una variabile locale `ref`.

Per ottenere il risultato desiderato, è necessario aggiungere il modificatore `ref` alla dichiarazione di variabile locale per fare in modo che la variabile sia un riferimento quando il valore restituito è un riferimento:

[!code-csharp[AssignRefReturn](../../../samples/snippets/csharp/new-in-7/program.cs#24_AssignRefReturn "Assign ref return")]

A questo punto, la seconda istruzione `WriteLine` nell'esempio precedente consente di stampare il valore `24`, che indica che la memorizzazione nella matrice è stata modificata. La variabile locale è stata dichiarata con il modificatore `ref` e accetterà un valore restituito `ref`. È necessario inizializzare una variabile `ref` quando viene dichiarata, non è possibile separare la dichiarazione e l'inizializzazione.

Il linguaggio C# usa altre tre regole per evitare usi impropri delle variabili locali e dei valori restituiti `ref`:

* Non è possibile assegnare un valore restituito del metodo standard a una variabile locale `ref`.
    - Questo non consente istruzioni come `ref int i = sequence.Count();`
* Non è possibile restituire un oggetto `ref` a una variabile la cui durata non si estende oltre l'esecuzione del metodo.
    - Ciò significa che non è possibile restituire un riferimento a una variabile locale o a una variabile con ambito simile.
* Non è possibile usare variabili locali e valori restituiti `ref` con i metodi asincroni.
    - Il compilatore non può stabilire se la variabile a cui si fa riferimento è stata impostata sul valore finale quando il metodo asincrono restituisce il controllo.

L'aggiunta di variabili locali e valori restituiti ref abilita algoritmi più efficienti, evitando la copia dei valori o l'esecuzione ripetuta di operazioni di dereferenziazione.

L'aggiunta di `ref` al valore restituito è una [modifica compatibile a livello di codice sorgente](version-update-considerations.md#source-compatible-changes). Il codice esistente viene compilato, ma il valore restituito ref viene copiato quando è assegnato. I chiamanti devono aggiornare l'archiviazione per il valore restituito in una variabile locale `ref` per archiviare il valore restituito come riferimento.

Per altre informazioni, vedere l'articolo relativo alla [parola chiave ref](../language-reference/keywords/ref.md).

## <a name="local-functions"></a>Funzioni locali

Molte progettazioni per le classi includono metodi che vengono chiamati da un solo percorso. Si tratta di metodi privati aggiuntivi che rendono più circoscritto e mirato ogni metodo. Tuttavia, possono complicare la comprensione di una classe quando viene letta la prima volta. Questi metodi devono essere compresi fuori dal contesto del singolo percorso chiamante.

In queste progettazioni le *funzioni locali* consentono di dichiarare metodi all'interno del contesto di un altro metodo. In questo modo è più semplice per i lettori della classe verificare se il metodo locale viene chiamato solo dal contesto in cui è dichiarato.

Esistono due casi di utilizzo molto comuni per le funzioni locali: i metodi iterator pubblici e i metodi async pubblici. Entrambi i tipi di metodi generano codice che segnala gli errori in ritardo rispetto a quanto previsto dai programmatori. Nel caso dei metodi iterator tutte le eccezioni vengono riscontrate solo quando si chiama il codice che enumera la sequenza restituita. Nel caso dei metodi async tutte le eccezioni vengono riscontrate solo quando è atteso l'oggetto restituito `Task`.

Iniziamo con un metodo iterator:

[!code-csharp[IteratorMethod](../../../samples/snippets/csharp/new-in-7/Iterator.cs#25_IteratorMethod "Iterator method")]

Esaminare il codice seguente che chiama il metodo iterator in modo non corretto:

[!code-csharp[CallIteratorMethod](../../../samples/snippets/csharp/new-in-7/program.cs#26_CallIteratorMethod "Call iterator method")]

L'eccezione viene generata quando viene eseguita l'iterazione di `resultSet`, non quando viene creato `resultSet`.
In questo esempio di dimensioni ridotte la maggior parte degli sviluppatori può diagnosticare rapidamente il problema. Tuttavia, nelle codebase più grandi il codice che crea un iteratore spesso non è così vicino al codice che enumera i risultati. È possibile eseguire il refactoring del codice in modo che il metodo pubblico convalidi tutti gli argomenti e un metodo privato generi l'enumerazione:

[!code-csharp[IteratorMethodRefactored](../../../samples/snippets/csharp/new-in-7/Iterator.cs#27_IteratorMethodRefactored "Iterator method refactored")]

La versione sottoposta a refactoring genera immediatamente eccezioni perché il metodo pubblico non è un metodo iterator. Solo il metodo privato usa la sintassi `yield return`. Tuttavia, esistono potenziali problemi con questo refactoring. Il metodo privato deve essere chiamato solo dal metodo di interfaccia pubblico, perché in caso contrario viene ignorata la convalida di tutti gli argomenti.
I lettori della classe devono individuare questo fatto leggendo l'intera classe e cercando eventuali altri riferimenti al metodo `alphabetSubsetImplementation`.

È possibile rendere più chiara la finalità della progettazione dichiarando `alphabetSubsetImplementation` come funzione locale all'interno del metodo API pubblico:

[!code-csharp[22_IteratorMethodLocal](../../../samples/snippets/csharp/new-in-7/Iterator.cs#28_IteratorMethodLocal "Iterator method with local function")]

La versione precedente indica chiaramente che viene fatto riferimento al metodo locale solo nel contesto del metodo esterno. Le regole per le funzioni locali garantiscono inoltre che uno sviluppatore non possa chiamare accidentalmente la funzione locale da un'altra posizione nella classe accidentalmente e ignorare la convalida degli argomenti.

La stessa tecnica può essere usata con i metodi `async` per garantire che le eccezioni risultanti dalla convalida degli argomenti vengano generate prima che inizino le attività asincrone:

[!code-csharp[TaskExample](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Task returning method with local function")]

> [!NOTE]
> Alcune delle progettazioni supportate dalle funzioni locali possono essere eseguite anche usando le *espressioni lambda*. Per chi è interessato sono disponibili [altre informazioni sulle differenze](../local-functions-vs-lambdas.md)

## <a name="more-expression-bodied-members"></a>Più membri con corpo di espressione

In C# 6 sono stati introdotti i [membri con corpo di espressione](csharp-6.md#expression-bodied-function-members) per le funzioni membro e le proprietà di sola lettura. C# 7.0 amplia la gamma di membri consentiti che possono essere implementati come espressioni. In C# 7.0 è possibile implementare *costruttori*, *finalizzatori* e funzioni di accesso `get` e `set` per *proprietà* e *indicizzatori*. Nel codice riportato di seguito vengono illustrati esempi di ogni tipo di membro:

[!code-csharp[ExpressionBodiedMembers](../../../samples/snippets/csharp/new-in-7/expressionmembers.cs#36_ExpressionBodiedEverything "new expression-bodied members")]

> [!NOTE]
> In questo esempio non è necessario un finalizzatore, ma viene incluso per illustrare la sintassi. Non implementare un finalizzatore nella classe a meno che non sia necessario per rilasciare risorse non gestite. È inoltre consigliabile usare la classe <xref:System.Runtime.InteropServices.SafeHandle> anziché gestire direttamente le risorse non gestite.

Questi nuovi percorsi per i membri con corpo di espressione rappresentano un importante punto cardine per il linguaggio C#: Queste funzionalità sono state implementate da membri della community che lavorano sul progetto open source [Roslyn](https://github.com/dotnet/Roslyn).

La modifica di un metodo in un membro con corpo di espressione è una [modifica compatibile a livello binario](version-update-considerations.md#binary-compatible-changes).

## <a name="throw-expressions"></a>Espressioni throw

In C# `throw` è sempre stata un'istruzione. Poiché `throw` è un'istruzione, non un'espressione, vi sono costrutti di C# in cui non è possibile usarla. Sono incluse le espressioni condizionali, le espressioni Null ridondanti e alcune espressioni lambda. L'aggiunta di membri con corpo di espressione consente di aggiungere più posizioni in cui le espressioni `throw` possono risultare utili. Per fare in modo che sia possibile scrivere uno di questi costrutti, C# 7.0 introduce le *espressioni throw*.

La sintassi è la stessa che è sempre stata usata per le istruzioni `throw`. L'unica differenza è che ora è possibile l'inserimento in nuove posizioni, ad esempio in un'espressione condizionale:

[!code-csharp[Throw_ExpressionExample](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#37_Throw_ExpressionExample "conditional throw expressions")]

Questa funzionalità consente l'uso di espressioni throw nelle espressioni di inizializzazione:

[!code-csharp[ThrowInInitialization](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#38_ThrowInInitialization "conditional throw expressions")]

In precedenza le inizializzazioni dovevano avvenire in un costruttore, con le istruzioni throw nel corpo del costruttore:


[!code-csharp[ThrowInConstructor](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#39_ThrowInConstructor "throw statements")]

> [!NOTE]
> Entrambi i costrutti precedenti causano la generazione di eccezioni durante la costruzione di un oggetto. Spesso sono situazioni difficili da risolvere.
> Per questo motivo, non sono consigliate le progettazioni che generano eccezioni durante la costruzione.

## <a name="generalized-async-return-types"></a>Tipi restituiti asincroni generalizzati

La restituzione di un oggetto `Task` dai metodi asincroni può introdurre colli di bottiglia delle prestazioni in determinati percorsi. `Task` è un tipo di riferimento, quindi usarlo significa allocare un oggetto. Nei casi in cui un metodo dichiarato con il modificatore `async` restituisce un risultato memorizzato nella cache o viene completato in modo sincrono, le allocazioni aggiuntive possono diventare impegnative in termini di tempo nelle sezioni di codice critiche per le prestazioni. Possono diventare molto onerose se si verificano in cicli ridotti.

La nuova funzionalità del linguaggio consente ai metodi asincroni di restituire altri tipi oltre a `Task`, `Task<T>` e `void`. Il tipo restituito deve comunque essere conforme al modello asincrono ovvero deve essere accessibile un metodo `GetAwaiter`. Per fare un esempio concreto, il tipo `ValueTask` è stato aggiunto a .NET Framework per consentire l'uso di questa nuova funzionalità del linguaggio: 

[!code-csharp[UsingValueTask](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#30_UsingValueTask "Using ValueTask")]

> [!NOTE]
> È necessario aggiungere il pacchetto NuGet [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) per usare il tipo <xref:System.Threading.Tasks.ValueTask%601>.

Una semplice ottimizzazione sarebbe usare `ValueTask` in posizioni in cui prima sarebbe stato usato `Task`. Tuttavia, se si vogliono eseguire manualmente altre ottimizzazioni, è possibile memorizzare nella cache i risultati delle attività asincrone e usarli di nuovo nelle chiamate successive. Lo struct `ValueTask` include un costruttore con un parametro `Task` in modo che sia possibile costruire un oggetto `ValueTask` dal valore restituito di qualsiasi metodo asincrono esistente:

[!code-csharp[AsyncOptimizedValueTask](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#31_AsyncOptimizedValueTask "Return async result or cached value")]

Come si raccomanda sempre a proposito delle prestazioni, è necessario creare un benchmark di entrambe le versioni prima di apportare modifiche su larga scala al codice.

Quando il valore restituito è la destinazione di un'istruzione `await`, la modifica di un'API da <xref:System.Threading.Tasks.Task%601> in <xref:System.Threading.Tasks.ValueTask%601> è una [modifica compatibile a livello di codice sorgente](version-update-considerations.md#source-compatible-changes). In generale, la modifica in `ValueTask` non lo è.

## <a name="numeric-literal-syntax-improvements"></a>Miglioramenti della sintassi dei valori letterali numerici

La lettura non corretta delle costanti numeriche può rendere più difficile la comprensione del codice quando viene letto per la prima volta. Ciò si verifica spesso quando questi numeri vengono usati come maschere di bit o altri elementi simbolici anziché come valori numerici. C# 7.0 include due nuove funzionalità per semplificare la scrittura dei numeri in modo che siano più leggibili per l'uso previsto: *valori letterali binari* e *separatori di cifre*.

Ogni volta che si creano maschere di bit o che una rappresentazione binaria di un numero rende il codice più leggibile, scrivere il numero in formato binario:

[!code-csharp[BinaryConstants](../../../samples/snippets/csharp/new-in-7/Program.cs#32_BinaryConstants "Binary constants")]

`0b` all'inizio della costante indica che il numero viene scritto come numero binario.

I numeri binari possono essere molto lunghi, quindi spesso è più semplice visualizzare gli schemi di bit introducendo il carattere `_` come separatore di cifre:

[!code-csharp[ThousandSeparators](../../../samples/snippets/csharp/new-in-7/Program.cs#33_ThousandSeparators "Thousands separators")]

Il separatore di cifre può apparire ovunque nella costante. Per i numeri in base 10, è più comune usarlo come separatore delle migliaia:

[!code-csharp[LargeIntegers](../../../samples/snippets/csharp/new-in-7/Program.cs#34_LargeIntegers "Large integer")]

Il separatore di cifre può essere usato anche con i tipi `decimal`, `float` e `double`:

[!code-csharp[OtherConstants](../../../samples/snippets/csharp/new-in-7/Program.cs#35_OtherConstants "non-integral constants")]

Nel loro insieme, è possibile dichiarare le costanti numeriche ottimizzando la leggibilità.
