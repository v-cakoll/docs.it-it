---
title: Funzioni locali - Guida per programmatori C#
description: Le funzioni locali in C# sono metodi privati annidati in un altro membro e possono essere chiamati dal membro contenitore.
ms.date: 06/14/2017
helpviewer_keywords:
- local functions [C#]
ms.openlocfilehash: 9987d6d5ad57c1dceb3a4bffbae22a81c240c794
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864527"
---
# <a name="local-functions-c-programming-guide"></a>Funzioni locali (Guida per programmatori C#)

A partire dalla versione 7.0, C# supporta le *funzioni locali*. Le funzioni locali sono metodi privati di un tipo annidati in un altro membro. Possono essere chiamate solo dal relativo membro contenitore. Le funzioni locali, in particolare, possono essere dichiarate in e chiamate da:

- Metodi, soprattutto metodi iteratori e metodi asincroni
- Costruttori
- Funzioni di accesso alle proprietà
- Funzioni di accesso agli eventi
- Metodi anonimi
- Espressioni lambda
- Finalizzatori
- Altre funzioni locali

Le funzioni locali, tuttavia, non possono essere dichiarate all'interno di un membro con corpo di espressione.

> [!NOTE]
> In alcuni casi, è possibile usare un'espressione lambda per implementare le funzionalità supportate anche da una funzione locale. Per un confronto, vedere [funzioni locali rispetto alle espressioni lambda](#local-functions-vs-lambda-expressions).

Le funzioni locali rendono chiaro l'obiettivo del codice. Chiunque legga il codice può vedere che il metodo non è richiamabile, ad eccezione del metodo contenitore. Per i progetti in team, le funzioni locali impediscono anche a un altro sviluppatore di chiamare per errore il metodo direttamente da un altro punto della classe o dello struct.

## <a name="local-function-syntax"></a>Sintassi delle funzioni locali

Una funzione locale viene definita come metodo annidato all'interno di un membro contenitore. La definizione presenta la sintassi seguente:

```csharp
<modifiers: async | unsafe> <return-type> <method-name> <parameter-list>
```

Le funzioni locali possono usare i modificatori [async](../../language-reference/keywords/async.md) e [unsafe](../../language-reference/keywords/unsafe.md).

Tutte le variabili locali definite nel membro contenitore, inclusi i relativi parametri di metodo, sono accessibili nella funzione locale.

Diversamente da una definizione di metodo, una definizione di funzione locale non può includere il modificatore di accesso ai membri. Poiché tutte le funzioni locali sono private, l'integrazione di un modificatore di accesso come la parola chiave `private` genera l'errore del compilatore CS0106: "Il modificatore 'private' non è valido per questo elemento".

> [!NOTE]
> Prima di C# 8,0, le funzioni locali non possono includere il `static` modificatore. L'integrazione della parola chiave `static` genera l'errore del compilatore CS0106: "Il modificatore 'private' non è valido per questo elemento".

Non è possibile, inoltre, applicare attributi alla funzione locale o ai relativi parametri e parametri di tipo.

L'esempio seguente definisce una funzione locale denominata `AppendPathSeparator`, privata di un metodo denominato `GetText`:

[!code-csharp[LocalFunctionExample](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions1.cs)]  

## <a name="local-functions-and-exceptions"></a>Funzioni locali ed eccezioni

Le funzioni locali offrono il vantaggio di consentire alle eccezioni di essere rilevate immediatamente. Nel caso degli iteratori di metodo, le eccezioni vengono rilevate solo nel momento in cui la sequenza restituita viene enumerata e non quando viene recuperato l'iteratore. Nel caso dei metodi asincroni, qualsiasi eccezione generata viene rilevata mentre è attesa l'attività restituita.

L'esempio seguente definisce un metodo `OddSequence` che enumera i numeri dispari in un intervallo specifico. Poiché al metodo enumeratore `OddSequence` viene trasmesso un numero maggiore di 100, il metodo genera una <xref:System.ArgumentOutOfRangeException>. Come illustrato dall'output dell'esempio, l'eccezione viene rilevata solo nel momento in cui vengono iterati i numeri e non quando si recupera l'enumeratore.

[!code-csharp[LocalFunctionIterator1](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator1.cs)]

È possibile tuttavia generare un'eccezione mentre si esegue la convalida e prima di recuperare l'iteratore restituendo l'iteratore da una funzione locale, come illustrato nell'esempio seguente.

[!code-csharp[LocalFunctionIterator2](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator2.cs)]

Le funzioni locali possono essere usate in modo analogo anche per gestire eccezioni esterne all'operazione asincrona. In genere, le eccezioni generate in un metodo asincrono richiedono che vengano esaminate le eccezioni interne di una <xref:System.AggregateException>. Le funzioni locali consentono al codice di adottare un approccio "fail fast" e alle eccezioni di essere generate e osservate in modo sincrono.

Nell'esempio seguente viene usato un metodo asincrono denominato `GetMultipleAsync` per sospendere l'operazione per un determinato numero di secondi e restituire un valore che sia un multiplo casuale del numero di secondi specificato. Il ritardo massimo consentito è 5 secondi. Se il valore è superiore a 5, viene generata una <xref:System.ArgumentOutOfRangeException>. Come illustrato nell'esempio seguente, l'eccezione generata quando al metodo `GetMultipleAsync` viene passato il valore 6 viene sottoposta a wrapping in una <xref:System.AggregateException> dopo che il metodo `GetMultipleAsync` inizia l'esecuzione.

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async1.cs)]

