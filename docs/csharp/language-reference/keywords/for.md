---
title: istruzione for-riferimenti per C#
ms.date: 06/13/2018
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
ms.openlocfilehash: db7cecc697a9cc9e5ff6b94b78747b799ed7e505
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401901"
---
# <a name="for-c-reference"></a>for (Riferimenti per C#)

L'istruzione `for` esegue un'istruzione o un blocco di istruzioni mentre un'espressione booleana specificata restituisce `true`.

In un punto qualsiasi all'interno del blocco dell'istruzione `for` è possibile uscire dal ciclo usando l'istruzione [break](break.md) o passare all'iterazione successiva nel ciclo con l'istruzione [continue](continue.md). È anche possibile uscire `for` da un ciclo tramite le istruzioni [goto](goto.md), [return](return.md)o [throw](throw.md) .

## <a name="structure-of-the-for-statement"></a>Struttura dell'istruzione `for`

L'istruzione `for` definisce le sezioni *inizializzatore*, *condizione* e *iteratore*:

```csharp
for (initializer; condition; iterator)
    body
```

Le tre sezioni sono facoltative. Il corpo del ciclo è un'istruzione o un blocco di istruzioni.

L'esempio seguente illustra l'istruzione `for` con tutte le sezioni definite:

[!code-csharp-interactive[for loop example](snippets/IterationKeywordsExamples.cs#5)]

### <a name="the-initializer-section"></a>Sezione *inizializzatore*

Le istruzioni nella sezione *inizializzatore* vengono eseguite una sola volta, prima dell'avvio del ciclo. La sezione *inizializzatore* può essere costituita da quanto segue:

- Dichiarazione e inizializzazione di una variabile di ciclo locale, non accessibile dall'esterno del ciclo stesso.

- Zero o più istruzioni, ricavate dal seguente elenco, separate da virgole:

  - Istruzione di [assegnazione](../operators/assignment-operator.md)

  - Chiamata di un metodo

  - Espressione di [incremento](../operators/arithmetic-operators.md#increment-operator-) in forma prefissa o suffissa, ad esempio `++i` o `i++`

  - Espressione di [decremento](../operators/arithmetic-operators.md#decrement-operator---) in forma prefissa o suffissa, ad esempio `--i` o `i--`

  - Creazione di un oggetto con l'operatore [new](../operators/new-operator.md)

  - Espressione [await](../operators/await.md)

La sezione *inizializzatore* dell'esempio precedente dichiara e inizializza la variabile di ciclo locale `i`:

```csharp
int i = 0
```

### <a name="the-condition-section"></a>Sezione *condizione*

La sezione *condizione*, se presente, deve essere un'espressione booleana. Tale espressione viene valutata prima di ogni iterazione del ciclo. Se la sezione *condizione* non è presente o l'espressione booleana restituisce `true`, viene eseguita la successiva iterazione del ciclo; in caso contrario, si esce dal ciclo.

La sezione *condizione* dell'esempio precedente determina se il ciclo termina in base al valore della variabile di ciclo locale:

```csharp
i < 5
```

### <a name="the-iterator-section"></a>Sezione *iteratore*

La sezione *iteratore* definisce cosa accade dopo ogni iterazione del corpo del ciclo. La sezione dell' *iteratore* contiene zero o più delle espressioni di istruzione seguenti, separate da virgole:

- Istruzione di [assegnazione](../operators/assignment-operator.md)

- Chiamata di un metodo

- Espressione di [incremento](../operators/arithmetic-operators.md#increment-operator-) in forma prefissa o suffissa, ad esempio `++i` o `i++`

- Espressione di [decremento](../operators/arithmetic-operators.md#decrement-operator---) in forma prefissa o suffissa, ad esempio `--i` o `i--`

- Creazione di un oggetto con l'operatore [new](../operators/new-operator.md)

- Espressione [await](../operators/await.md)

La sezione *iteratore* dell'esempio precedente incrementa la variabile di ciclo locale:

```csharp
i++
```

## <a name="examples"></a>Esempi

L'esempio seguente illustra alcuni utilizzi meno comuni delle sezioni dell'istruzione `for`: assegnazione di un valore a una variabile di ciclo esterna nella sezione *inizializzatore*, chiamata di un metodo sia nella sezione *inizializzatore* che nella sezione *iteratore* e modifica dei valori di due variabili nella sezione *iteratore*. Selezionare **Esegui** per eseguire il codice di esempio. Dopo l'esecuzione è possibile modificare il codice ed eseguirlo di nuovo.

[!code-csharp-interactive[not typical for loop example](snippets/IterationKeywordsExamples.cs#6)]

L'esempio seguente definisce il ciclo `for` infinito:

[!code-csharp[infinite for loop example](snippets/IterationKeywordsExamples.cs#7)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [L'istruzione for](~/_csharplang/spec/statements.md#the-for-statement) della [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [foreach, in](foreach-in.md)
