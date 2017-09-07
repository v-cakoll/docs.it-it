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
ms.translationtype: HT
ms.sourcegitcommit: 4582cb0ee091526423cce3fc1d8243029f34f59c
ms.openlocfilehash: 366d7465433f2786960e22418b8aa46ba10e1fd1
ms.contentlocale: it-it
ms.lasthandoff: 08/16/2017

---
# <a name="local-functions-compared-to-lambda-expressions"></a>Confronto tra funzioni locali ed espressioni lambda

A prima vista, le [funzioni locali](programming-guide/classes-and-structs/local-functions.md) e le [espressioni lambda](lambda-expressions.md) sono molto simili.
In alcuni casi, tuttavia, le funzioni locali possono costituire una soluzione molto più semplice ed efficace.

Si esamineranno ora le differenze tra implementazioni di funzioni locali e implementazioni di espressioni lambda dell'algoritmo fattoriale. Si analizzerà per prima la versione che usa una funzione locale:

[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Fattoriale ricorsivo che usa una funzione locale")]

Confrontare l'implementazione con una versione che usa le espressioni lambda:

[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Fattoriale ricorsivo che usa le espressioni lambda")]

In primo luogo, le espressioni lambda vengono implementate creando un'istanza di un delegato e richiamando il delegato, mentre le funzioni locali sono implementate come chiamate al metodo.
La creazione di istanze necessaria per le espressioni lambda comporta allocazioni di memoria aggiuntive che possono ridurre le prestazioni nei percorsi di codice in cui il tempo è un fattore cruciale.
Questo sovraccarico non si verifica per le funzioni locali. Nell'esempio precedente, la versione con funzioni locali presenta due allocazioni in meno rispetto alla versione con espressioni lambda.

Questo metodo ricorsivo è abbastanza semplice da consentire l'implementazione della funzione locale come metodo privato con un nome generato dal compilatore. A differenza di altri metodi privati, l'ambito semantico di questo metodo si trova all'interno della funzione esterna.

In secondo luogo, le funzioni locali possono essere chiamate prima che vengano definite, mentre le espressioni lambda devono essere dichiarate prima di essere definite. Per questo motivo le funzioni locali sono più semplici da usare negli algoritmi ricorsivi, come illustrato sopra.

Si noti che la versione che usa l'espressione lambda deve dichiarare e inizializzare l'espressione lambda `nthFactorial` prima di definirla. In caso contrario, si verifica un errore di compilazione per fare riferimento a `nthFactorial` prima di assegnarla.
Gli algoritmi ricorsivi sono più facili da creare usando le funzioni locali.

In terzo luogo, per le espressioni lambda il compilatore deve creare sempre una classe anonima e un'istanza della classe per archiviare eventuali variabili acquisite dalla chiusura. Si consideri questo esempio asincrono:

[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Metodo con restituzione di Task con espressione lambda")]

La chiusura per questa espressione lambda contiene le variabili `address`, `index` e `name`. Nel caso delle funzioni locali, l'oggetto che implementa la chiusura può essere di tipo `struct` ed esegue il salvataggio in un'allocazione.

> [!NOTE]
> La funzione locale equivalente di questo metodo usa anche una classe per la chiusura. Se la chiusura di una funzione locale viene implementata come `class` o `struct` non ha molta importanza. Una funzione locale può usare `struct` mentre un'espressione lambda userà sempre `class`.

[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Metodo di restituzione attività con funzione locale")]

Come ultimo vantaggio, non illustrato in questo esempio, le funzioni locali possono essere implementate come iteratori usando la sintassi `yield return` per produrre una sequenza di valori.

Sebbene le funzioni locali possano apparire ridondanti rispetto alle espressioni lambda, in realtà hanno finalità e usi diversi.
Le funzioni locali sono più efficienti nel caso si voglia scrivere una funzione che viene chiamata solo dal contesto di un altro metodo.

