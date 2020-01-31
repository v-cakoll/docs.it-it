---
title: struct - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 8d9a23a0813423571c894758257b284ad67a72e2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744655"
---
# <a name="struct-c-reference"></a>struct (Riferimenti per C#)

Un `struct` è un tipo di valore generalmente usato per incapsulare piccoli gruppi di variabili correlate, ad esempio le coordinate di un rettangolo o le caratteristiche di un articolo in un inventario. Nell'esempio che segue è illustrata una semplice dichiarazione struct:

```csharp
public struct Book
{
    public decimal price;
    public string title;
    public string author;
}
```

## <a name="remarks"></a>Note

Gli struct possono contenere anche [costruttori](../../programming-guide/classes-and-structs/constructors.md), [costanti](../../programming-guide/classes-and-structs/constants.md), [campi](../../programming-guide/classes-and-structs/fields.md), [metodi](../../programming-guide/classes-and-structs/methods.md), [proprietà](../../programming-guide/classes-and-structs/properties.md), [indicizzatori](../../programming-guide/indexers/index.md), [operatori](../operators/index.md), [eventi](../../programming-guide/events/index.md) e [tipi annidati](../../programming-guide/classes-and-structs/nested-types.md), anche se è consigliabile trasformare il tipo in una classe se sono necessari molti di questi membri.

Per i relativi esempi, vedere [Uso di struct](../../programming-guide/classes-and-structs/using-structs.md).

Gli struct possono implementare un'interfaccia, ma non possono ereditare da altri struct. Per questo motivo i membri di struct non possono essere dichiarati come `protected`.

Per altre informazioni, vedere [Struct](../../programming-guide/classes-and-structs/structs.md).

## <a name="examples"></a>Esempi

Per altre informazioni ed esempi, vedere [Uso di struct](../../programming-guide/classes-and-structs/using-structs.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per i relativi esempi, vedere [Uso di struct](../../programming-guide/classes-and-structs/using-structs.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Parole chiave C#](index.md)
- [Tabella dei tipi incorporati](built-in-types-table.md)
- [Tipi valore](../builtin-types/value-types.md)
- [classe](class.md)
- [interface](interface.md)
- [Classi e struct](../../programming-guide/classes-and-structs/index.md)
