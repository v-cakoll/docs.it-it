---
title: '- Operatori - e -= - Riferimenti per C#'
ms.date: 05/27/2019
f1_keywords:
- -_CSharpKeyword
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction operator [C#]
- delegate removal [C#]
- '- operator [C#]'
- subtraction assignment operator [C#]
- event unsubscription [C#]
- -= operator [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 2017aade92e8d7ad2af7101a107122fa8d7b9e27
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847651"
---
# <a name="--and---operators-c-reference"></a>Operatori - e -= (Riferimenti per C#)

Gli `-` `-=` operatori e sono supportati dai tipi numerici [integrali](../builtin-types/integral-numeric-types.md) e [a virgola mobile](../builtin-types/floating-point-numeric-types.md) incorporati e dai tipi [delegati.](../builtin-types/reference-types.md#the-delegate-type)

Per informazioni sull'operatore aritmetico `-`, vedere le sezioni [Operatori più e meno unari](arithmetic-operators.md#unary-plus-and-minus-operators) e [Operatore di sottrazione -](arithmetic-operators.md#subtraction-operator--) dell'articolo [Operatori aritmetici](arithmetic-operators.md).

## <a name="delegate-removal"></a>Rimozione di delegati

Per gli operandi dello stesso tipo [delegato](../builtin-types/reference-types.md#the-delegate-type), l'operatore `-` restituisce un'istanza di delegato che viene calcolata come segue:

- Se entrambi gli operandi sono diversi da Null e l'elenco chiamate dell'operando di destra è un sottoelenco contiguo dell'elenco chiamate dell'operando di sinistra, il risultato dell'operazione è un nuovo elenco chiamate ottenuto rimuovendo le voci dell'operando di destra dall'elenco di chiamate dell'operando di sinistra. Se l'elenco dell'operando di destra corrisponde a più sottoelenchi contigui nell'elenco dell'operando di sinistra, viene rimosso solo il sottoelenco corrispondente più a destra. Se la rimozione restituisce un elenco vuoto, il risultato è `null`.

  [!code-csharp-interactive[delegate removal](snippets/SubtractionOperator.cs#DelegateRemoval)]

- Se l'elenco chiamate dell'operando di destra non è un sottoelenco contiguo dell'elenco chiamate dell'operando di sinistra, il risultato dell'operazione è l'operando di sinistra. La rimozione di un delegato che non fa parte del delegato multicast, ad esempio, non produce alcun risultato e il delegato multicast rimane invariato.

  [!code-csharp-interactive[delegate removal with no effect](snippets/SubtractionOperator.cs#DelegateRemovalNoChange)]

  L'esempio precedente dimostra anche che, durante la rimozione del delegato, vengono confrontate le istanze del delegato. I delegati prodotti dalla valutazione di [espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) identiche, ad esempio, non sono uguali. Per altre informazioni sull'uguaglianza dei delegati, vedere la sezione [Delegare gli operatori di uguaglianza](~/_csharplang/spec/expressions.md#delegate-equality-operators) dell'articolo [Specifiche del linguaggio C#](~/_csharplang/spec/introduction.md).

- Se l'operando di sinistra è `null`, il risultato dell'operazione è `null`. Se l'operando di destra è `null`, il risultato dell'operazione è l'operando di sinistra.

  [!code-csharp-interactive[delegate removal and null](snippets/SubtractionOperator.cs#DelegateRemovalAndNull)]

Per combinare i delegati, utilizzare [ `+` l'operatore](addition-operator.md#delegate-combination).

Per altre informazioni sui tipi delegate, vedere [Delegati](../../programming-guide/delegates/index.md).

## <a name="subtraction-assignment-operator--"></a>Operatore di assegnazione di sottrazione -=

Un'espressione che usa l'operatore `-=`, ad esempio

```csharp
x -= y
```

equivale a

```csharp
x = x - y
```

con la differenza che `x` viene valutato una sola volta.

Nell'esempio seguente viene illustrato l'uso dell'operatore `-=`:

[!code-csharp-interactive[-= examples](snippets/SubtractionOperator.cs#SubtractAndAssign)]

È anche possibile usare l'operatore `-=` per specificare un metodo del gestore eventi quando si elimina la sottoscrizione a un [evento](../keywords/event.md). Per ulteriori informazioni, vedere [Come sottoscrivere e annullare la sottoscrizione agli eventi](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="operator-overloadability"></a>Overload degli operatori

Un tipo definito dall'utente può eseguire l'[overload](operator-overloading.md) dell'operatore `-`. Quando viene eseguito l'overload di un operatore `-` binario, viene eseguito in modo implicito anche l'overload dell'operatore `-=`. Un tipo definito dall'utente non può eseguire l'overload dell'operatore `-=` in modo esplicito.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni [Operatore meno unario](~/_csharplang/spec/expressions.md#unary-minus-operator) e [Operatore di sottrazione](~/_csharplang/spec/expressions.md#subtraction-operator) di [Specifiche del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- [Events](../../programming-guide/events/index.md)
- [Operatori aritmetici](arithmetic-operators.md)
- [Operatori + e +=](addition-operator.md)
