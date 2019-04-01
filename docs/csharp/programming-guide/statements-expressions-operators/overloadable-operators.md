---
title: Operatori che supportano l'overload - Guida per programmatori C#
ms.custom: seodec18
ms.date: 08/27/2018
helpviewer_keywords:
- C# language, operator overloading
- operator overloading [C#]
ms.assetid: 390d9d01-79fc-40ab-9ed3-0bf448da1b6a
ms.openlocfilehash: b4e4c3c6f73a10008093d727929f74e77c063239
ms.sourcegitcommit: 4a8c2b8d0df44142728b68ebc842575840476f6d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2019
ms.locfileid: "58545494"
---
# <a name="overloadable-operators-c-programming-guide"></a>Operatori che supportano l'overload (Guida per programmatori C#)

C# consente ai tipi definiti dall'utente di eseguire l'overload degli operatori definendo le funzioni membro statiche mediante la parola chiave [operator](../../language-reference/keywords/operator.md). Non tutti gli operatori, tuttavia, possono essere sottoposti a overload e gli altri sono soggetti alle restrizioni elencate in questa tabella:

| Operatori | Possibilità di overload |
| --------- | --------------- |
|[+](../../language-reference/operators/addition-operator.md), [-](../../language-reference/operators/subtraction-operator.md), [!](../../language-reference/operators/logical-negation-operator.md), [~](../../language-reference/operators/bitwise-complement-operator.md), [++](../../language-reference/operators/arithmetic-operators.md#increment-operator-), [--](../../language-reference/operators/arithmetic-operators.md#decrement-operator---), [true](../../language-reference/keywords/true-false-operators.md), [false](../../language-reference/keywords/true-false-operators.md)|Questi operatori unari possono essere sottoposti a overload.|
|[+](../../language-reference/operators/addition-operator.md), [-](../../language-reference/operators/subtraction-operator.md), [\*](../../language-reference/operators/arithmetic-operators.md#multiplication-operator-), [/](../../language-reference/operators/arithmetic-operators.md#division-operator-), [%](../../language-reference/operators/arithmetic-operators.md#remainder-operator-), [&](../../language-reference/operators/and-operator.md), [&#124;](../../language-reference/operators/or-operator.md), [^](../../language-reference/operators/xor-operator.md), [\<\<](../../language-reference/operators/left-shift-operator.md), [>>](../../language-reference/operators/right-shift-operator.md)|Questi operatori binari possono essere sottoposti a overload.|
|[==](../../language-reference/operators/equality-operators.md#equality-operator-), [!=](../../language-reference/operators/equality-operators.md#inequality-operator-), [\<](../../language-reference/operators/less-than-operator.md), [>](../../language-reference/operators/greater-than-operator.md), [\<=](../../language-reference/operators/less-than-equal-operator.md), [>=](../../language-reference/operators/greater-than-equal-operator.md)|Gli operatori di confronto possono essere sottoposti a overload (vedere però la nota dopo questa tabella).|
|[&&](../../language-reference/operators/conditional-and-operator.md), [&#124;&#124;](../../language-reference/operators/conditional-or-operator.md)|Gli operatori logici condizionali non possono essere sottoposti a overload, ma vengono valutati con `&` e <code>&#124;</code> che possono essere sottoposti a overload.|
|[&#91;&#93;](../../language-reference/operators/index-operator.md)|L'operatore di indicizzazione matrice non può essere sottoposto a overload, ma è possibile definire gli [indicizzatori](../indexers/index.md).|
|[(T)x](../../language-reference/operators/invocation-operator.md)|L'operatore cast non può essere sottoposto a overload, ma è possibile definire nuovi operatori di conversione (vedere [explicit](../../language-reference/keywords/explicit.md) e [implicit](../../language-reference/keywords/implicit.md)).|
|[+=](../../language-reference/operators/addition-assignment-operator.md), [-=](../../language-reference/operators/subtraction-assignment-operator.md), [\*=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [/=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [%=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [&=](../../language-reference/operators/and-assignment-operator.md), [&#124;=](../../language-reference/operators/or-assignment-operator.md), [^=](../../language-reference/operators/xor-assignment-operator.md), [\<\<=](../../language-reference/operators/left-shift-assignment-operator.md), [>>=](../../language-reference/operators/right-shift-assignment-operator.md)|Gli operatori di assegnazione non possono essere sottoposti a overload in modo esplicito. Quando viene eseguito l'overload di un operatore binario, viene tuttavia eseguito anche in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente. Ad esempio, `+=` viene valutato usando `+`, che può essere sottoposto a overload.|
|[=](../../language-reference/operators/assignment-operator.md), [.](../../language-reference/operators/member-access-operator.md), [?:](../../language-reference/operators/conditional-operator.md), [??](../../language-reference/operators/null-coalescing-operator.md), [->](../../language-reference/operators/dereference-operator.md), [=>](../../language-reference/operators/lambda-operator.md), [f(x)](../../language-reference/operators/invocation-operator.md), [as](../../language-reference/keywords/as.md), [checked](../../language-reference/keywords/checked.md), [unchecked](../../language-reference/keywords/unchecked.md), [default](../../programming-guide/statements-expressions-operators/default-value-expressions.md), [delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md), [is](../../language-reference/keywords/is.md), [new](../../language-reference/keywords/new.md), [sizeof](../../language-reference/keywords/sizeof.md), [typeof](../../language-reference/keywords/typeof.md)|Questi operatori non possono essere sottoposti a overload.|

> [!NOTE]
> Gli operatori di confronto, se sottoposti a overload, devono esserlo in coppie, ovvero, se `==` è sottoposto a overload, deve esserlo anche `!=`. È vero anche il contrario e se `!=` è sottoposto a overload deve esserlo anche `==`. Lo stesso vale per gli operatori di confronto `<` e `>` e per `<=` e `>=`.

Per informazioni su come eseguire l'overload di un operatore, vedere l'articolo relativo alla parola chiave [operator](../../language-reference/keywords/operator.md).

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Istruzioni, espressioni e operatori](index.md)
- [Operatori](operators.md)
- [Operatori C#](../../language-reference/operators/index.md)
- [Why are overloaded operators always static in C#?](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/) (Perché gli operatori sottoposti a overload sono sempre statici in C#?)
