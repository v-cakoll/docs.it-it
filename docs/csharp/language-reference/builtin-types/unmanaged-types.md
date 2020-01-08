---
title: Tipi non gestiti - Riferimenti per C#
ms.date: 09/06/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 97aa4dd629e385dbe9641d82a7da21a0aaa63e92
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75342585"
---
# <a name="unmanaged-types-c-reference"></a>Tipi non gestiti (Riferimenti per C#)

Un tipo è un **tipo non gestito** se è uno dei tipi seguenti:

- `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` o `bool`
- Qualsiasi tipo [enum](enum.md)
- Qualsiasi tipo [puntatore](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- Qualsiasi tipo [struct](../keywords/struct.md) definito dall'utente che contiene campi solo di tipi non gestiti e, in C# 7,3 e versioni precedenti, non è un tipo costruito (un tipo che include almeno un argomento di tipo)

A partire C# da 7,3, è possibile usare il [vincolo`unmanaged`](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) per specificare che un parametro di tipo è un tipo non gestito non nullable.

A partire C# da 8,0, viene anche gestito un tipo struct *costruito* che contiene campi di tipi non gestiti, come illustrato nell'esempio seguente:

[!code-csharp[unmanaged constructed types](~/samples/csharp/language-reference/builtin-types/UnmanagedTypes.cs#ProgramExample)]

Uno struct generico può essere l'origine dei tipi costruiti non gestiti e non gestiti. Nell'esempio precedente viene definito uno struct generico `Coords<T>` e vengono presentati gli esempi di tipi costruiti non gestiti. L'esempio di non è un tipo non gestito è `Coords<object>`. Non è gestita perché contiene i campi del tipo di `object`, che non è gestito. Se si desidera che *tutti i* tipi costruiti siano tipi non gestiti, utilizzare il `unmanaged` vincolo nella definizione di uno struct generico:

[!code-csharp[unmanaged constraint in type definition](~/samples/csharp/language-reference/builtin-types/UnmanagedTypes.cs#AlwaysUnmanaged)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Tipi puntatore](~/_csharplang/spec/unsafe-code.md#pointer-types) nella [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Tipi di puntatori](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Tipi correlati alla memoria e agli intervalli](../../../standard/memory-and-spans/index.md)
- [Operatore sizeof](../operators/sizeof.md)
- [Operatore stackalloc](../operators/stackalloc.md)
