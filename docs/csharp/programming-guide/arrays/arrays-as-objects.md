---
title: Matrici come oggetti (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e29685af509009f42f38ba2dbf8524075e880ff9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="arrays-as-objects-c-programming-guide"></a><span data-ttu-id="272c8-102">Matrici come oggetti (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="272c8-102">Arrays as Objects (C# Programming Guide)</span></span>
<span data-ttu-id="272c8-103">In C# le matrici sono in effetti oggetti e non semplicemente aree indirizzabili di memoria contigua come in C e C++.</span><span class="sxs-lookup"><span data-stu-id="272c8-103">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="272c8-104"><xref:System.Array> è il tipo di base astratto di tutti i tipi di matrice.</span><span class="sxs-lookup"><span data-stu-id="272c8-104"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="272c8-105">È possibile usare le proprietà e gli altri membri di classe disponibili per <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="272c8-105">You can use the properties, and other class members, that <xref:System.Array> has.</span></span> <span data-ttu-id="272c8-106">Un esempio è l'uso della proprietà <xref:System.Array.Length%2A> per ottenere la lunghezza della matrice.</span><span class="sxs-lookup"><span data-stu-id="272c8-106">An example of this would be using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="272c8-107">Il codice seguente assegna la lunghezza della matrice `numbers`, ovvero `5`, a una variabile denominata `lengthOfNumbers`:</span><span class="sxs-lookup"><span data-stu-id="272c8-107">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>  
  
 [!code-csharp[csProgGuideArrays#3](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_1.cs)]  
  
 <span data-ttu-id="272c8-108">La classe <xref:System.Array> offre numerosi altri utili metodi e proprietà per l'ordinamento, la ricerca e la copia di matrici.</span><span class="sxs-lookup"><span data-stu-id="272c8-108">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span>  
  
## <a name="example"></a><span data-ttu-id="272c8-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="272c8-109">Example</span></span>  
 <span data-ttu-id="272c8-110">Questo esempio usa la proprietà <xref:System.Array.Rank%2A> per visualizzare il numero di dimensioni di una matrice.</span><span class="sxs-lookup"><span data-stu-id="272c8-110">This example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>  
  
 [!code-csharp[csProgGuideArrays#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="272c8-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="272c8-111">See Also</span></span>  
 [<span data-ttu-id="272c8-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="272c8-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="272c8-113">Array</span><span class="sxs-lookup"><span data-stu-id="272c8-113">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="272c8-114">Matrici unidimensionali</span><span class="sxs-lookup"><span data-stu-id="272c8-114">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="272c8-115">Matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="272c8-115">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="272c8-116">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="272c8-116">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
