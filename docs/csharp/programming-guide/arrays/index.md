---
title: Matrici - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: bbabc84c144e5b3415c19f346b890782e251662c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75715061"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="aee31-102">Matrici (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="aee31-102">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="aee31-103">È possibile archiviare più variabili dello stesso tipo in una struttura di dati a matrice.</span><span class="sxs-lookup"><span data-stu-id="aee31-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="aee31-104">Una matrice viene dichiarata specificando il tipo degli elementi.</span><span class="sxs-lookup"><span data-stu-id="aee31-104">You declare an array by specifying the type of its elements.</span></span> <span data-ttu-id="aee31-105">Se si desidera che la matrice memorizzi `object` elementi di qualsiasi tipo, è possibile specificare come tipo.</span><span class="sxs-lookup"><span data-stu-id="aee31-105">If you want the array to store elements of any type, you can specify `object` as its type.</span></span> <span data-ttu-id="aee31-106">Nel sistema di tipi unificato di C#, tutti i tipi, predefiniti e definiti dall'utente, i tipi riferimento e i tipi valore ereditano direttamente o indirettamente da <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="aee31-106">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span>

```csharp
type[] arrayName;
```

## <a name="example"></a><span data-ttu-id="aee31-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="aee31-107">Example</span></span>

<span data-ttu-id="aee31-108">L'esempio seguente consente di creare matrici unidimensionali, multidimensionali e irregolari:</span><span class="sxs-lookup"><span data-stu-id="aee31-108">The following example creates single-dimensional, multidimensional, and jagged arrays:</span></span>

[!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]

## <a name="array-overview"></a><span data-ttu-id="aee31-109">Panoramica dell'array</span><span class="sxs-lookup"><span data-stu-id="aee31-109">Array overview</span></span>

<span data-ttu-id="aee31-110">Le matrici hanno le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="aee31-110">An array has the following properties:</span></span>

- <span data-ttu-id="aee31-111">Una matrice può essere [unidimensionale](single-dimensional-arrays.md), [multidimensionale](multidimensional-arrays.md) o [irregolare](jagged-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="aee31-111">An array can be [Single-Dimensional](single-dimensional-arrays.md), [Multidimensional](multidimensional-arrays.md) or [Jagged](jagged-arrays.md).</span></span>
- <span data-ttu-id="aee31-112">Il numero di dimensioni e la lunghezza di ogni dimensione sono definiti durante la creazione dell'istanza della matrice.</span><span class="sxs-lookup"><span data-stu-id="aee31-112">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="aee31-113">Questi valori non possono essere modificati per la durata dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="aee31-113">These values can't be changed during the lifetime of the instance.</span></span>
- <span data-ttu-id="aee31-114">I valori predefiniti degli elementi numerici della matrice sono impostati su zero, mentre gli elementi di riferimento sono impostati su null.</span><span class="sxs-lookup"><span data-stu-id="aee31-114">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>
- <span data-ttu-id="aee31-115">Una matrice irregolare è una matrice di matrici, quindi i relativi elementi sono tipi di riferimento inizializzati su `null`.</span><span class="sxs-lookup"><span data-stu-id="aee31-115">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>
- <span data-ttu-id="aee31-116">Le matrici sono a indice zero. Una matrice con `n` elementi viene indicizzata da `0` a `n-1`.</span><span class="sxs-lookup"><span data-stu-id="aee31-116">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>
- <span data-ttu-id="aee31-117">Gli elementi di una matrice possono essere di qualsiasi tipo, anche di tipo matrice.</span><span class="sxs-lookup"><span data-stu-id="aee31-117">Array elements can be of any type, including an array type.</span></span>
- <span data-ttu-id="aee31-118">I tipi matrice sono [tipi di riferimento](../../language-reference/keywords/reference-types.md) derivati dal tipo di base astratto <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="aee31-118">Array types are [reference types](../../language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="aee31-119">Poiché questo tipo implementa <xref:System.Collections.IEnumerable> e <xref:System.Collections.Generic.IEnumerable%601>, è possibile usare l'iterazione [foreach](../../language-reference/keywords/foreach-in.md) su tutte le matrici in C#.</span><span class="sxs-lookup"><span data-stu-id="aee31-119">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>

## <a name="related-sections"></a><span data-ttu-id="aee31-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="aee31-120">Related sections</span></span>

- [<span data-ttu-id="aee31-121">Matrici come oggetti</span><span class="sxs-lookup"><span data-stu-id="aee31-121">Arrays as Objects</span></span>](arrays-as-objects.md)
- [<span data-ttu-id="aee31-122">Uso di foreach con matrici</span><span class="sxs-lookup"><span data-stu-id="aee31-122">Using foreach with Arrays</span></span>](using-foreach-with-arrays.md)
- [<span data-ttu-id="aee31-123">Passaggio di matrici come argomenti</span><span class="sxs-lookup"><span data-stu-id="aee31-123">Passing Arrays as Arguments</span></span>](passing-arrays-as-arguments.md)

## <a name="c-language-specification"></a><span data-ttu-id="aee31-124">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="aee31-124">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="aee31-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aee31-125">See also</span></span>

- [<span data-ttu-id="aee31-126">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="aee31-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="aee31-127">Raccolte</span><span class="sxs-lookup"><span data-stu-id="aee31-127">Collections</span></span>](../concepts/collections.md)
