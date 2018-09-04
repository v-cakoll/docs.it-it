---
title: 'Procedura: identificare un tipo nullable (Guida per programmatori C#)'
description: Informazioni su come determinare se un tipo è un tipo nullable o se un'istanza è di un tipo nullable
ms.date: 08/06/2018
helpviewer_keywords:
- nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: bb7ab2b8c13c2b8b4b6cd60e7959a391cd7e75c1
ms.sourcegitcommit: bd4fa78f5a46133efdead1bc692a9aa2811d7868
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2018
ms.locfileid: "42754956"
---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a>Procedura: identificare un tipo nullable (Guida per programmatori C#)

L'esempio seguente illustra come determinare se un'istanza <xref:System.Type?displayProperty=nameWithType> rappresenta un tipo nullable:

[!code-csharp-interactive[whether Type is nullable](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#1)]

Come illustrato nell'esempio, è possibile usare l'operatore [typeof](../../language-reference/keywords/typeof.md) per creare un oggetto <xref:System.Type?displayProperty=nameWithType>.  
  
Se si vuole determinare se un'istanza è di un tipo nullable, non usare il metodo <xref:System.Object.GetType%2A?displayProperty=nameWithType> per ottenere un'istanza <xref:System.Type> da testare con il codice precedente. Quando si chiama il metodo <xref:System.Object.GetType%2A?displayProperty=nameWithType> in un'istanza di un tipo nullable, viene eseguita la [conversione boxing](using-nullable-types.md#boxing-and-unboxing) dell'istanza a <xref:System.Object>. Poiché la conversione boxing di un'istanza non Null di un tipo nullable è equivalente alla conversione boxing di un valore del tipo sottostante, <xref:System.Object.GetType%2A> restituisce un oggetto <xref:System.Type> che rappresenta il tipo sottostante di un tipo nullable:

[!code-csharp-interactive[GetType example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#2)]

Non usare l'operatore [is](../../language-reference/keywords/is.md) per determinare se un'istanza è di un tipo nullable. Come illustrato nell'esempio seguente, non è possibile distinguere i tipi di istanze di un tipo nullable e del relativo tipo sottostante con l'operatore `is`:

[!code-csharp-interactive[is operator example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#3)]

È possibile usare il codice riportato nell'esempio seguente per determinare se un'istanza è di un tipo nullable:

[!code-csharp-interactive[whether an instance is of a nullable type](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#4)]
  
## <a name="see-also"></a>Vedere anche

[Tipi nullable](index.md)  
[Uso dei tipi nullable](using-nullable-types.md)  
<xref:System.Nullable.GetUnderlyingType%2A>  
