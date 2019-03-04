---
title: Matrici come oggetti - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: 8500cf508b77a0fa7e348ce0fe6b1f16fd2bab25
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977171"
---
# <a name="arrays-as-objects-c-programming-guide"></a><span data-ttu-id="e9578-102">Matrici come oggetti (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e9578-102">Arrays as Objects (C# Programming Guide)</span></span>

<span data-ttu-id="e9578-103">In C# le matrici sono in effetti oggetti e non semplicemente aree indirizzabili di memoria contigua come in C e C++.</span><span class="sxs-lookup"><span data-stu-id="e9578-103">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="e9578-104"><xref:System.Array> è il tipo di base astratto di tutti i tipi di matrice.</span><span class="sxs-lookup"><span data-stu-id="e9578-104"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="e9578-105">È possibile usare le proprietà e gli altri membri di classe disponibili per <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="e9578-105">You can use the properties, and other class members, that <xref:System.Array> has.</span></span> <span data-ttu-id="e9578-106">Un esempio è l'uso della proprietà <xref:System.Array.Length%2A> per ottenere la lunghezza della matrice.</span><span class="sxs-lookup"><span data-stu-id="e9578-106">An example of this would be using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="e9578-107">Il codice seguente assegna la lunghezza della matrice `numbers`, ovvero `5`, a una variabile denominata `lengthOfNumbers`:</span><span class="sxs-lookup"><span data-stu-id="e9578-107">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>  
  
 [!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]  
  
 <span data-ttu-id="e9578-108">La classe <xref:System.Array> offre numerosi altri utili metodi e proprietà per l'ordinamento, la ricerca e la copia di matrici.</span><span class="sxs-lookup"><span data-stu-id="e9578-108">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9578-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="e9578-109">Example</span></span>

 <span data-ttu-id="e9578-110">Questo esempio usa la proprietà <xref:System.Array.Rank%2A> per visualizzare il numero di dimensioni di una matrice.</span><span class="sxs-lookup"><span data-stu-id="e9578-110">This example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>  
  
 [!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e9578-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9578-111">See also</span></span>

- [<span data-ttu-id="e9578-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e9578-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e9578-113">Matrici</span><span class="sxs-lookup"><span data-stu-id="e9578-113">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)
- [<span data-ttu-id="e9578-114">Matrici unidimensionali</span><span class="sxs-lookup"><span data-stu-id="e9578-114">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)
- [<span data-ttu-id="e9578-115">Matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="e9578-115">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)
- [<span data-ttu-id="e9578-116">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="e9578-116">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
