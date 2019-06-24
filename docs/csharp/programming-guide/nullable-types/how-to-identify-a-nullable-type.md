---
title: 'Procedura: Identificare un tipo nullable - Guida per programmatori C#'
ms.custom: seodec18
description: Informazioni su come determinare se un tipo è un tipo nullable o se un'istanza è di un tipo nullable
ms.date: 09/24/2018
helpviewer_keywords:
- nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: 73017b8f4c4c046b428d5270a2ef0241c565b07d
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/21/2019
ms.locfileid: "67307039"
---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a><span data-ttu-id="7280a-103">Procedura: Identificare un tipo nullable (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="7280a-103">How to: Identify a nullable type (C# Programming Guide)</span></span>

<span data-ttu-id="7280a-104">Nell'esempio seguente viene illustrato come determinare se un'istanza <xref:System.Type?displayProperty=nameWithType> rappresenta un tipo nullable generico chiuso, ovvero il tipo <xref:System.Nullable%601?displayProperty=nameWithType> con un parametro di tipo specificato `T`:</span><span class="sxs-lookup"><span data-stu-id="7280a-104">The following example shows how to determine whether a <xref:System.Type?displayProperty=nameWithType> instance represents a closed generic nullable type, that is, the <xref:System.Nullable%601?displayProperty=nameWithType> type with a specified type parameter `T`:</span></span>

[!code-csharp-interactive[whether Type is nullable](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#1)]

<span data-ttu-id="7280a-105">Come illustrato nell'esempio, è possibile usare l'operatore [typeof](../../language-reference/operators/type-testing-and-conversion-operators.md#typeof-operator) per creare un oggetto <xref:System.Type?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7280a-105">As the example shows, you use the [typeof](../../language-reference/operators/type-testing-and-conversion-operators.md#typeof-operator) operator to create a <xref:System.Type?displayProperty=nameWithType> object.</span></span>  
  
<span data-ttu-id="7280a-106">Se si vuole determinare se un'istanza è di un tipo nullable, non usare il metodo <xref:System.Object.GetType%2A?displayProperty=nameWithType> per ottenere un'istanza <xref:System.Type> da testare con il codice precedente.</span><span class="sxs-lookup"><span data-stu-id="7280a-106">If you want to determine whether an instance is of a nullable type, don't use the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method to get a <xref:System.Type> instance to be tested with the preceding code.</span></span> <span data-ttu-id="7280a-107">Quando si chiama il metodo <xref:System.Object.GetType%2A?displayProperty=nameWithType> in un'istanza di un tipo nullable, viene eseguita la [conversione boxing](using-nullable-types.md#boxing-and-unboxing) dell'istanza a <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="7280a-107">When you call the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method on an instance of a nullable type, the instance is [boxed](using-nullable-types.md#boxing-and-unboxing) to <xref:System.Object>.</span></span> <span data-ttu-id="7280a-108">Poiché la conversione boxing di un'istanza non Null di un tipo nullable è equivalente alla conversione boxing di un valore del tipo sottostante, <xref:System.Object.GetType%2A> restituisce un oggetto <xref:System.Type> che rappresenta il tipo sottostante di un tipo nullable:</span><span class="sxs-lookup"><span data-stu-id="7280a-108">As boxing of a non-null instance of a nullable type is equivalent to boxing of a value of the underlying type, <xref:System.Object.GetType%2A> returns a <xref:System.Type> object that represents the underlying type of a nullable type:</span></span>

[!code-csharp-interactive[GetType example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#2)]

<span data-ttu-id="7280a-109">Non usare l'operatore [is](../../language-reference/keywords/is.md) per determinare se un'istanza è di un tipo nullable.</span><span class="sxs-lookup"><span data-stu-id="7280a-109">Don't use the [is](../../language-reference/keywords/is.md) operator to determine whether an instance is of a nullable type.</span></span> <span data-ttu-id="7280a-110">Come illustrato nell'esempio seguente, non è possibile distinguere i tipi di istanze di un tipo nullable e del relativo tipo sottostante con l'operatore `is`:</span><span class="sxs-lookup"><span data-stu-id="7280a-110">As the following example shows, you cannot distinguish types of instances of a nullable type and its underlying type with using the `is` operator:</span></span>

[!code-csharp-interactive[is operator example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#3)]

<span data-ttu-id="7280a-111">È possibile usare il codice riportato nell'esempio seguente per determinare se un'istanza è di un tipo nullable:</span><span class="sxs-lookup"><span data-stu-id="7280a-111">You can use the code presented in the following example to determine whether an instance is of a nullable type:</span></span>

[!code-csharp-interactive[whether an instance is of a nullable type](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#4)]
  
## <a name="see-also"></a><span data-ttu-id="7280a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7280a-112">See also</span></span>

- [<span data-ttu-id="7280a-113">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="7280a-113">Nullable types</span></span>](index.md)
- [<span data-ttu-id="7280a-114">Uso dei tipi nullable</span><span class="sxs-lookup"><span data-stu-id="7280a-114">Using nullable types</span></span>](using-nullable-types.md)
- <xref:System.Nullable.GetUnderlyingType%2A>
