---
title: nomedellespressione - Informazioni di riferimento su C
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 5a68161be7bb03122d2a63ccef4365c5853862b2
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507139"
---
# <a name="nameof-expression-c-reference"></a>nomedell espressione (riferimenti per C

Un'espressione produce il nome di una variabile, un tipo o un membro come costante di stringa:A `nameof` expression produces the name of a variable, type, or member as the string constant:

[!code-csharp-interactive[nameof expression](snippets/NameOfOperator.cs#Examples)]

Come illustrato nell'esempio precedente, nel caso di un tipo e di uno spazio dei nomi, il nome prodotto in genere non è [completo](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).

Un'espressione `nameof` viene valutata in fase di compilazione e non ha alcun effetto in fase di esecuzione.

È possibile `nameof` utilizzare un'espressione per rendere più gestibile il codice di controllo degli argomenti:You can use a expression to make the argument-checking code more maintainable:

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

Un'espressione `nameof` è disponibile in C , 6 e versioni successive.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Espressioni Nameof](~/_csharplang/spec/expressions.md#nameof-expressions) in [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
