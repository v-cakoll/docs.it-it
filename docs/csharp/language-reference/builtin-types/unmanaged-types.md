---
title: Tipi non gestiti - Riferimenti per C#
ms.date: 09/06/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 8a4599514115aa21f17c32848ce203fea704072e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846464"
---
# <a name="unmanaged-types-c-reference"></a>Tipi non gestiti (Riferimenti per C#)

Un tipo è un tipo non gestito se è uno dei tipi seguenti:A type is an **unmanaged type** if it's any of the following types:

- `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` o `bool`
- Qualsiasi tipo [enum](enum.md)
- Qualsiasi tipo [puntatore](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- Qualsiasi tipo [struct](struct.md) definito dall'utente che contiene solo campi di tipi non gestiti e, in C .NET 7.3 e versioni precedenti, non è un tipo costruito (un tipo che include almeno un argomento di tipo)

A partire dalla versione 7.3 di C, è possibile usare il [ `unmanaged` vincolo](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) per specificare che un parametro di tipo è un tipo non puntatore e non nullable non gestito.

A partire dalla versione 8.0 di C, un tipo struct costruito che contiene solo campi di tipi non gestiti è unmanaged, come illustrato nell'esempio seguente:At beginning with C' 8.0, a *constructed* struct type that contains fields of unmanaged types only is also unmanaged, as the following example shows:

[!code-csharp[unmanaged constructed types](snippets/UnmanagedTypes.cs#ProgramExample)]

Uno struct generico può essere l'origine di tipi costruiti non gestiti e non gestiti. Nell'esempio precedente viene definito `Coords<T>` uno struct generico e vengono presentate gli esempi di tipi costruiti non gestiti. L'esempio di non un `Coords<object>`tipo non gestito è . Non è gestito perché ha i campi `object` del tipo, che non è gestito. Se si desidera che *tutti i* tipi `unmanaged` costruiti siano tipi non gestiti, utilizzare il vincolo nella definizione di uno struct generico:

[!code-csharp[unmanaged constraint in type definition](snippets/UnmanagedTypes.cs#AlwaysUnmanaged)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Tipi puntatore](~/_csharplang/spec/unsafe-code.md#pointer-types) nella [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Tipi di puntatore](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Tipi correlati alla memoria e agli intervalli](../../../standard/memory-and-spans/index.md)
- [operatore sizeof](../operators/sizeof.md)
- [Operatore stackalloc](../operators/stackalloc.md)
