---
title: Overload degli operatori - Riferimento C#
description: Informazioni su come eseguire l'overload di un operatore C# e sugli operatori C# che supportano l'overload.
ms.date: 07/05/2019
f1_keywords:
- operator_CSharpKeyword
helpviewer_keywords:
- operator keyword [C#]
- operator overloading [C#]
ms.openlocfilehash: 29ae9fcec414af988019463a51c964d46b009534
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378923"
---
# <a name="operator-overloading-c-reference"></a>Overload degli operatori (Riferimento C#)

Un tipo definito dall'utente può eseguire l'overload di un operatore C# definito in precedenza. Ovvero, un tipo può fornire l'implementazione personalizzata di un'operazione nel caso in cui uno o entrambi gli operandi siano di quel tipo. La sezione [Operatori che supportano l'overload](#overloadable-operators) illustra gli operatori C# che possono essere sottoposti a overload.

Per dichiarare un operatore, usare la parola chiave `operator`. Una dichiarazione di operatore deve soddisfare le regole seguenti:

- Include sia un modificatore `public` che un modificatore `static`.
- Un operatore unario ha un parametro di input. Un operatore binario ha due parametri di input. In entrambi i casi almeno un parametro deve essere di tipo `T` o `T?`, dove `T` è il tipo che contiene la dichiarazione dell'operatore.

L'esempio seguente definisce una struttura semplificata per la rappresentazione di un numero razionale. La struttura esegue l'overload di alcuni [operatori aritmetici](arithmetic-operators.md):

[!code-csharp[fraction example](snippets/OperatorOverloading.cs)]

È possibile estendere l'esempio precedente [definendo una conversione implicita](user-defined-conversion-operators.md) da `int` a `Fraction` . Gli operatori di overload supporteranno quindi gli argomenti di questi due tipi. Diventerà quindi possibile aggiungere un numero intero a una frazione e ottenere di conseguenza una frazione.

È anche possibile usare la parola chiave `operator` per definire una conversione del tipo personalizzata. Per altre informazioni, vedere [Operatori di conversione definiti dall'utente](user-defined-conversion-operators.md).

## <a name="overloadable-operators"></a>Operatori che supportano l'overload

La tabella seguente fornisce informazioni sugli operatori C# che è possibile sottoporre a overload:

| Operatori | Possibilità di overload |
| --------- | --------------- |
|[+x](arithmetic-operators.md#unary-plus-and-minus-operators), [-x](arithmetic-operators.md#unary-plus-and-minus-operators), [!x](boolean-logical-operators.md#logical-negation-operator-), [~x](bitwise-and-shift-operators.md#bitwise-complement-operator-), [++](arithmetic-operators.md#increment-operator-), [--](arithmetic-operators.md#decrement-operator---), [true](true-false-operators.md), [false](true-false-operators.md)|Questi operatori unari possono essere sottoposti a overload.|
|[x + y](addition-operator.md), [x - y](subtraction-operator.md), [x \* y](arithmetic-operators.md#multiplication-operator-), [x / y](arithmetic-operators.md#division-operator-), [x % y](arithmetic-operators.md#remainder-operator-), [x & y](boolean-logical-operators.md#logical-and-operator-), [x &#124; y](boolean-logical-operators.md#logical-or-operator-), [x ^ y](boolean-logical-operators.md#logical-exclusive-or-operator-), [x \<\< y](bitwise-and-shift-operators.md#left-shift-operator-), [x >> y](bitwise-and-shift-operators.md#right-shift-operator-), [x == y](equality-operators.md#equality-operator-), [x != y](equality-operators.md#inequality-operator-), [x \< y](comparison-operators.md#less-than-operator-), [x > y](comparison-operators.md#greater-than-operator-), [x \<= y](comparison-operators.md#less-than-or-equal-operator-), [x >= y](comparison-operators.md#greater-than-or-equal-operator-)|Questi operatori binari possono essere sottoposti a overload. Alcuni operatori devono essere sottoposti a overload in coppia: per altre informazioni, vedere la nota dopo questa tabella.|
|[x && y](boolean-logical-operators.md#conditional-logical-and-operator-), [x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-)|Non è possibile eseguire l'overload degli operatori logici condizionali. Tuttavia, se un tipo con gli operatori di overload [ `true` e `false` ](true-false-operators.md) , inoltre, può eseguire l'overload dell' `&` <code>&#124;</code> operatore o in un certo modo, l' `&&` <code>&#124;&#124;</code> operatore o, rispettivamente, può essere valutato per gli operandi di quel tipo. Per altre informazioni, vedere la sezione [Operatori logici condizionali definiti dall'utente](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) di [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).|
|[&#91;&#93;](member-access-operators.md#indexer-operator-),[`a?[i]`](member-access-operators.md#null-conditional-operators--and-)|L'accesso all'elemento non viene considerato come operatore con supporto dell'overload, ma è possibile definire un [indicizzatore](../../programming-guide/indexers/index.md).|
|[(T) x](type-testing-and-cast.md#cast-expression)|Non è possibile eseguire l'overload dell'operatore cast, ma è possibile definire conversioni di tipi personalizzate che possono essere eseguite da un'espressione cast. Per altre informazioni, vedere [Operatori di conversione definiti dall'utente](user-defined-conversion-operators.md).|
|[+=](arithmetic-operators.md#compound-assignment), [-=](arithmetic-operators.md#compound-assignment) , [\*=](arithmetic-operators.md#compound-assignment) , [/=](arithmetic-operators.md#compound-assignment) , [%=](arithmetic-operators.md#compound-assignment) , [&=](boolean-logical-operators.md#compound-assignment) , [&#124;=](boolean-logical-operators.md#compound-assignment), [^=](boolean-logical-operators.md#compound-assignment) , [\<\<=](bitwise-and-shift-operators.md#compound-assignment) ,[>>=](bitwise-and-shift-operators.md#compound-assignment)|Gli operatori di assegnazione composta non possono essere sottoposti a overload in modo esplicito. Quando viene eseguito l'overload di un operatore binario, viene tuttavia eseguito in modo implicito anche l'overload dell'operatore di assegnazione composta corrispondente, se presente. Ad esempio, `+=` viene valutato usando `+`, che può essere sottoposto a overload.|
|[^ x](member-access-operators.md#index-from-end-operator-), [x = y](assignment-operator.md), [x. y](member-access-operators.md#member-access-expression-), [`x?.y`](member-access-operators.md#null-conditional-operators--and-) , [c? t: f](conditional-operator.md), [x?? y](null-coalescing-operator.md), [x?? = y](null-coalescing-operator.md), [x.. y](member-access-operators.md#range-operator-), [x->y](pointer-related-operators.md#pointer-member-access-operator--), [=>](lambda-operator.md) , [f (x)](member-access-operators.md#invocation-expression-), [As](type-testing-and-cast.md#as-operator), [await](await.md), [checked](../keywords/checked.md), [unchecked](../keywords/unchecked.md), [default](default.md), [delegate](delegate-operator.md), [is](type-testing-and-cast.md#is-operator), [NameOf](nameof.md), [New](new-operator.md), [sizeof](sizeof.md), [stackalloc](stackalloc.md), [typeof](type-testing-and-cast.md#typeof-operator)|Questi operatori non possono essere sottoposti a overload.|

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

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- [Operatori di conversione definiti dall'utente](user-defined-conversion-operators.md)
- [Linee guida di progettazione-overload degli operatori](../../../standard/design-guidelines/operator-overloads.md)
- [Linee guida di progettazione-operatori di uguaglianza](../../../standard/design-guidelines/equality-operators.md)
- [Why are overloaded operators always static in C#? (Perché gli operatori sottoposti a overload sono sempre statici in C#?)](https://docs.microsoft.com/archive/blogs/ericlippert/why-are-overloaded-operators-always-static-in-c)
