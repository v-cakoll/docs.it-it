---
title: Operatori di conversione definiti dall'utente - Riferimenti per C#
description: Informazioni su come definire conversioni di tipi impliciti ed espliciti personalizzate in C#.
ms.date: 07/09/2019
f1_keywords:
- explicit_CSharpKeyword
- implicit_CSharpKeyword
helpviewer_keywords:
- explicit keyword [C#]
- implicit keyword [C#]
- conversion operator [C#]
- user-defined conversion [C#]
ms.openlocfilehash: b59fc27be31f1a38e2a6c3cabd82598933b5ed53
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121396"
---
# <a name="user-defined-conversion-operators-c-reference"></a>Operatori di conversione definiti dall'utente (riferimenti per C#)

Un tipo definito dall'utente può definire una conversione implicita o esplicita da o in un altro tipo.

Le conversioni implicite non richiedono una sintassi specifica per essere richiamate e possono essere usate in diverse situazioni, ad esempio durante le chiamate di metodi e assegnazioni. Le conversioni implicite predefinite di C' hanno sempre esito positivo e non generano mai un'eccezione. Anche le conversioni implicite definite dall'utente si devono comportare nello stesso modo. Se una conversione personalizzata può generare un'eccezione o una perdita di informazioni, è necessario definirla come conversione esplicita.

Le conversioni definite dall'utente non vengono considerate dagli operatori [is](type-testing-and-cast.md#is-operator) e [as](type-testing-and-cast.md#as-operator). Usare [un'espressione cast](type-testing-and-cast.md#cast-expression) per richiamare una conversione esplicita definita dall'utente.

Usare `operator` e `implicit` o le parole chiave `explicit` per definire rispettivamente una conversione implicita o esplicita. Il tipo che definisce una conversione deve essere un tipo di origine o un tipo di destinazione della conversione. È possibile definire una conversione tra due tipi definiti dall'utente in uno dei due tipi.

L'esempio seguente illustra come definire una conversione implicita ed esplicita:

[!code-csharp[implicit an explicit conversions](snippets/UserDefinedConversions.cs)]

È anche possibile usare la parola chiave `operator` per eseguire l'overload di un operatore C# predefinito. Per altre informazioni, vedere [Overload degli operatori](operator-overloading.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Operatori di conversione](~/_csharplang/spec/classes.md#conversion-operators)
- [Conversioni definite dall'utente](~/_csharplang/spec/conversions.md#user-defined-conversions)
- [Conversioni implicite](~/_csharplang/spec/conversions.md#implicit-conversions)
- [Conversioni espliciteExplicit conversions](~/_csharplang/spec/conversions.md#explicit-conversions)

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- [Overload degli operatori](operator-overloading.md)
- [Operatori di cast e di test del tipo](type-testing-and-cast.md)
- [Esecuzione del cast e conversioni di tipi](../../programming-guide/types/casting-and-type-conversions.md)
- [Linee guida di progettazione - Operatori di conversione](../../../standard/design-guidelines/operator-overloads.md#conversion-operators)
- [Conversioni esplicite concatenate definite dall'utente in C#](https://docs.microsoft.com/archive/blogs/ericlippert/chained-user-defined-explicit-conversions-in-c)
