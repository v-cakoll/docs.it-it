---
title: Operatori true e false - Riferimenti per C#
ms.custom: seodec18
ms.date: 12/10/2018
helpviewer_keywords:
- false operator [C#]
- true operator [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: 0a75566fdb6222157ecda12a50fd78e22f92fcb4
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245732"
---
# <a name="true-and-false-operators-c-reference"></a>Operatori true e false (Riferimenti per C#)

L'operatore `true` restituisce il valore [bool](bool.md) `true` per indicare che un operando è indubbiamente true. L'operatore `false` restituisce il valore `bool` `true` per indicare che un operando è indubbiamente false. Gli operatori `true` e `false` non sono necessariamente complementari tra loro. Questo significa che entrambi gli operatori `true` e `false` possono restituire il valore `bool` `false` per lo stesso operando. Se un tipo definisce uno dei due operatori, deve definire anche l'altro operatore.

Se un tipo con gli operatori `true` e `false` definiti esegue l'[overload](operator.md) dell'[operatore logico OR](../operators/or-operator.md) `|` o dell'[operatore AND logico](../operators/and-operator.md) `&` in un certo modo, l'[operatore OR logico condizionale](../operators/conditional-or-operator.md) `||` oppure l'[operatore AND logico condizionale](../operators/conditional-and-operator.md) `&&`, rispettivamente, può essere valutato per gli operandi di quel tipo. Per altre informazioni, vedere la sezione [Operatori logici condizionali definiti dall'utente](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) di [Specifica del linguaggio C#](../language-specification/index.md).

Un tipo con l'operatore `true` definito può essere il tipo di un risultato di un'espressione condizionale di controllo nelle istruzioni [if](if-else.md), [do](do.md), [while](while.md) e [for](for.md) e nell'[operatore condizionale `?:`](../operators/conditional-operator.md). Per altre informazioni, vedere la sezione [Espressioni booleane](~/_csharplang/spec/expressions.md#boolean-expressions) della [specifica del linguaggio C#](../language-specification/index.md).

> [!TIP]
> Usare il tipo `bool?` se occorre supportare la logica a tre valori, ad esempio quando si lavora con database che supportano un tipo logico a tre valori. Per altre informazioni, vedere la sezione [Tipo bool?](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) dell'articolo [Uso dei tipi nullable](../../programming-guide/nullable-types/using-nullable-types.md).

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
- [Operatori C#](../operators/index.md)
- [Valore letterale `true`](true-literal.md)
- [Valore letterale `false`](false-literal.md)