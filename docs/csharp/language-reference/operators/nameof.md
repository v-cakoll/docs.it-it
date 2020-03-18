---
title: Operatore nameof - Riferimenti per C#
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof operator [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: ffbc801acf61bf72db1c88912dc2142a478fa280
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846272"
---
# <a name="nameof-operator-c-reference"></a>Operatore nameof (Riferimenti per C#)

L'operatore `nameof` ottiene il nome di una variabile, di un tipo o di un membro come costante stringa:

[!code-csharp-interactive[nameof operator](snippets/NameOfOperator.cs#Examples)]

Come illustrato nell'esempio precedente, nel caso di un tipo e di uno spazio dei nomi, il nome prodotto in genere non è [completo](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).

L'operatore `nameof` viene valutato in fase di compilazione e non ha alcun effetto in fase di esecuzione.

È possibile usare l'operatore `nameof` per rendere più gestibile il codice per il controllo degli argomenti:

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

L'operatore `nameof` è disponibile in C# 6 e versioni successive.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Espressioni Nameof](~/_csharplang/spec/expressions.md#nameof-expressions) in [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
