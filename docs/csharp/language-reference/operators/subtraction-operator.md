---
title: '- Operatori - e -= (Riferimenti per C#)'
ms.custom: seodec18
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
ms.openlocfilehash: 9f43a863de69122e251204668af2ea989fcc993c
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300081"
---
# <a name="--and---operators-c-reference"></a>Operatori - e -= (Riferimenti per C#)

L'operatore `-` è supportato dai tipi numerici predefiniti e i tipi [delegato](../keywords/delegate.md).

Per informazioni sull'operatore aritmetico `-`, vedere le sezioni [Operatori più e meno unari](arithmetic-operators.md#unary-plus-and-minus-operators) e [Operatore di sottrazione -](arithmetic-operators.md#subtraction-operator--) dell'articolo [Operatori aritmetici](arithmetic-operators.md).

## <a name="delegate-removal"></a>Rimozione di delegati

Per gli operandi dello stesso tipo [delegato](../keywords/delegate.md), l'operatore `-` restituisce un'istanza di delegato che viene calcolata come segue:

- Se entrambi gli operandi sono diversi da Null e l'elenco chiamate del secondo operando è un sottoelenco contiguo dell'elenco chiamate del primo operando, il risultato dell'operazione è un nuovo elenco chiamate ottenuto rimuovendo le voci del secondo operando dall'elenco di chiamate del primo operando. Se l'elenco del secondo operando corrisponde a più sottoelenchi contigui nell'elenco del primo operando, viene rimosso solo il sottoelenco corrispondente più a destra. Se la rimozione restituisce un elenco vuoto, il risultato è `null`.
- Se l'elenco chiamate del secondo operando non è un sottoelenco contiguo dell'elenco chiamate del primo operando, il risultato dell'operazione è il primo operando.
- Se il primo operando è `null`, il risultato dell'operazione è `null`. Se il secondo operando è `null`, il risultato dell'operazione è il primo operando.

L'esempio seguente illustra come l'operazione `-` esegue la rimozione dei delegati:

[!code-csharp-interactive[delegate removal](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemoval)]

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

[!code-csharp-interactive[-= examples](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#SubtractAndAssign)]

È anche possibile usare l'operatore `-=` per specificare un metodo del gestore eventi quando si elimina la sottoscrizione a un [evento](../keywords/event.md). Per altre informazioni, vedere [Procedura: Sottoscrivere e annullare la sottoscrizione di eventi](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="operator-overloadability"></a>Overload degli operatori

Un tipo definito dall'utente può eseguire l'[overload](../keywords/operator.md) dell'operatore `-`. Quando viene eseguito l'overload di un operatore `-` binario, viene eseguito in modo implicito anche l'overload dell'operatore `-=`. Un tipo definito dall'utente non può eseguire l'overload dell'operatore `-=` in modo esplicito.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni [Operatore meno unario](~/_csharplang/spec/expressions.md#unary-minus-operator) e [Operatore di sottrazione](~/_csharplang/spec/expressions.md#subtraction-operator) di [Specifiche del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Delegati](../../programming-guide/delegates/index.md)
- [Eventi](../../programming-guide/events/index.md)
- [Checked e Unchecked](../keywords/checked-and-unchecked.md)
- [Operatori aritmetici](arithmetic-operators.md)
- [Operatori + e +=](addition-operator.md)
