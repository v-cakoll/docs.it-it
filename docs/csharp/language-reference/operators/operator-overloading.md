---
title: Overload degli operatori - Riferimento C#
description: Informazioni su come eseguire l'overload di un operatore C# e sugli operatori C# che supportano l'overload.
ms.date: 07/05/2019
f1_keywords:
- operator_CSharpKeyword
helpviewer_keywords:
- operator keyword [C#]
- operator overloading [C#]
ms.openlocfilehash: 77f9d37b7f3232bb1f9bad0466916336801572dd
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512376"
---
# <a name="operator-overloading-c-reference"></a>Overload degli operatori (Riferimento C#)

Un tipo definito dall'utente può eseguire l'overload di un operatore C# definito in precedenza. In altri termini, un tipo può fornire l'implementazione personalizzata di un'operazione quando uno o entrambi gli operandi sono di quel tipo. La sezione [Operatori che supportano l'overload](#overloadable-operators) illustra gli operatori C# che possono essere sottoposti a overload.

Per dichiarare un operatore, usare la parola chiave `operator`. Una dichiarazione di operatore deve soddisfare le regole seguenti:

- Include sia un modificatore `public` che un modificatore `static`.
- Un operatore unario accetta un parametro. Un operatore binario accetta due parametri. In entrambi i casi almeno un parametro deve essere di tipo `T` o `T?`, dove `T` è il tipo che contiene la dichiarazione dell'operatore.

L'esempio seguente definisce una struttura semplificata per la rappresentazione di un numero razionale. La struttura esegue l'overload di alcuni [operatori aritmetici](arithmetic-operators.md):

[!code-csharp[fraction example](~/samples/csharp/language-reference/operators/OperatorOverloading.cs)]

È possibile estendere l'esempio precedente definendo una conversione implicita da `int` in `Fraction`. Gli operatori di overload supporteranno quindi gli argomenti di questi due tipi. Diventerà quindi possibile aggiungere un numero intero a una frazione e ottenere di conseguenza una frazione.

È anche possibile usare la parola chiave `operator` per definire una conversione del tipo personalizzata. Per altre informazioni, vedere [Operatori di conversione definiti dall'utente](user-defined-conversion-operators.md).

## <a name="overloadable-operators"></a>Operatori che supportano l'overload

La tabella seguente fornisce informazioni sugli operatori C# che è possibile sottoporre a overload:

| Operatori | Possibilità di overload |
| --------- | --------------- |
|[+](arithmetic-operators.md#unary-plus-and-minus-operators), [-](arithmetic-operators.md#unary-plus-and-minus-operators), [!](boolean-logical-operators.md#logical-negation-operator-), [~](bitwise-and-shift-operators.md#bitwise-complement-operator-), [++](arithmetic-operators.md#increment-operator-), [--](arithmetic-operators.md#decrement-operator---), [true](true-false-operators.md), [false](true-false-operators.md)|Questi operatori unari possono essere sottoposti a overload.|
|[+](addition-operator.md), [-](subtraction-operator.md), [\*](arithmetic-operators.md#multiplication-operator-), [/](arithmetic-operators.md#division-operator-), [%](arithmetic-operators.md#remainder-operator-), [&](boolean-logical-operators.md#logical-and-operator-), [&#124;](boolean-logical-operators.md#logical-or-operator-), [^](boolean-logical-operators.md#logical-exclusive-or-operator-), [\<\<](bitwise-and-shift-operators.md#left-shift-operator-), [>>](bitwise-and-shift-operators.md#right-shift-operator-), [==](equality-operators.md#equality-operator-), [!=](equality-operators.md#inequality-operator-), [\<](comparison-operators.md#less-than-operator-), [>](comparison-operators.md#greater-than-operator-), [\<=](comparison-operators.md#less-than-or-equal-operator-), [>=](comparison-operators.md#greater-than-or-equal-operator-)|Questi operatori binari possono essere sottoposti a overload. Alcuni operatori devono essere sottoposti a overload in coppia: per altre informazioni, vedere la nota dopo questa tabella.|
|[&&](boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124;](boolean-logical-operators.md#conditional-logical-or-operator-)|Non è possibile eseguire l'overload degli operatori logici condizionali. Se tuttavia, un tipo definito con gli operatori con overload [`true` e `false`](true-false-operators.md) esegue anche l'overload dell'operatore `&` o <code>&#124;</code> con una determinata modalità, l'operatore `&&` o <code>&#124;&#124;</code> rispettivamente può essere valutato per gli operandi di quel tipo. Per altre informazioni, vedere la sezione [Operatori logici condizionali definiti dall'utente](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) di [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).|
|[&#91;&#93;](member-access-operators.md#indexer-operator-)|L'accesso all'elemento non viene considerato come operatore con supporto dell'overload, ma è possibile definire un [indicizzatore](../../programming-guide/indexers/index.md).|
|[(T)x](type-testing-and-conversion-operators.md#cast-operator-)|L'operatore cast non può essere sottoposto a overload, ma è possibile definire nuovi operatori di conversione. Per altre informazioni, vedere [Operatori di conversione definiti dall'utente](user-defined-conversion-operators.md).|
|[+=](arithmetic-operators.md#compound-assignment), [-=](arithmetic-operators.md#compound-assignment), [\*=](arithmetic-operators.md#compound-assignment), [/=](arithmetic-operators.md#compound-assignment), [%=](arithmetic-operators.md#compound-assignment), [&=](boolean-logical-operators.md#compound-assignment), [&#124;=](boolean-logical-operators.md#compound-assignment), [^=](boolean-logical-operators.md#compound-assignment), [\<\<=](bitwise-and-shift-operators.md#compound-assignment), [>>=](bitwise-and-shift-operators.md#compound-assignment)|Gli operatori di assegnazione composta non possono essere sottoposti a overload in modo esplicito. Quando viene eseguito l'overload di un operatore binario, viene tuttavia eseguito in modo implicito anche l'overload dell'operatore di assegnazione composta corrispondente, se presente. Ad esempio, `+=` viene valutato usando `+`, che può essere sottoposto a overload.|
|[=](assignment-operator.md), [.](member-access-operators.md#member-access-operator-), [?:](conditional-operator.md), [??](null-coalescing-operator.md), [->](pointer-related-operators.md#pointer-member-access-operator--), [=>](lambda-operator.md), [f(x)](member-access-operators.md#invocation-operator-), [as](type-testing-and-conversion-operators.md#as-operator), [checked](../keywords/checked.md), [unchecked](../keywords/unchecked.md), [default](../../programming-guide/statements-expressions-operators/default-value-expressions.md), [delegate](delegate-operator.md), [is](type-testing-and-conversion-operators.md#is-operator), [nameof](nameof.md), [new](new-operator.md), [sizeof](sizeof.md), [stackalloc](stackalloc.md), [typeof](type-testing-and-conversion-operators.md#typeof-operator)|Questi operatori non possono essere sottoposti a overload.|

> [!NOTE]
> Gli operatori di confronto devono essere sottoposti a overload in coppie. Se uno dei due operatori di una coppia viene sottoposto a overload, anche l'altro operatore della coppia deve essere sottoposto a overload. Le associazioni sono le seguenti:
>
> - Operatori `==` e `!=`
> - Operatori `<` e `>`
> - Operatori `<=` e `>=`

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Overload degli operatori](~/_csharplang/spec/expressions.md#operator-overloading)
- [Operatori](~/_csharplang/spec/classes.md#operators)

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Operatori C#](index.md)
- [Operatori di conversione definiti dall'utente](user-defined-conversion-operators.md)
- [Why are overloaded operators always static in C#?](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/) (Perché gli operatori sottoposti a overload sono sempre statici in C#?)
