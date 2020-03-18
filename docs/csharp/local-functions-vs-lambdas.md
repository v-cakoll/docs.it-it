---
title: Funzioni locali ed espressioni lambda
description: Informazioni sui motivi per cui le funzioni locali possono essere una scelta migliore rispetto alle espressioni lambda.
ms.date: 06/27/2016
ms.technology: csharp-advanced-concepts
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
ms.openlocfilehash: 13cc3fe47bbcd6a465347a6c991b2006586c78fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173341"
---
# <a name="local-functions-compared-to-lambda-expressions"></a>Confronto tra funzioni locali ed espressioni lambda

A prima vista, le [funzioni locali](programming-guide/classes-and-structs/local-functions.md) e le [espressioni lambda](./programming-guide/statements-expressions-operators/lambda-expressions.md) sono molto simili. In molti casi, la scelta tra l'uso di funzioni locali ed espressioni lambda è una questione di stile e preferenze personali. Esistono tuttavia differenze reali di cui è necessario essere consapevoli nei casi in cui è possibile usare le une o le altre.

Si esamineranno ora le differenze tra implementazioni di funzioni locali e implementazioni di espressioni lambda dell'algoritmo fattoriale. Si analizzerà per prima la versione che usa una funzione locale:

[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]

Confrontare l'implementazione con una versione che usa le espressioni lambda:

[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]

Le funzioni locali hanno nomi. Le espressioni lambda sono metodi anonimi che vengono assegnati a variabili di tipo `Func` o `Action`. Quando si dichiara una funzione locale, i tipi di argomento e il tipo restituito fanno parte della dichiarazione della funzione. Anziché far parte del corpo dell'espressione lambda, i tipi di argomento e il tipo restituito fanno parte della dichiarazione del tipo di variabile dell'espressione lambda. Queste due differenze possono avere come risultato una maggiore chiarezza del codice.

Le funzioni locali hanno regole diverse per l'assegnazione certa rispetto alle espressioni lambda. A una dichiarazione di funzione locale si può fare riferimento da qualsiasi posizione di codice nel cui ambito la funzione si trova. Un'espressione lambda deve essere assegnata a una variabile delegata prima che sia possibile accedervi (o chiamare tramite il delegato che fa riferimento all'espressione lambda). Si noti che la versione che usa l'espressione lambda deve dichiarare e inizializzare l'espressione lambda, `nthFactorial` prima di definirla. In caso contrario, si verifica un errore di compilazione per fare riferimento a `nthFactorial` prima di assegnarla.
Queste differenze fanno sì che gli algoritmi ricorsivi sino più facili da creare usando funzioni locali. È possibile dichiarare e definire una funzione locale che chiama se stessa. Le espressioni lambda devono essere dichiarate e a queste deve essere assegnato un valore predefinito prima che sia possibile riassegnarle a un corpo che fa riferimento alla stessa espressione lambda.

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

L'analisi che consente l'analisi di esempio consente la quarta differenza.
A seconda del loro uso, le funzioni locali possono evitare le allocazioni di heap, che sono sempre necessarie per le espressioni lambda. Se una funzione locale non viene mai convertita in delegato e nessuna delle variabili acquisite dalla funzione locale viene acquisita da altre espressioni lambda o funzioni locali convertite in delegati, il compilatore può evitare allocazioni di heap.

Si consideri questo esempio asincrono:

[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]

La chiusura per questa espressione lambda contiene le variabili `address`, `index` e `name`. Nel caso delle funzioni locali, l'oggetto che implementa la chiusura può essere di tipo `struct` Tale tipo struct verrebbe passato per riferimento alla funzione locale. Questa differenza di implementazione consentirebbe di risparmiare un'allocazione.

La creazione di istanze necessaria per le espressioni lambda comporta allocazioni di memoria aggiuntive che possono ridurre le prestazioni nei percorsi di codice in cui il tempo è un fattore cruciale.
Questo sovraccarico non si verifica per le funzioni locali. Nell'esempio precedente, la versione con funzioni locali presenta due allocazioni in meno rispetto alla versione con espressioni lambda.

> [!NOTE]
> La funzione locale equivalente di questo metodo usa anche una classe per la chiusura. Se la chiusura di una funzione locale viene implementata come `class` o `struct` non ha molta importanza. Una funzione locale può usare `struct` mentre un'espressione lambda userà sempre `class`.

[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

Come ultimo vantaggio, non illustrato in questo esempio, le funzioni locali possono essere implementate come iteratori usando la sintassi `yield return` per produrre una sequenza di valori. L'istruzione `yield return` non è consentita nelle espressioni lambda.

Sebbene le funzioni locali possano apparire ridondanti rispetto alle espressioni lambda, in realtà hanno finalità e usi diversi.
Le funzioni locali sono più efficienti nel caso si voglia scrivere una funzione che viene chiamata solo dal contesto di un altro metodo.
