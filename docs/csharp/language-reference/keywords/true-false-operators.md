---
title: Operatori true e false - Riferimenti per C#
ms.custom: seodec18
ms.date: 12/10/2018
helpviewer_keywords:
- false operator [C#]
- true operator [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: 869eeab6515340b2f1884ab7206979e83654a10b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59328244"
---
# <a name="true-and-false-operators-c-reference"></a>Operatori true e false (Riferimenti per C#)

L'operatore `true` restituisce il valore [bool](bool.md) `true` per indicare che un operando è indubbiamente true. L'operatore `false` restituisce il valore `bool` `true` per indicare che un operando è indubbiamente false. Gli operatori `true` e `false` non sono necessariamente complementari tra loro. Questo significa che entrambi gli operatori `true` e `false` possono restituire il valore `bool` `false` per lo stesso operando. Se un tipo definisce uno dei due operatori, deve definire anche l'altro operatore.

Se un tipo con gli operatori `true` e `false` definiti esegue l'[overload](operator.md) dell'[operatore logico OR](../operators/boolean-logical-operators.md#logical-or-operator-) `|` o dell'[operatore AND logico](../operators/boolean-logical-operators.md#logical-and-operator-) `&` in un certo modo, l'[operatore OR logico condizionale](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) `||` oppure l'[operatore AND logico condizionale](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) `&&`, rispettivamente, può essere valutato per gli operandi di quel tipo. Per altre informazioni, vedere la sezione [Operatori logici condizionali definiti dall'utente](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) di [Specifica del linguaggio C#](../language-specification/index.md).

Un tipo con l'operatore `true` definito può essere il tipo di un risultato di un'espressione condizionale di controllo nelle istruzioni [if](if-else.md), [do](do.md), [while](while.md) e [for](for.md) e nell'[operatore condizionale `?:`](../operators/conditional-operator.md). Per altre informazioni, vedere la sezione [Espressioni booleane](~/_csharplang/spec/expressions.md#boolean-expressions) della [specifica del linguaggio C#](../language-specification/index.md).

> [!TIP]
> Usare il tipo `bool?` se occorre supportare la logica a tre valori, ad esempio quando si lavora con database che supportano un tipo booleano a tre valori. In C# sono disponibili gli operatori `&` e `|` che supportano la logica a tre valori con gli operandi `bool?`. Per altre informazioni, vedere la sezione [Operatori logici booleani nullable](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) dell'articolo [Operatori logici booleani](../operators/boolean-logical-operators.md).

L'esempio seguente presenta il tipo che definisce entrambi gli operatori `true` e `false`. Esegue inoltre l'overload dell'operatore AND logico `&` in un modo tale che anche l'operatore `&&` può essere valutato per gli operandi di quel tipo.

[!code-csharp-interactive[true and false operators example](~/samples/snippets/csharp/keywords/TrueFalseOperatorsExample.cs)]

Si noti il comportamento che causa il corto circuito dell'operatore `&&`. Quando il metodo `GetFuelLaunchStatus` restituisce `LaunchStatus.Red`, il secondo operando dell'operatore `&&` non viene valutato. Il motivo è che `LaunchStatus.Red` è indubbiamente false. Pertanto il risultato dell'operatore AND logico non dipende dal valore del secondo operando. L'output dell'esempio è il seguente:

```console
Getting fuel launch status...
Wait!
```

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Operatori [C#]](../operators/index.md)
- [`true` valore letterale](true-literal.md)
- [`false` valore letterale](false-literal.md)