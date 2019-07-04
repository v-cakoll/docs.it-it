---
title: Operatori true e false - Riferimenti per C#
ms.custom: seodec18
ms.date: 12/10/2018
helpviewer_keywords:
- false operator [C#]
- true operator [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: f4391e73b17c3700dc04240e1289b523c4bdc596
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025026"
---
# <a name="true-and-false-operators-c-reference"></a>Operatori true e false (Riferimenti per C#)

L'operatore `true` restituisce il valore [bool](../keywords/bool.md) `true` per indicare che un operando è indubbiamente true. L'operatore `false` restituisce il valore `bool` `true` per indicare che un operando è indubbiamente false. Gli operatori `true` e `false` non sono necessariamente complementari tra loro. Questo significa che entrambi gli operatori `true` e `false` possono restituire il valore `bool` `false` per lo stesso operando. Se un tipo definisce uno dei due operatori, deve definire anche l'altro operatore.

Se un tipo con gli operatori `true` e `false` definiti esegue l'[overload](../keywords/operator.md) dell'[operatore logico OR](boolean-logical-operators.md#logical-or-operator-) `|` o dell'[operatore AND logico](boolean-logical-operators.md#logical-and-operator-) `&` in un certo modo, l'[operatore OR logico condizionale](boolean-logical-operators.md#conditional-logical-or-operator-) `||` oppure l'[operatore AND logico condizionale](boolean-logical-operators.md#conditional-logical-and-operator-) `&&`, rispettivamente, può essere valutato per gli operandi di quel tipo. Per altre informazioni, vedere la sezione [Operatori logici condizionali definiti dall'utente](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) di [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

Un tipo con l'operatore `true` definito può essere il tipo di un risultato di un'espressione condizionale di controllo nelle istruzioni [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md) e [for](../keywords/for.md) e nell'[operatore condizionale `?:`](conditional-operator.md). Per altre informazioni, vedere la sezione [Espressioni booleane](~/_csharplang/spec/expressions.md#boolean-expressions) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

> [!TIP]
> Usare il tipo `bool?` se occorre supportare la logica a tre valori, ad esempio quando si lavora con database che supportano un tipo booleano a tre valori. In C# sono disponibili gli operatori `&` e `|` che supportano la logica a tre valori con gli operandi `bool?`. Per altre informazioni, vedere la sezione [Operatori logici booleani nullable](boolean-logical-operators.md#nullable-boolean-logical-operators) dell'articolo [Operatori logici booleani](boolean-logical-operators.md).

L'esempio seguente presenta il tipo che definisce entrambi gli operatori `true` e `false`. Esegue inoltre l'overload dell'operatore AND logico `&` in un modo tale che anche l'operatore `&&` può essere valutato per gli operandi di quel tipo.

[!code-csharp[true and false operators example](~/samples/csharp/language-reference/operators/TrueFalseOperators.cs)]

Si noti il comportamento che causa il corto circuito dell'operatore `&&`. Quando il metodo `GetFuelLaunchStatus` restituisce `LaunchStatus.Red`, il secondo operando dell'operatore `&&` non viene valutato. Il motivo è che `LaunchStatus.Red` è indubbiamente false. Pertanto il risultato dell'operatore AND logico non dipende dal valore del secondo operando. L'output dell'esempio è il seguente:

```console
Getting fuel launch status...
Wait!
```

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Operatori C#](index.md)
- [Valore letterale true](../keywords/true-literal.md)
- [Valore letterale false](../keywords/false-literal.md)
