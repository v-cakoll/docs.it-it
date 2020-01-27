---
title: Value types - C# reference
ms.date: 01/22/2020
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 6b96d65f657f2af1af5c9a245e956640ee06260e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76748517"
---
# <a name="value-types-c-reference"></a>Value types (C# reference)

*Value types* and [reference types](../keywords/reference-types.md) are the two main categories of C# types. A variable of a value type contains an instance of the type. This differs from a variable of a reference type, which contains a reference to an instance of the type. By default, on [assignment](../operators/assignment-operator.md), passing an argument to a method, or returning a method result, variable values are copied. In the case of value-type variables, the corresponding type instances are copied. L'esempio seguente illustra questo comportamento:

[!code-csharp[copy of values](~/samples/csharp/language-reference/builtin-types/ValueTypes.cs#ValueTypeCopied)]

As the preceding example shows, operations on a value-type variable affect only that instance of the value type, stored in the variable.

If a value type contains a data member of a reference type, only the reference to the instance of the reference type is copied when a value-type instance is copied. Both the copy and original value-type instance have access to the same reference-type instance. L'esempio seguente illustra questo comportamento:

[!code-csharp[shallow copy](~/samples/csharp/language-reference/builtin-types/ValueTypes.cs#ShallowCopy)]

> [!NOTE]
> To make your code less error-prone and more robust, define and use immutable value types. This article uses mutable value types only for demonstration purposes.

## <a name="kinds-of-value-types"></a>Kinds of value types

A value type can be one of the two following kinds:

- a [structure type](../keywords/struct.md), which encapsulates data and related functionality
- un [tipo di enumerazione](enum.md), definito da un set di costanti denominate e rappresenta una scelta o una combinazione di scelte

Un [tipo di valore nullable](nullable-value-types.md) `T?` rappresenta tutti i valori del tipo di valore sottostante `T` e un valore [null](../keywords/null.md) aggiuntivo. Non è possibile assegnare `null` a una variabile di un tipo di valore, a meno che non si tratti di un tipo di valore Nullable.

## <a name="built-in-value-types"></a>Tipi di valore predefiniti

C#in sono disponibili i tipi di valore predefiniti seguenti, noti anche come *tipi semplici*:

- [Tipi numerici integrali](integral-numeric-types.md)
- [Tipi numerici a virgola mobile](floating-point-numeric-types.md)
- [bool](bool.md) che rappresenta un valore booleano
- [char](char.md) che rappresenta un carattere UTF-16 Unicode

Tutti i tipi semplici sono tipi di struttura e differiscono da quelli di altri tipi di struttura in quanto consentono determinate operazioni aggiuntive:

- È possibile utilizzare valori letterali per fornire un valore di un tipo semplice. Ad esempio, `'A'` è un valore letterale del tipo `char` e `2001` è un valore letterale del tipo `int`.

- È possibile dichiarare costanti dei tipi semplici con la parola chiave [const](../keywords/const.md). Non è possibile avere costanti di altri tipi di struttura.

- Le espressioni costanti, i cui operandi sono tutte costanti dei tipi semplici, vengono valutate in fase di compilazione.

A partire C# da 7,0 C# , supporta le [Tuple di valori](../../tuples.md). Una tupla di valori è un tipo di valore, ma non un tipo semplice.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Tipi valore](~/_csharplang/spec/types.md#value-types)
- [Tipi semplici](~/_csharplang/spec/types.md#simple-types)
- [Variabili](~/_csharplang/spec/variables.md)

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- <xref:System.ValueType?displayProperty=nameWithType>
- [Tipi riferimento](../keywords/reference-types.md)
