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
# <a name="how-to-identify-a-nullable-value-type-c-programming-guide"></a><span data-ttu-id="c44cc-103">Procedura: identificare un tipo di valore Nullable (C# guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="c44cc-103">How to: identify a nullable value type (C# Programming Guide)</span></span>

<span data-ttu-id="c44cc-104">Nell'esempio seguente viene illustrato come determinare se un'istanza di <xref:System.Type?displayProperty=nameWithType> rappresenta un tipo di valore Nullable generico chiuso, ovvero il tipo <xref:System.Nullable%601?displayProperty=nameWithType> con un parametro di tipo specificato `T`:</span><span class="sxs-lookup"><span data-stu-id="c44cc-104">The following example shows how to determine whether a <xref:System.Type?displayProperty=nameWithType> instance represents a closed generic nullable value type, that is, the <xref:System.Nullable%601?displayProperty=nameWithType> type with a specified type parameter `T`:</span></span>

[!code-csharp-interactive[whether Type is nullable](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#1)]

<span data-ttu-id="c44cc-105">Come illustrato nell'esempio, è possibile usare l'operatore [typeof](../../language-reference/operators/type-testing-and-cast.md#typeof-operator) per creare un oggetto <xref:System.Type?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c44cc-105">As the example shows, you use the [typeof](../../language-reference/operators/type-testing-and-cast.md#typeof-operator) operator to create a <xref:System.Type?displayProperty=nameWithType> object.</span></span>

<span data-ttu-id="c44cc-106">Se si desidera determinare se un'istanza è di un tipo di valore Nullable, non utilizzare il metodo <xref:System.Object.GetType%2A?displayProperty=nameWithType> per ottenere un'istanza di <xref:System.Type> da testare con il codice precedente.</span><span class="sxs-lookup"><span data-stu-id="c44cc-106">If you want to determine whether an instance is of a nullable value type, don't use the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method to get a <xref:System.Type> instance to be tested with the preceding code.</span></span> <span data-ttu-id="c44cc-107">Quando si chiama il metodo <xref:System.Object.GetType%2A?displayProperty=nameWithType> su un'istanza di un tipo di valore Nullable, l'istanza viene sottoposta a [boxing](using-nullable-types.md#boxing-and-unboxing) <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="c44cc-107">When you call the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method on an instance of a nullable value type, the instance is [boxed](using-nullable-types.md#boxing-and-unboxing) to <xref:System.Object>.</span></span> <span data-ttu-id="c44cc-108">Poiché la conversione boxing di un'istanza non null di un tipo di valore Nullable equivale alla conversione boxing di un valore del tipo sottostante, <xref:System.Object.GetType%2A> restituisce un oggetto <xref:System.Type> che rappresenta il tipo sottostante di un tipo di valore Nullable:</span><span class="sxs-lookup"><span data-stu-id="c44cc-108">As boxing of a non-null instance of a nullable value type is equivalent to boxing of a value of the underlying type, <xref:System.Object.GetType%2A> returns a <xref:System.Type> object that represents the underlying type of a nullable value type:</span></span>

[!code-csharp-interactive[GetType example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#2)]

<span data-ttu-id="c44cc-109">Non usare l'operatore [is](../../language-reference/keywords/is.md) per determinare se un'istanza è un tipo di valore Nullable.</span><span class="sxs-lookup"><span data-stu-id="c44cc-109">Don't use the [is](../../language-reference/keywords/is.md) operator to determine whether an instance is of a nullable value type.</span></span> <span data-ttu-id="c44cc-110">Come illustrato nell'esempio seguente, non è possibile distinguere i tipi di istanze di un tipo di valore nullable e il tipo sottostante usando l'operatore `is`:</span><span class="sxs-lookup"><span data-stu-id="c44cc-110">As the following example shows, you cannot distinguish types of instances of a nullable value type and its underlying type with using the `is` operator:</span></span>

[!code-csharp-interactive[is operator example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#3)]

<span data-ttu-id="c44cc-111">È possibile utilizzare il codice presentato nell'esempio seguente per determinare se un'istanza è un tipo di valore Nullable:</span><span class="sxs-lookup"><span data-stu-id="c44cc-111">You can use the code presented in the following example to determine whether an instance is of a nullable value type:</span></span>

[!code-csharp-interactive[whether an instance is of a nullable type](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#4)]

## <a name="see-also"></a><span data-ttu-id="c44cc-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c44cc-112">See also</span></span>

- [<span data-ttu-id="c44cc-113">Tipi valore nullable</span><span class="sxs-lookup"><span data-stu-id="c44cc-113">Nullable value types</span></span>](index.md)
- [<span data-ttu-id="c44cc-114">Utilizzo di tipi di valore Nullable</span><span class="sxs-lookup"><span data-stu-id="c44cc-114">Using nullable value types</span></span>](using-nullable-types.md)
- <xref:System.Nullable.GetUnderlyingType%2A>
