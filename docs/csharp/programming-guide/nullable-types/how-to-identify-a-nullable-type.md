---
title: 'Procedura: identificare un tipo di valore Nullable- C# Guida alla programmazione'
ms.custom: seodec18
description: Informazioni su come determinare se un tipo è un tipo di valore nullable o se un'istanza è un tipo di valore Nullable
ms.date: 09/26/2019
helpviewer_keywords:
- nullable value types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: 15b1ffedf57648955ee5a004514841a5d140292b
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392615"
---
# <a name="how-to-identify-a-nullable-value-type-c-programming-guide"></a>Procedura: identificare un tipo di valore Nullable (C# guida per programmatori)

Nell'esempio seguente viene illustrato come determinare se un'istanza di <xref:System.Type?displayProperty=nameWithType> rappresenta un tipo di valore Nullable generico chiuso, ovvero il tipo <xref:System.Nullable%601?displayProperty=nameWithType> con un parametro di tipo specificato `T`:

[!code-csharp-interactive[whether Type is nullable](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#1)]

Come illustrato nell'esempio, è possibile usare l'operatore [typeof](../../language-reference/operators/type-testing-and-cast.md#typeof-operator) per creare un oggetto <xref:System.Type?displayProperty=nameWithType>.

Se si desidera determinare se un'istanza è di un tipo di valore Nullable, non utilizzare il metodo <xref:System.Object.GetType%2A?displayProperty=nameWithType> per ottenere un'istanza di <xref:System.Type> da testare con il codice precedente. Quando si chiama il metodo <xref:System.Object.GetType%2A?displayProperty=nameWithType> su un'istanza di un tipo di valore Nullable, l'istanza viene sottoposta a [boxing](using-nullable-types.md#boxing-and-unboxing) <xref:System.Object>. Poiché la conversione boxing di un'istanza non null di un tipo di valore Nullable equivale alla conversione boxing di un valore del tipo sottostante, <xref:System.Object.GetType%2A> restituisce un oggetto <xref:System.Type> che rappresenta il tipo sottostante di un tipo di valore Nullable:

[!code-csharp-interactive[GetType example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#2)]

Non usare l'operatore [is](../../language-reference/keywords/is.md) per determinare se un'istanza è un tipo di valore Nullable. Come illustrato nell'esempio seguente, non è possibile distinguere i tipi di istanze di un tipo di valore nullable e il tipo sottostante usando l'operatore `is`:

[!code-csharp-interactive[is operator example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#3)]

È possibile utilizzare il codice presentato nell'esempio seguente per determinare se un'istanza è un tipo di valore Nullable:

[!code-csharp-interactive[whether an instance is of a nullable type](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#4)]

## <a name="see-also"></a>Vedere anche

- [Tipi valore nullable](index.md)
- [Utilizzo di tipi di valore Nullable](using-nullable-types.md)
- <xref:System.Nullable.GetUnderlyingType%2A>
