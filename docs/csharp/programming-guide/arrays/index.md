---
title: Matrici - Guida per programmatori C#
description: Archiviare più variabili dello stesso tipo in una struttura di dati di matrice in C#. Dichiarare una matrice specificando un tipo o specificando un oggetto per archiviare qualsiasi tipo.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: e302ff2e4c2488c4899c4eb99a666d2d322119ce
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474735"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="68a5b-104">Matrici (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="68a5b-104">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="68a5b-105">È possibile archiviare più variabili dello stesso tipo in una struttura di dati a matrice.</span><span class="sxs-lookup"><span data-stu-id="68a5b-105">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="68a5b-106">Una matrice viene dichiarata specificando il tipo degli elementi.</span><span class="sxs-lookup"><span data-stu-id="68a5b-106">You declare an array by specifying the type of its elements.</span></span> <span data-ttu-id="68a5b-107">Se si desidera che la matrice memorizzi elementi di qualsiasi tipo, è possibile specificare `object` come tipo.</span><span class="sxs-lookup"><span data-stu-id="68a5b-107">If you want the array to store elements of any type, you can specify `object` as its type.</span></span> <span data-ttu-id="68a5b-108">Nel sistema di tipi unificato di C#, tutti i tipi, predefiniti e definiti dall'utente, i tipi riferimento e i tipi valore ereditano direttamente o indirettamente da <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="68a5b-108">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span>

```csharp
type[] arrayName;
```

## <a name="example"></a><span data-ttu-id="68a5b-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="68a5b-109">Example</span></span>

<span data-ttu-id="68a5b-110">L'esempio seguente consente di creare matrici unidimensionali, multidimensionali e irregolari:</span><span class="sxs-lookup"><span data-stu-id="68a5b-110">The following example creates single-dimensional, multidimensional, and jagged arrays:</span></span>

[!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]

## <a name="array-overview"></a><span data-ttu-id="68a5b-111">Panoramica dell'array</span><span class="sxs-lookup"><span data-stu-id="68a5b-111">Array overview</span></span>

<span data-ttu-id="68a5b-112">Le matrici hanno le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="68a5b-112">An array has the following properties:</span></span>

- <span data-ttu-id="68a5b-113">Una matrice può essere [unidimensionale](single-dimensional-arrays.md), [multidimensionale](multidimensional-arrays.md) o [irregolare](jagged-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="68a5b-113">An array can be [Single-Dimensional](single-dimensional-arrays.md), [Multidimensional](multidimensional-arrays.md) or [Jagged](jagged-arrays.md).</span></span>
- <span data-ttu-id="68a5b-114">Il numero di dimensioni e la lunghezza di ogni dimensione sono definiti durante la creazione dell'istanza della matrice.</span><span class="sxs-lookup"><span data-stu-id="68a5b-114">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="68a5b-115">Questi valori non possono essere modificati per la durata dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="68a5b-115">These values can't be changed during the lifetime of the instance.</span></span>
- <span data-ttu-id="68a5b-116">I valori predefiniti degli elementi numerici della matrice sono impostati su zero, mentre gli elementi di riferimento sono impostati su null.</span><span class="sxs-lookup"><span data-stu-id="68a5b-116">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>
- <span data-ttu-id="68a5b-117">Una matrice irregolare è una matrice di matrici, quindi i relativi elementi sono tipi di riferimento inizializzati su `null`.</span><span class="sxs-lookup"><span data-stu-id="68a5b-117">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>
- <span data-ttu-id="68a5b-118">Le matrici sono a indice zero. Una matrice con `n` elementi viene indicizzata da `0` a `n-1`.</span><span class="sxs-lookup"><span data-stu-id="68a5b-118">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>
- <span data-ttu-id="68a5b-119">Gli elementi di una matrice possono essere di qualsiasi tipo, anche di tipo matrice.</span><span class="sxs-lookup"><span data-stu-id="68a5b-119">Array elements can be of any type, including an array type.</span></span>
- <span data-ttu-id="68a5b-120">I tipi matrice sono [tipi di riferimento](../../language-reference/keywords/reference-types.md) derivati dal tipo di base astratto <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="68a5b-120">Array types are [reference types](../../language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="68a5b-121">Poiché questo tipo implementa <xref:System.Collections.IEnumerable> e <xref:System.Collections.Generic.IEnumerable%601>, è possibile usare l'iterazione [foreach](../../language-reference/keywords/foreach-in.md) su tutte le matrici in C#.</span><span class="sxs-lookup"><span data-stu-id="68a5b-121">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>

## <a name="related-sections"></a><span data-ttu-id="68a5b-122">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="68a5b-122">Related sections</span></span>

- [<span data-ttu-id="68a5b-123">Matrici come oggetti</span><span class="sxs-lookup"><span data-stu-id="68a5b-123">Arrays as Objects</span></span>](arrays-as-objects.md)
- [<span data-ttu-id="68a5b-124">Uso di foreach con matrici</span><span class="sxs-lookup"><span data-stu-id="68a5b-124">Using foreach with Arrays</span></span>](using-foreach-with-arrays.md)
- [<span data-ttu-id="68a5b-125">Passaggio di matrici come argomenti</span><span class="sxs-lookup"><span data-stu-id="68a5b-125">Passing Arrays as Arguments</span></span>](passing-arrays-as-arguments.md)

## <a name="c-language-specification"></a><span data-ttu-id="68a5b-126">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="68a5b-126">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="68a5b-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68a5b-127">See also</span></span>

- [<span data-ttu-id="68a5b-128">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="68a5b-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="68a5b-129">raccolte</span><span class="sxs-lookup"><span data-stu-id="68a5b-129">Collections</span></span>](../concepts/collections.md)
