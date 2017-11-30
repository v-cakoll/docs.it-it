---
title: Funzioni locali ed espressioni lambda
description: Informazioni sui motivi per cui le funzioni locali possono essere una scelta migliore rispetto alle espressioni lambda.
keywords: "C#, .NET, .NET Core, funzionalità recenti, novità, funzioni locali, espressioni lambda"
author: BillWagner
ms.author: wiwagn
ms.date: 06/27/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
ms.openlocfilehash: 20312b58a24dc991791edad4bb92d3a8ca6d501a
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2017
---
# <a name="local-functions-compared-to-lambda-expressions"></a>Funzioni locali rispetto alle espressioni lambda

A prima vista, le [funzioni locali](programming-guide/classes-and-structs/local-functions.md) e le [espressioni lambda](lambda-expressions.md) sono molto simili. In molti casi, la scelta tra l'utilizzo di funzioni locali ed espressioni lambda è una questione di stile e le preferenze personali. Tuttavia, esistono differenze reali in cui è possibile utilizzare uno o l'altro che è necessario essere consapevoli di.

Si esamineranno ora le differenze tra implementazioni di funzioni locali e implementazioni di espressioni lambda dell'algoritmo fattoriale. Si analizzerà per prima la versione che usa una funzione locale:

[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]

Confrontare l'implementazione con una versione che usa le espressioni lambda:

[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]

Le funzioni locali hanno nomi. Le espressioni lambda sono metodi anonimi che vengono assegnati a variabili che sono `Func` o `Action` tipi. Quando si dichiara una funzione locale, i tipi di argomento e un tipo restituito fanno parte della dichiarazione di funzione. Anziché far parte del corpo dell'espressione lambda espressione, i tipi di argomento e il tipo restituito fanno parte della dichiarazione di variabile di tipo dell'espressione lambda. Queste due differenze possono generare codice più chiara.

Le funzioni locali hanno regole diverse per l'assegnazione di espressioni lambda. Una dichiarazione di funzione locale può fare riferimento da qualsiasi posizione di codice in cui si trova nell'ambito. Un'espressione lambda deve essere assegnata a una variabile delegato prima che può essere accedere (o tramita il delegato che fa riferimento l'espressione lambda.) Si noti che la versione che usa l'espressione lambda deve dichiarare e inizializzare l'espressione lambda `nthFactorial` prima di definirla. In caso contrario, si verifica un errore di compilazione per fare riferimento a `nthFactorial` prima di assegnarla.
Queste differenze indicano che algoritmi ricorsivi sono più semplici da creare usando funzioni locali. È possibile dichiarare e definire una funzione locale che chiama se stessa. Espressioni lambda devono essere dichiarate e assegnate un valore predefinito prima di poter essere riassegnati a un corpo che fa riferimento la stessa espressione lambda.

Le regole di assegnazione definita influenzano anche tutte le variabili acquisite per il epression lambda o di funzione locale. Le funzioni locali sia le regole delle espressioni lambda richiedono che tutte le variabili acquisite sono assegnate in corrispondenza del punto quando l'espressione lambda o di funzione locale viene convertito in un delegato. La differenza è che le espressioni lambda vengono convertite in delegati quando vengono dichiarati. Le funzioni locali vengono convertite in delegati solo se utilizzato come un delegato. Se si dichiara una funzione locale e fare riferimento solo quando viene chiamata come un metodo, non essere convertito in un delegato. Tale regola consente di dichiarare una funzione locale in qualsiasi posizione appropriata nel relativo ambito contenitore. È comune per dichiarare le funzioni locali alla fine del metodo padre, dopo le istruzioni return.

In terzo luogo, il compilatore può eseguire l'analisi statica che consente di funzioni locali assegnare in modo definitivo variabili acquisite nell'ambito di inclusione. Si consideri l'esempio seguente:

```csharp
bool M()
{
    int y;
    Local();
    return y;

    void Local() => y = 0;
}
```

Il compilatore può determinare che `Local` sicuramente assegna `y` quando viene chiamato. Poiché `Local` viene chiamato prima di `return` istruzione `y` definitiely assegnata nel `return` istruzione.

L'analisi che consente di eseguire analisi che consente la quarta differenza.
A seconda del loro utilizzo, le funzioni locali possono evitare le allocazioni di heap sono sempre necessari per le espressioni lambda. Se una funzione locale non viene mai convertita in un delegato e nessuna delle variabili acquisite dalla funzione locale vengono acquisita da altre espressioni lambda o funzioni locali che vengono convertite in delegati, il compilatore può evitare allocazioni di heap. 

Si consideri questo esempio asincrono:

[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]

La chiusura per questa espressione lambda contiene le variabili `address`, `index` e `name`. Nel caso delle funzioni locali, l'oggetto che implementa la chiusura può essere di tipo `struct` Che tipo di struct verrebbe passato per riferimento alla funzione locale. Questa differenza di implementazione verrà salvate in un'allocazione.

La creazione di istanze necessarie per le espressioni lambda significa che le allocazioni di memoria aggiuntiva, che possono essere un fattore di prestazioni nei percorsi di codice critico.
Questo sovraccarico non si verifica per le funzioni locali. Nell'esempio precedente, la versione con funzioni locali presenta due allocazioni in meno rispetto alla versione con espressioni lambda.

> [!NOTE]
> La funzione locale equivalente di questo metodo usa anche una classe per la chiusura. Se la chiusura di una funzione locale viene implementata come `class` o `struct` non ha molta importanza. Una funzione locale può usare `struct` mentre un'espressione lambda userà sempre `class`.

[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Task returning method with local function")]

Come ultimo vantaggio, non illustrato in questo esempio, le funzioni locali possono essere implementate come iteratori usando la sintassi `yield return` per produrre una sequenza di valori. Il `yield return` istruzione non è consentita nelle espressioni lambda.

Sebbene le funzioni locali possano apparire ridondanti rispetto alle espressioni lambda, in realtà hanno finalità e usi diversi.
Le funzioni locali sono più efficienti nel caso si voglia scrivere una funzione che viene chiamata solo dal contesto di un altro metodo.
