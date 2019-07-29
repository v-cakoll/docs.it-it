---
title: Tipi non gestiti - Riferimenti per C#
ms.date: 07/23/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 2b675be5dbc61006725549f4b69284326650401d
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512067"
---
# <a name="unmanaged-types-c-reference"></a>Tipi non gestiti (Riferimenti per C#)

Un **tipo non gestito** è un tipo che non è un tipo riferimento o un tipo costruito (un tipo che include almeno un argomento di tipo) e che non contiene campi di tipo riferimento o di tipo costruito a qualsiasi livello di annidamento. In altre parole, un tipo non gestito è uno dei seguenti:

- `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` o `bool`
- Qualsiasi tipo [enum](../keywords/enum.md)
- Qualsiasi tipo [puntatore](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- Qualsiasi tipo [struct](../keywords/struct.md) definito dall'utente che non sia un tipo costruito e che contenga campi solo di tipi non gestiti

A partire da C# 7.3, è possibile usare il [vincolo `unmanaged`](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) per specificare che il parametro di tipo deve essere un tipo non gestito non puntatore.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Tipi puntatore](~/_csharplang/spec/unsafe-code.md#pointer-types) nella [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Tipi di puntatori](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Tipi correlati alla memoria e agli intervalli](../../../standard/memory-and-spans/index.md)
- [Operatore sizeof](../operators/sizeof.md)
- [Operatore stackalloc](../operators/stackalloc.md)
