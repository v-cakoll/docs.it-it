---
title: 'Espressione Loops: for...in'
description: Vedere come il F# ... nel costrutto di ciclo di espressioni viene usato per eseguire l'iterazione delle corrispondenze di un modello in una raccolta enumerabile.
ms.date: 05/16/2016
ms.openlocfilehash: 5a2ca59ca4199ece5d78010ff780e86ae2b25181
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216454"
---
# <a name="loops-forin-expression"></a>Espressione Loops: for...in

Questo costrutto di ciclo viene usato per eseguire l'iterazione delle corrispondenze di un modello in una raccolta enumerabile, ad esempio un'espressione di intervallo, una sequenza, un elenco, una matrice o un altro costrutto che supporta l'enumerazione.

## <a name="syntax"></a>Sintassi

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a>Note

L' `for...in` espressione può essere confrontata `for each` con l'istruzione in altri linguaggi .NET perché viene utilizzata per eseguire il ciclo sui valori in una raccolta enumerabile. Tuttavia, `for...in` supporta anche criteri di ricerca sulla raccolta anziché semplicemente iterazione sull'intera raccolta.

L'espressione enumerabile può essere specificata come raccolta enumerabile o, usando l' `..` operatore, come intervallo in un tipo integrale. Le raccolte enumerabili includono elenchi, sequenze, matrici, set, mappe e così via. È possibile utilizzare qualsiasi `System.Collections.IEnumerable` tipo che implementa.

Quando si esprime un intervallo usando l' `..` operatore, è possibile usare la sintassi seguente.

*Avvia* ... *finish*

È anche possibile usare una versione che include un incremento denominato *Skip*, come nel codice seguente.

*Avvia* ... *Ignora* . *finish*

Quando si usano intervalli integrali e una semplice variabile contatore come modello, il comportamento tipico consiste nell'incrementare la variabile contatore di 1 per ogni iterazione, ma se l'intervallo include un valore skip, il contatore viene incrementato in base al valore skip.

È anche possibile usare i valori corrispondenti nel criterio nell'espressione Body.

Negli esempi di codice seguenti viene illustrato l'utilizzo dell' `for...in` espressione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

L'output è indicato di seguito.

```console
1
5
100
450
788
```

Nell'esempio seguente viene illustrato come eseguire il ciclo su una sequenza e come utilizzare un modello di tupla anziché una variabile semplice.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

L'output è indicato di seguito.

```console
1 squared is 1
2 squared is 4
3 squared is 9
4 squared is 16
5 squared is 25
6 squared is 36
7 squared is 49
8 squared is 64
9 squared is 81
10 squared is 100
```

Nell'esempio seguente viene illustrato come eseguire il ciclo su un intervallo di valori integer semplici.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

L'output di funzione1 è il seguente.

```console
1 2 3 4 5 6 7 8 9 10
```

Nell'esempio seguente viene illustrato come eseguire il ciclo su un intervallo con un valore skip di 2, che include tutti gli altri elementi dell'intervallo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

Di seguito è `function2` riportato l'output di.

```console
1 3 5 7 9
```

Nell'esempio seguente viene illustrato come utilizzare un intervallo di caratteri.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

Di seguito è `function3` riportato l'output di.

```console
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

Nell'esempio seguente viene illustrato come utilizzare un valore skip negativo per un'iterazione inversa.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

Di seguito è `function4` riportato l'output di.

```console
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

L'inizio e la fine dell'intervallo possono anche essere espressioni, ad esempio funzioni, come nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

Di seguito è `function5` riportato l'output di con questo input.

```console
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

Nell'esempio seguente viene illustrato l'utilizzo di un carattere jolly\_() quando l'elemento non è necessario nel ciclo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

L'output è indicato di seguito.

```console
Number of elements in list1: 5
```

`Note`È possibile utilizzare `for...in` nelle espressioni di sequenza e in altre espressioni `for...in` di calcolo, nel qual caso viene utilizzata una versione personalizzata dell'espressione. Per altre informazioni, vedere [sequenze](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md)ed [espressioni di calcolo](computation-expressions.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Cicli `for...to`Espressione](loops-for-to-expression.md)
- [Cicli `while...do`Espressione](loops-while-do-expression.md)
