---
title: 'Cicli: espressioni for...in (F#)'
description: 'Vedere come il ciclo for di F #... nell''espressione costrutto di ciclo viene utilizzato per scorrere le corrispondenze di un modello in una raccolta enumerabile.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f54e3228-4aec-4d0a-ae37-bc3376508284
ms.openlocfilehash: d86aeb3bdd975261e59004d636354a740bd95c47
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="loops-forin-expression"></a>Espressione Loops: for...in

Questo costrutto di ciclo viene utilizzato per scorrere le corrispondenze di un modello in una raccolta enumerabile, ad esempio un'espressione di intervallo, sequenza, elenco, matrice o un altro costrutto che supporta l'enumerazione.


## <a name="syntax"></a>Sintassi

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a>Note
Il `for...in` espressione può essere confrontata con il `for each` istruzione in altri linguaggi .NET perché è utilizzato per eseguire il ciclo i valori di una raccolta enumerabile. Tuttavia, `for...in` supporta anche i criteri di ricerca della raccolta anziché solo l'iterazione nell'intera raccolta.

L'espressione enumerabile può essere specificata come una raccolta enumerabile o, tramite il `..` (operatore), come un intervallo in un tipo integrale. Raccolte enumerabili includono elenchi, sequenze, matrici, set, mappe e così via. Qualsiasi tipo che implementa `System.Collections.IEnumerable` può essere utilizzato.

Quando si esprime un intervallo mediante la `..` operatore, è possibile utilizzare la sintassi seguente.

*Avviare* ... *fine*

È inoltre possibile utilizzare una versione che include un incremento, detto di *ignorare*, come nel codice riportato di seguito.

*Avviare* ... *ignorare* ... *fine*

Quando si utilizza intervalli integrali e a una variabile contatore semplice come modello, il comportamento tipico consiste nell'incrementare la variabile contatore di 1 a ogni iterazione, ma se l'intervallo include un valore di salto, il contatore viene incrementato invece del valore di salto.

I valori corrispondenti nel modello utilizzabile anche nell'espressione del corpo.

Gli esempi di codice seguente viene illustrato l'utilizzo del `for...in` espressione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

L'output è indicato di seguito.

```
1
5
100
450
788
```

Nell'esempio seguente viene illustrato come eseguire un ciclo in una sequenza e come usare un tupla (modello) anziché una variabile semplice.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

L'output è indicato di seguito.

```
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

Nell'esempio seguente viene illustrato come eseguire un ciclo su un intervallo di numeri interi semplice.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

L'output di function1 è come indicato di seguito.

```
1 2 3 4 5 6 7 8 9 10
```

Nell'esempio seguente viene illustrato come eseguire un ciclo su un intervallo con un skip 2, che include ogni altro elemento dell'intervallo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

L'output di `function2` è indicato di seguito.

```
1 3 5 7 9
```

Nell'esempio seguente viene illustrato come utilizzare un intervallo di caratteri.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

L'output di `function3` è indicato di seguito.

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

Nell'esempio seguente viene illustrato come utilizzare un valore negativo skip per un'iterazione inversa.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

L'output di `function4` è indicato di seguito.

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

Inizio e alla fine dell'intervallo possono anche essere espressioni, ad esempio funzioni, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

L'output di `function5` con questo input è indicato di seguito.

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

Nell'esempio successivo viene illustrato l'utilizzo di un carattere jolly (_) quando l'elemento non è necessario nel ciclo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

L'output è indicato di seguito.

```
Number of elements in list1: 5
```

`Note`È possibile utilizzare `for...in` in espressioni sequenza e altre espressioni di calcolo, nel qual caso una versione personalizzata del `for...in` viene utilizzata l'espressione. Per ulteriori informazioni, vedere [sequenze](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md), e [espressioni di calcolo](computation-expressions.md).


## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

[Cicli: espressione `for...to`](loops-for-to-expression.md)

[Cicli: espressione `while...do`](loops-while-do-expression.md)
