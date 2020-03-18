---
title: Novità di C# 7.0 - Guida a C#
description: Panoramica delle nuove funzionalità nella versione 7.0 del linguaggio C#.
ms.date: 02/20/2019
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: a6ac5c00ceb2ce8e5e56e2a86a8cde937d5108e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399693"
---
# <a name="whats-new-in-c-70"></a>Novità di C# 7.0

C# 7.0 aggiunge diverse nuove funzionalità al linguaggio C#:

- [`out`Variabili](#out-variables)
  - È possibile dichiarare valori `out` inline come argomenti per il metodo in cui vengono usati.
- [Tuple](#tuples)
  - È possibile creare tipi leggeri e senza nome che contengono più campi pubblici. I compilatori e gli strumenti dell'IDE comprendono la semantica di questi tipi.
- [Variabili discard](#discards)
  - Le variabili discard sono variabili temporanee di sola scrittura usate nelle assegnazioni quando non si è interessati al valore assegnato. Sono utili soprattutto per la decostruzione di tuple e tipi definiti dall'utente, nonché per la chiamata di metodi con i parametri `out`.
- [Criteri](#pattern-matching)
  - È possibile creare una logica di salto condizionato basata su tipi e valori arbitrari dei membri di tali tipi.
- [`ref`gente del posto e ritorni](#ref-locals-and-returns)
  - Le variabili locali del metodo e i valori restituiti possono essere riferimenti ad altre opzioni di memorizzazione.
- [Funzioni locali](#local-functions)
  - È possibile annidare funzioni all'interno di altre funzioni per limitarne l'ambito e visibilità.
- [Più membri con corpo di espressione](#more-expression-bodied-members)
  - L'elenco dei membri che possono essere creati con le espressioni è cresciuto.
- [`throw`Espressioni](#throw-expressions)
  - È possibile generare eccezioni in costrutti di codice che in precedenza non erano consentiti, perché `throw` era un'istruzione.
- [Tipi restituiti asincroni generalizzati](#generalized-async-return-types)
  - I metodi dichiarati con il modificatore `async` possono restituire altri tipi oltre a `Task` e `Task<T>`.
- [Miglioramenti della sintassi dei valori letterali numerici](#numeric-literal-syntax-improvements)
  - Nuovi token migliorano la leggibilità delle costanti numeriche.

La parte restante di questo articolo illustra una panoramica di ogni funzionalità. Per ogni funzionalità verranno illustrati i concetti di base e si apprenderà la sintassi. È possibile esplorare queste funzionalità nell'ambiente in uso tramite lo strumento globale `dotnet try`:

1. Installare lo strumento globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).
1. Clonare il repository [dotnet/try-samples](https://github.com/dotnet/try-samples).
1. Impostare la directory corrente sulla sottodirectory *csharp7* per il repository *try-samples*.
1. Eseguire `dotnet try`.

## <a name="out-variables"></a>Variabili `out`

La sintassi esistente che supporta i parametri `out` è stata migliorata in questa versione. Ora è possibile dichiarare le variabili `out` nell'elenco di argomenti di una chiamata al metodo, anziché scrivere un'istruzione di dichiarazione separata:

[!code-csharp[OutVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVariableDeclarations "Out variable declarations")]

Si consiglia di specificare il tipo della variabile `out` per maggiore chiarezza, come illustrato in precedenza. Il linguaggio tuttavia supporta l'uso di una variabile locale tipizzata in modo implicito:

[!code-csharp[OutVarVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVarVariableDeclarations "Implicitly typed Out variable")]

- Il codice è più facile da leggere.
  - Si dichiara la variabile out nel punto in cui viene usata, non in una riga precedente.
- Non è necessario assegnare un valore iniziale.
  - Se si dichiara la variabile `out` nel punto in cui viene usata in una chiamata al metodo, non è possibile usarla accidentalmente prima che venga assegnata.

## <a name="tuples"></a>Tuple

C# offre una sintassi completa per le classi e gli struct usati per spiegare la finalità della progettazione. In alcuni casi tale sintassi richiede ulteriore lavoro con vantaggi minimi. Spesso è possibile scrivere metodi che richiedono una struttura semplice contenente più di un elemento dati. Per supportare questi scenari, sono state aggiunte *tuple* a C#. Le tuple sono strutture di dati leggere che contengono più campi per rappresentare i membri dati.
I campi non vengono convalidati e non è possibile definire i propri metodi

> [!NOTE]
> Le tuple erano già disponibili prima di C# 7.0, ma in modo poco efficiente e senza supporto del linguaggio.
> Questo significava poter fare riferimento agli elementi delle tuple solo come `Item1`, `Item2` e così via. C# 7.0 introduce il supporto del linguaggio per le tuple, che consente nomi semantici per i campi di una tupla con tipi di tupla nuovi e più efficienti.

È possibile creare una tupla assegnando un valore a ogni membro e fornendo facoltativamente nomi semantici per ogni membro della tupla:

[!code-csharp[NamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#NamedTuple "Named tuple")]

La tupla `namedLetters` contiene campi detti `Alpha` e `Beta`. Tali nomi esistono solo in fase di compilazione e non vengono mantenuti, ad esempio, quando si esamina la tupla tramite reflection in fase di esecuzione.

In un'assegnazione di tupla è anche possibile specificare i nomi dei campi sul lato destro dell'assegnazione:

[!code-csharp[ImplicitNamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#ImplicitNamedTuple "Implicitly named tuple")]

Può rendersi necessario decomprimere i membri di una tupla che sono stati restituiti da un metodo.  In questo caso è possibile dichiarare variabili separate per ogni valore nella tupla. Questa operazione di decompressione è detta *decostruzione* della tupla:

[!code-csharp[CallingWithDeconstructor](~/samples/snippets/csharp/new-in-7/program.cs#CallingWithDeconstructor "Deconstructing a tuple")]

È anche possibile specificare una decostruzione simile per qualsiasi tipo in .NET. Si scrive un metodo `Deconstruct` come membro della classe. Tale metodo `Deconstruct` specifica un set di argomenti `out` per ognuna delle proprietà da estrarre. Considerare questa classe `Point` che specifica un metodo di decostruzione che estrae le coordinate `X` e `Y`:

[!code-csharp[PointWithDeconstruction](~/samples/snippets/csharp/new-in-7/point.cs#PointWithDeconstruction "Point with deconstruction method")]

È possibile estrarre i singoli campi assegnando un oggetto `Point` a una tupla:

[!code-csharp[DeconstructPoint](~/samples/snippets/csharp/new-in-7/program.cs#DeconstructPoint "Deconstruct a point")]

Informazioni più approfondite sulle tuple sono disponibili nell'[articolo relativo alle tuple](../tuples.md).

## <a name="discards"></a>Variabili discard

Spesso durante lo decostruzione di una tupla o la chiamata di un metodo con parametri `out`, si è costretti a definire una variabile con un valore non significativo e che non si intende usare. C# aggiunge il supporto delle *variabili discard* per gestire questo scenario. Una variabile discard è una variabile di sola scrittura il cui nome è `_` (carattere di sottolineatura). È possibile assegnare tutti i valori che non occorre mantenere alla singola variabile. Una variabile discard è simile a una variabile non assegnata. Con l'eccezione dell'istruzione di assegnazione, la variabile discard non può essere usata nel codice.

Le variabili discard sono supportate negli scenari seguenti:

- Per la decostruzione di tuple o tipi definiti dall'utente.
- Per la chiamata di metodi con parametri [out](../language-reference/keywords/out-parameter-modifier.md).
- In operazioni con criteri di ricerca con le istruzioni [is](../language-reference/keywords/is.md) e [switch](../language-reference/keywords/switch.md).
- Come identificatore autonomo quando si vuole identificare in modo esplicito il valore di un'assegnazione come variabile discard.

L'esempio seguente definisce un metodo `QueryCityDataForYears` che restituisce una tupla con 6 elementi che contiene i dati di una città per due anni diversi. La chiamata del metodo nell'esempio è interessata solo ai due valori di popolazione restituiti dal metodo e quindi gestisce i valori rimanenti nella tupla come variabili discard quando decostruisce la tupla.

[!code-csharp[Tuple-discard](~/samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

Per altre informazioni, vedere [Variabili discard](../discards.md).

## <a name="pattern-matching"></a>Corrispondenza dei criteri

L'uso dei *criteri di ricerca* consente di implementare l'invio dei metodi per le proprietà diverse dal tipo di un oggetto. Probabilmente si ha già familiarità con l'invio dei metodi basato sul tipo di un oggetto. Nella programmazione orientata agli oggetti i metodi virtuali e di override offrono la sintassi del linguaggio necessaria per implementare l'invio dei metodi basato sul tipo di un oggetto. Le classi di base e derivate consentono diverse implementazioni.
Le espressioni di criteri di ricerca estendono questo concetto in modo che sia possibile implementare facilmente modelli di invio simili per i tipi e gli elementi di dati che non sono correlati attraverso una gerarchia di ereditarietà.

I criteri di ricerca supportano le espressioni `is` e le espressioni `switch`. Ognuno consente di esaminare un oggetto e le relative proprietà per determinare se l'oggetto soddisfa il criterio ricercato. Usare la parola chiave `when` per specificare regole aggiuntive per il modello.

L'espressione `is` di modello estende [ `is` l'operatore](../language-reference/keywords/is.md#pattern-matching-with-is) familiare per eseguire una query su un oggetto sul relativo tipo e assegnare il risultato in un'istruzione. Il codice seguente controlla se una variabile è un `int` e in tal caso lo aggiunge alla somma corrente:

```csharp
if (input is int count)
    sum += count;
```

Il breve esempio precedente dimostra i miglioramenti all'espressione `is`. È possibile eseguire test rispetto a tipi di valore e tipi di riferimento e assegnare il risultato positivo a una nuova variabile del tipo corretto.

L'espressione di ricerca switch ha una sintassi familiare, basata sull'istruzione `switch` che fa già parte del linguaggio C#. L'istruzione switch aggiornata presenta vari nuovi costrutti:

- Il tipo che gestisce un'espressione `switch` non è più limitato a tipi integrali, tipi `Enum`, `string` o a un tipo nullable corrispondente a uno di questi tipi. Ora è possibile usare qualsiasi tipo.
- È possibile eseguire il test del tipo dell'espressione `switch` in ogni etichetta `case`. Come per l'espressione `is`, è possibile assegnare una nuova variabile a tale tipo.
- È possibile aggiungere una clausola `when` per eseguire ulteriori test delle condizioni per tale variabile.
- L'ordine delle etichette `case` ora è importante. Viene eseguito il primo ramo che registra una corrispondenza; gli altri rami vengono ignorati.

Il codice seguente dimostra queste nuove funzionalità:

```csharp
public static int SumPositiveNumbers(IEnumerable<object> sequence)
{
    int sum = 0;
    foreach (var i in sequence)
    {
        switch (i)
        {
            case 0:
                break;
            case IEnumerable<int> childSequence:
            {
                foreach(var item in childSequence)
                    sum += (item > 0) ? item : 0;
                break;
            }
            case int n when n > 0:
                sum += n;
                break;
            case null:
                throw new NullReferenceException("Null found in sequence");
            default:
                throw new InvalidOperationException("Unrecognized type");
        }
    }
    return sum;
}
```

- `case 0:` è il criterio costante familiare.
- `case IEnumerable<int> childSequence:` è un criterio del tipo.
- `case int n when n > 0:` è un criterio del tipo con una condizione `when` aggiuntiva.
- `case null:` è il criterio null.
- `default:` è il case predefinito già noto.

Altre informazioni sui criteri di ricerca sono disponibili nell'argomento [Criteri di ricerca](../pattern-matching.md).

## <a name="ref-locals-and-returns"></a>Variabili locali e valori restituiti per riferimento

Questa funzionalità abilita algoritmi che usano e restituiscono riferimenti a variabili definite altrove. Un esempio è lavorare con matrici di grandi dimensioni e trovare un'unica posizione con determinate caratteristiche. Il metodo seguente restituisce un **riferimento** a questa risorsa di archiviazione nella matrice:

[!code-csharp[FindReturningRef](~/samples/snippets/csharp/new-in-7/MatrixSearch.cs#FindReturningRef "Find returning by reference")]

È possibile dichiarare il valore restituito come `ref` e modificare tale valore nella matrice, come illustrato nel codice seguente:

[!code-csharp[AssignRefReturn](~/samples/snippets/csharp/new-in-7/Program.cs#AssignRefReturn "Assign ref return")]

Il linguaggio C# usa diverse regole per evitare l'uso improprio delle variabili locali `ref` e dei valori restituiti:

- È necessario aggiungere la parola chiave `ref` alla firma del metodo e a tutte le istruzioni `return` in un metodo.
  - In questo modo appare chiaro che le restituzioni avvengono in base al riferimento nell'intero metodo.
- Un elemento `ref return` può essere assegnato a una variabile value o a una variabile `ref`.
  - Il chiamante determina se il valore restituito viene copiato oppure no. L'omissione del modificatore `ref` quando si assegna il valore restituito indica che il chiamante desidera una copia del valore e non un riferimento alla risorsa di archiviazione.
- Non è possibile assegnare un valore restituito del metodo standard a una variabile locale `ref`.
  - Questo non consente istruzioni come `ref int i = sequence.Count();`
- Non è possibile restituire un elemento `ref` a una variabile la cui durata è limitata alla durata di esecuzione del metodo.
  - Ciò significa che non è possibile restituire un riferimento a una variabile locale o a una variabile con ambito simile.
- Non è possibile usare variabili locali e valori restituiti `ref` con i metodi asincroni.
  - Il compilatore non può stabilire se la variabile a cui si fa riferimento è stata impostata sul valore finale quando il metodo asincrono restituisce il controllo.

L'aggiunta di variabili locali e valori restituiti ref abilita algoritmi più efficienti, evitando la copia dei valori o l'esecuzione ripetuta di operazioni di dereferenziazione.

L'aggiunta di `ref` al valore restituito è una [modifica compatibile a livello di codice sorgente](version-update-considerations.md#source-compatible-changes). Il codice esistente viene compilato, ma il valore restituito ref viene copiato quando è assegnato. I chiamanti devono aggiornare l'archiviazione per il valore restituito in una variabile locale `ref` per archiviare il valore restituito come riferimento.

Per altre informazioni, vedere l'articolo relativo alla [parola chiave ref](../language-reference/keywords/ref.md).

## <a name="local-functions"></a>Funzioni locali

Molte progettazioni per le classi includono metodi che vengono chiamati da un solo percorso. Si tratta di metodi privati aggiuntivi che rendono più circoscritto e mirato ogni metodo. Le *funzioni locali* consentono di dichiarare metodi all'interno del contesto di un altro metodo. Le funzioni locali rendono più semplice per i lettori della classe verificare se il metodo locale viene chiamato solo dal contesto in cui è dichiarato.

Esistono due casi d'uso comuni per le funzioni locali: i metodi iterator pubblici e i metodi async pubblici. Entrambi i tipi di metodi generano codice che segnala gli errori in ritardo rispetto a quanto previsto dai programmatori. Per i metodi iterator le eccezioni vengono riscontrate solo quando si chiama il codice che enumera la sequenza restituita. Per i metodi async tutte le eccezioni vengono riscontrate solo quando è atteso l'oggetto restituito `Task`. L'esempio seguente illustra la separazione tra convalida dei parametri e implementazione dell'iteratore usando una funzione locale:

[!code-csharp[22_IteratorMethodLocal](~/samples/snippets/csharp/new-in-7/Iterator.cs#IteratorMethodLocal "Iterator method with local function")]

La stessa tecnica può essere usata con i metodi `async` per garantire che le eccezioni risultanti dalla convalida degli argomenti vengano generate prima che inizino le attività asincrone:

[!code-csharp[TaskExample](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

> [!NOTE]
> Alcune delle progettazioni supportate dalle funzioni locali possono essere eseguite anche usando le *espressioni lambda*. Per altre informazioni, vedere [Funzioni locali e espressioni lambda](../local-functions-vs-lambdas.md).

## <a name="more-expression-bodied-members"></a>Più membri con corpo di espressione

In C# 6 sono stati introdotti i [membri con corpo di espressione](csharp-6.md#expression-bodied-function-members) per le funzioni membro e le proprietà di sola lettura. C# 7.0 amplia la gamma di membri consentiti che possono essere implementati come espressioni. In C# 7.0 è possibile implementare *costruttori*, *finalizzatori* e funzioni di accesso `get` e `set` per *proprietà* e *indicizzatori*. Nel codice riportato di seguito vengono illustrati esempi di ogni tipo di membro:

[!code-csharp[ExpressionBodiedMembers](~/samples/snippets/csharp/new-in-7/expressionmembers.cs#ExpressionBodiedEverything "new expression-bodied members")]

> [!NOTE]
> In questo esempio non è necessario un finalizzatore, ma viene incluso per illustrare la sintassi. Non implementare un finalizzatore nella classe a meno che non sia necessario per rilasciare risorse non gestite. È inoltre consigliabile usare la classe <xref:System.Runtime.InteropServices.SafeHandle> anziché gestire direttamente le risorse non gestite.

Le nuove posizioni per i membri con corpo di espressione rappresentano un importante punto cardine per il linguaggio C#: queste funzionalità sono state implementate dai membri della community che lavoravano al progetto open source [Roslyn](https://github.com/dotnet/Roslyn).

La modifica di un metodo in un membro con corpo di espressione è una [modifica compatibile a livello binario](version-update-considerations.md#binary-compatible-changes).

## <a name="throw-expressions"></a>Espressioni throw

In C# `throw` è sempre stata un'istruzione. Poiché `throw` è un'istruzione, non un'espressione, non può essere usata in determinati costrutti di C#. Sono incluse le espressioni condizionali, le espressioni Null ridondanti e alcune espressioni lambda. L'aggiunta di membri con corpo di espressione consente di aggiungere più posizioni in cui le espressioni `throw` possono risultare utili. Per fare in modo che sia possibile scrivere uno di questi costrutti, C# 7.0 introduce le [*espressioni throw*](../language-reference/keywords/throw.md#the-throw-expression).

Questa aggiunta facilita la scrittura di codice basato sulle espressioni. Non sono necessarie istruzioni aggiuntive per il controllo degli errori.

## <a name="generalized-async-return-types"></a>Tipi restituiti asincroni generalizzati

La restituzione di un oggetto `Task` dai metodi asincroni può introdurre colli di bottiglia delle prestazioni in determinati percorsi. `Task` è un tipo di riferimento, quindi usarlo significa allocare un oggetto. Nei casi in cui un metodo dichiarato con il modificatore `async` restituisce un risultato memorizzato nella cache o viene completato in modo sincrono, le allocazioni aggiuntive possono diventare impegnative in termini di tempo nelle sezioni di codice critiche per le prestazioni. Possono diventare onerose se si verificano in cicli ridotti.

La nuova funzionalità del linguaggio significa che i tipi restituiti dal metodo asincrono non sono limitati a `Task`, `Task<T>` e `void`. Il tipo restituito deve comunque essere conforme al modello asincrono ovvero deve essere accessibile un metodo `GetAwaiter`. Come esempio concreto, il `ValueTask` tipo è stato aggiunto a .NET per utilizzare questa nuova funzionalità del linguaggio:As one concrete example, the type has been added to .NET to make use of this new language feature:

[!code-csharp[UsingValueTask](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#UsingValueTask "Using ValueTask")]

> [!NOTE]
> È necessario aggiungere il [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) pacchetto NuGet <xref:System.Threading.Tasks.ValueTask%601> per usare il tipo.

Questo miglioramento è particolarmente utile perché consente agli autori di librerie di evitare l'allocazione di un `Task` in codice critico per le prestazioni.

## <a name="numeric-literal-syntax-improvements"></a>Miglioramenti della sintassi dei valori letterali numerici

La lettura non corretta delle costanti numeriche può rendere più difficile la comprensione del codice quando viene letto per la prima volta. Le maschere di bit o altri valori simbolici possono dare origine a interpretazioni errate. C# 7.0 include due nuove funzionalità per la scrittura dei numeri in modo che siano più leggibili per l'uso previsto: *valori letterali binari* e *separatori di cifre*.

Ogni volta che si creano maschere di bit o che una rappresentazione binaria di un numero rende il codice più leggibile, scrivere il numero in formato binario:

[!code-csharp[ThousandSeparators](~/samples/snippets/csharp/new-in-7/Program.cs#ThousandSeparators "Thousands separators")]

`0b` all'inizio della costante indica che il numero viene scritto come numero binario. I numeri binari possono essere lunghi, quindi spesso è più semplice visualizzare gli schemi di bit introducendo il carattere `_` come separatore di cifre, come illustrato sopra nella costante binaria. Il separatore di cifre può apparire ovunque nella costante. Per i numeri in base 10 è comune usarlo come separatore delle migliaia:

[!code-csharp[LargeIntegers](~/samples/snippets/csharp/new-in-7/Program.cs#LargeIntegers "Large integer")]

Il separatore di cifre può essere usato anche con i tipi `decimal`, `float` e `double`:

[!code-csharp[OtherConstants](~/samples/snippets/csharp/new-in-7/Program.cs#OtherConstants "non-integral constants")]

Nel loro insieme, è possibile dichiarare le costanti numeriche ottimizzando la leggibilità.
