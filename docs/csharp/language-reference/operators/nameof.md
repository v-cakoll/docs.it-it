---
title: espressione NameOf-riferimenti per C#
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: d71acf0cf7d5cdcfa5310455af2120fa1f82d567
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135919"
---
# <a name="nameof-expression-c-reference"></a>espressione NameOf (riferimenti per C#)

Un' `nameof` espressione produce il nome di una variabile, di un tipo o di un membro come costante stringa:

[!code-csharp-interactive[nameof expression](snippets/NameOfOperator.cs#Examples)]

Come illustrato nell'esempio precedente, nel caso di un tipo e di uno spazio dei nomi, il nome prodotto in genere non è [completo](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).

Nel caso degli [identificatori Verbatim](../tokens/verbatim.md), il `@` carattere non è la parte di un nome, come illustrato nell'esempio seguente:

[!code-csharp-interactive[nameof verbatim](snippets/NameOfOperator.cs#Verbatim)]

Un' `nameof` espressione viene valutata in fase di compilazione e non ha alcun effetto in fase di esecuzione.

È possibile usare un' `nameof` espressione per rendere più gestibile il codice per il controllo degli argomenti:

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

Un' `nameof` espressione è disponibile in C# 6 e versioni successive.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Espressioni Nameof](~/_csharplang/spec/expressions.md#nameof-expressions) in [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedi anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
