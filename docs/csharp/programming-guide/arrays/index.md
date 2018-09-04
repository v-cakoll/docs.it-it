---
title: Matrici (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: 1469336bf034fd22c9d7355b2f8dd8be32721fdf
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510638"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="bd9ad-102">Matrici (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="bd9ad-102">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="bd9ad-103">È possibile archiviare più variabili dello stesso tipo in una struttura di dati a matrice.</span><span class="sxs-lookup"><span data-stu-id="bd9ad-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="bd9ad-104">Una matrice viene dichiarata specificando il tipo degli elementi.</span><span class="sxs-lookup"><span data-stu-id="bd9ad-104">You declare an array by specifying the type of its elements.</span></span>  
  
 `type[] arrayName;`  
  
 <span data-ttu-id="bd9ad-105">L'esempio seguente consente di creare matrici unidimensionali, multidimensionali e irregolari:</span><span class="sxs-lookup"><span data-stu-id="bd9ad-105">The following examples create single-dimensional, multidimensional, and jagged arrays:</span></span>  
  
 [!code-csharp[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]  
  
## <a name="array-overview"></a><span data-ttu-id="bd9ad-106">Panoramica delle matrici</span><span class="sxs-lookup"><span data-stu-id="bd9ad-106">Array Overview</span></span>

 <span data-ttu-id="bd9ad-107">Le matrici hanno le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd9ad-107">An array has the following properties:</span></span>  
  
-   <span data-ttu-id="bd9ad-108">Una matrice può essere [unidimensionale](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [multidimensionale](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) o [irregolare](../../../csharp/programming-guide/arrays/jagged-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="bd9ad-108">An array can be [Single-Dimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [Multidimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) or [Jagged](../../../csharp/programming-guide/arrays/jagged-arrays.md).</span></span>  
  
-   <span data-ttu-id="bd9ad-109">Il numero di dimensioni e la lunghezza di ogni dimensione sono definiti durante la creazione dell'istanza della matrice.</span><span class="sxs-lookup"><span data-stu-id="bd9ad-109">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="bd9ad-110">Questi valori non possono essere modificati per la durata dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="bd9ad-110">These values can't be changed during the lifetime of the instance.</span></span>  
  
-   <span data-ttu-id="bd9ad-111">I valori predefiniti degli elementi numerici della matrice sono impostati su zero, mentre gli elementi di riferimento sono impostati su null.</span><span class="sxs-lookup"><span data-stu-id="bd9ad-111">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>  
  
-   <span data-ttu-id="bd9ad-112">Una matrice irregolare è una matrice di matrici, quindi i relativi elementi sono tipi di riferimento inizializzati su `null`.</span><span class="sxs-lookup"><span data-stu-id="bd9ad-112">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
-   <span data-ttu-id="bd9ad-113">Le matrici sono a indice zero. Una matrice con `n` elementi viene indicizzata da `0` a `n-1`.</span><span class="sxs-lookup"><span data-stu-id="bd9ad-113">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>  
  
-   <span data-ttu-id="bd9ad-114">Gli elementi di una matrice possono essere di qualsiasi tipo, anche di tipo matrice.</span><span class="sxs-lookup"><span data-stu-id="bd9ad-114">Array elements can be of any type, including an array type.</span></span>  
  
-   <span data-ttu-id="bd9ad-115">I tipi matrice sono [tipi di riferimento](../../../csharp/language-reference/keywords/reference-types.md) derivati dal tipo di base astratto <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="bd9ad-115">Array types are [reference types](../../../csharp/language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="bd9ad-116">Poiché questo tipo implementa <xref:System.Collections.IEnumerable> e <xref:System.Collections.Generic.IEnumerable%601>, è possibile usare l'iterazione [foreach](../../../csharp/language-reference/keywords/foreach-in.md) su tutte le matrici in C#.</span><span class="sxs-lookup"><span data-stu-id="bd9ad-116">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../../csharp/language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bd9ad-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="bd9ad-117">Related Sections</span></span>  
  
-   [<span data-ttu-id="bd9ad-118">Matrici come oggetti</span><span class="sxs-lookup"><span data-stu-id="bd9ad-118">Arrays as Objects</span></span>](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
-   [<span data-ttu-id="bd9ad-119">Uso di foreach con matrici</span><span class="sxs-lookup"><span data-stu-id="bd9ad-119">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
-   [<span data-ttu-id="bd9ad-120">Passaggio di matrici come argomenti</span><span class="sxs-lookup"><span data-stu-id="bd9ad-120">Passing Arrays as Arguments</span></span>](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
-   [<span data-ttu-id="bd9ad-121">Passaggio di matrici usando ref e out</span><span class="sxs-lookup"><span data-stu-id="bd9ad-121">Passing Arrays Using ref and out</span></span>](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)   
  
## <a name="c-language-specification"></a><span data-ttu-id="bd9ad-122">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="bd9ad-122">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bd9ad-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd9ad-123">See Also</span></span>

- [<span data-ttu-id="bd9ad-124">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="bd9ad-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="bd9ad-125">Raccolte</span><span class="sxs-lookup"><span data-stu-id="bd9ad-125">Collections</span></span>](https://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)  
- [<span data-ttu-id="bd9ad-126">Tipo di raccolta Array</span><span class="sxs-lookup"><span data-stu-id="bd9ad-126">Array Collection Type</span></span>](https://msdn.microsoft.com/library/8a9964de-8941-47b1-a3cf-a01bc88db9e8)