Come per l'iteratore di metodo, è possibile effettuare il refactoring del codice dell'esempio per eseguire la convalida prima di chiamare il metodo asincrono. Come illustrato dall'output dell'esempio seguente, l'eccezione <xref:System.ArgumentOutOfRangeException> non viene sottoposta a wrapping in un'eccezione <xref:System.AggregateException>.

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async2.cs)]

## <a name="local-functions-vs-lambda-expressions"></a>Funzioni locali ed espressioni lambda

A prima vista, le funzioni locali e le [espressioni lambda](../statements-expressions-operators/lambda-expressions.md) sono molto simili. In molti casi, la scelta tra l'uso di funzioni locali ed espressioni lambda è una questione di stile e preferenze personali. Esistono tuttavia differenze reali di cui è necessario essere consapevoli nei casi in cui è possibile usare le une o le altre.

Si esamineranno ora le differenze tra implementazioni di funzioni locali e implementazioni di espressioni lambda dell'algoritmo fattoriale. Si analizzerà per prima la versione che usa una funzione locale:

[!code-csharp[LocalFunctionFactorial](../../../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]

Confrontare l'implementazione con una versione che usa le espressioni lambda:

[!code-csharp[26_LambdaFactorial](../../../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]

Le funzioni locali hanno nomi. Le espressioni lambda sono metodi anonimi che vengono assegnati a variabili di tipo `Func` o `Action`. Quando si dichiara una funzione locale, i tipi di argomento e il tipo restituito fanno parte della dichiarazione della funzione. Anziché far parte del corpo dell'espressione lambda, i tipi di argomento e il tipo restituito fanno parte della dichiarazione del tipo di variabile dell'espressione lambda. Queste due differenze possono avere come risultato una maggiore chiarezza del codice.

Le funzioni locali hanno regole diverse per l'assegnazione certa rispetto alle espressioni lambda. A una dichiarazione di funzione locale si può fare riferimento da qualsiasi posizione di codice nel cui ambito la funzione si trova. Un'espressione lambda deve essere assegnata a una variabile delegata prima che sia possibile accedervi o chiamarla tramite il delegato che fa riferimento all'espressione lambda. Si noti che la versione che usa l'espressione lambda deve dichiarare e inizializzare l'espressione lambda `nthFactorial` prima di definirla. In caso contrario, si verifica un errore di compilazione per fare riferimento a `nthFactorial` prima di assegnarla. Queste differenze fanno sì che gli algoritmi ricorsivi sino più facili da creare usando funzioni locali. È possibile dichiarare e definire una funzione locale che chiama se stessa. Le espressioni lambda devono essere dichiarate e a queste deve essere assegnato un valore predefinito prima che sia possibile riassegnarle a un corpo che fa riferimento alla stessa espressione lambda.

Le regole di assegnazione certa influiscono anche su tutte le variabili acquisite dalla funzione locale o dall'espressione lambda. Sia le regole delle funzioni locali che quelle delle espressioni lambda richiedono che tutte le variabili acquisite siano assegnate in modo certo nel momento in cui la funzione locale o l'espressione lambda viene convertita in delegato. La differenza è che le espressioni lambda vengono convertite in delegati quando vengono dichiarate. Le funzioni locali vengono convertite in delegati solo quando vengono usate come delegati. Se si dichiara una funzione locale e si fa riferimento a questa solo chiamandola come un metodo, non verrà convertita in delegato. Tale regola consente di dichiarare una funzione locale in qualsiasi posizione comoda all'interno dell'ambito che la comprende. È una pratica comune dichiarare funzioni locali alla fine del metodo padre, dopo le istruzioni Return.

In terzo luogo, il compilatore può eseguire un'analisi statica che consente alle funzioni locali di assegnare in modo certo variabili acquisite nell'ambito che le contiene. Considerare questo esempio:

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

Il compilatore può determinare che `LocalFunction` assegna in modo certo `y` quando viene chiamata. Poiché `LocalFunction` viene chiamata prima dell'istruzione `return`, `y` viene assegnata in modo certo in corrispondenza dell'istruzione `return`.

L'analisi che consente l'analisi di esempio consente la quarta differenza. A seconda del loro uso, le funzioni locali possono evitare le allocazioni di heap, che sono sempre necessarie per le espressioni lambda. Se una funzione locale non viene mai convertita in delegato e nessuna delle variabili acquisite dalla funzione locale viene acquisita da altre espressioni lambda o funzioni locali convertite in delegati, il compilatore può evitare allocazioni di heap.

Si consideri questo esempio asincrono:

[!code-csharp[TaskLambdaExample](../../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]

La chiusura per questa espressione lambda contiene le variabili `address`, `index` e `name`. Nel caso delle funzioni locali, l'oggetto che implementa la chiusura può essere di tipo `struct` Tale tipo struct verrebbe passato per riferimento alla funzione locale. Questa differenza di implementazione consentirebbe di risparmiare un'allocazione.

La creazione di istanze necessaria per le espressioni lambda comporta allocazioni di memoria aggiuntive che possono ridurre le prestazioni nei percorsi di codice in cui il tempo è un fattore cruciale. Questo sovraccarico non si verifica per le funzioni locali. Nell'esempio precedente, la versione con funzioni locali presenta due allocazioni in meno rispetto alla versione con espressioni lambda.

> [!NOTE]
> La funzione locale equivalente di questo metodo usa anche una classe per la chiusura. Se la chiusura di una funzione locale viene implementata come `class` o `struct` non ha molta importanza. Una funzione locale può usare `struct` mentre un'espressione lambda userà sempre `class`.

[!code-csharp[TaskLocalFunctionExample](../../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

Come ultimo vantaggio, non illustrato in questo esempio, le funzioni locali possono essere implementate come iteratori usando la sintassi `yield return` per produrre una sequenza di valori. L'istruzione `yield return` non è consentita nelle espressioni lambda.

Sebbene le funzioni locali possano apparire ridondanti rispetto alle espressioni lambda, in realtà hanno finalità e usi diversi. Le funzioni locali sono più efficienti nel caso si voglia scrivere una funzione che viene chiamata solo dal contesto di un altro metodo.

## <a name="see-also"></a>Vedi anche

- [Metodi](methods.md)
