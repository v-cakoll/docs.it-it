---
title: 'Cicli: espressioni for...in (F#)'
description: "Vedere come il ciclo for di F #.. nell'espressione costrutto di ciclo viene utilizzato per scorrere le corrispondenze di un modello in una raccolta enumerabile."
ms.date: 05/16/2016
ms.openlocfilehash: c4fba1f1dea3993cafa2e37ad0f32d9fb2eed85a
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "46540385"
---
# <a name="loops-forin-expression"></a>Espressione Loops: for...in

Questo costrutto di ciclo viene utilizzato per scorrere le corrispondenze di un modello in una raccolta enumerabile, ad esempio un'espressione di intervallo, sequenza, elenco, matrice o un altro costrutto che supporta l'enumerazione.

## <a name="syntax"></a>Sintassi

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a>Note

Il `for...in` espressione può essere confrontato con il `for each` istruzione in altri linguaggi .NET perché è usato per eseguire il ciclo nei valori in una raccolta enumerabile. Tuttavia, `for...in` supporta anche criteri di ricerca per la raccolta invece solo l'iterazione nell'intera raccolta.

L'espressione enumerabile può essere specificata come una raccolta enumerabile o, utilizzando il `..` operatore, sotto forma di intervallo su un tipo integrale. Raccolte enumerabili includono elenchi, sequenze, matrici, set, mappe e così via. Qualsiasi tipo che implementa `System.Collections.IEnumerable` può essere utilizzato.

Quando si esprime un intervallo usando la `..` operatore, è possibile usare la sintassi seguente.

*Avviare* ... *Fine*

È anche possibile usare una versione che include un incremento denominato il *ignorare*, come nel codice seguente.

*Avviare* ... *ignorare* ... *Fine*

Quando si usa intervalli integrali e una variabile contatore semplici come un modello, il comportamento tipico è incrementare la variabile contatore da 1 a ogni iterazione, ma se l'intervallo include un valore di omissione, il contatore viene incrementato dal valore skip invece.

Valori corrispondenti nel modello possono essere usati anche nell'espressione corpo.

Gli esempi di codice seguenti illustrano l'uso del `for...in` espressione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

L'output è indicato di seguito.

```
1
5
100
450
788
```

Nell'esempio seguente viene illustrato come eseguire un ciclo su una sequenza e come usare un modello tupla anziché una variabile semplice.

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

L'output di funzione1 è come indicato di seguito.

```
1 2 3 4 5 6 7 8 9 10
```

Nell'esempio seguente viene illustrato come eseguire un ciclo su un intervallo con un skip 2, che include ogni altro elemento dell'intervallo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

L'output di `function2` è come indicato di seguito.

```
1 3 5 7 9
```

Nell'esempio seguente viene illustrato come utilizzare un intervallo di caratteri.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

L'output di `function3` è come indicato di seguito.

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

Nell'esempio seguente viene illustrato come utilizzare un valore negativo skip per un'iterazione inversa.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

L'output di `function4` è come indicato di seguito.

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

L'inizio e la fine dell'intervallo possono essere anche espressioni, ad esempio funzioni, come nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

L'output di `function5` con questo input è come indicato di seguito.

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

L'esempio seguente mostra l'uso di un carattere jolly (\_) quando l'elemento non è necessaria nel ciclo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

L'output è indicato di seguito.

```
Number of elements in list1: 5
```

`Note` È possibile usare `for...in` nelle espressioni di sequenza e altre espressioni di calcolo, nel qual caso una versione personalizzata del `for...in` espressione viene usata. Per altre informazioni, vedere [sequenze](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md), e [espressioni di calcolo](computation-expressions.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Cicli: espressione `for...to`](loops-for-to-expression.md)
- [Cicli: espressione `while...do`](loops-while-do-expression.md)
