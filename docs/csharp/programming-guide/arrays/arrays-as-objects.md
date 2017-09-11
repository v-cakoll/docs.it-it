---
title: Matrici come oggetti (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 396d0df9196b7331e94127730b83782ffc8ea593
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="arrays-as-objects-c-programming-guide"></a><span data-ttu-id="1e91d-102">Matrici come oggetti (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="1e91d-102">Arrays as Objects (C# Programming Guide)</span></span>
<span data-ttu-id="1e91d-103">In C# le matrici sono in effetti oggetti e non semplicemente aree indirizzabili di memoria contigua come in C e C++.</span><span class="sxs-lookup"><span data-stu-id="1e91d-103">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="1e91d-104"><xref:System.Array> è il tipo di base astratto di tutti i tipi di matrice.</span><span class="sxs-lookup"><span data-stu-id="1e91d-104"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="1e91d-105">È possibile usare le proprietà e gli altri membri di classe disponibili per <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="1e91d-105">You can use the properties, and other class members, that <xref:System.Array> has.</span></span> <span data-ttu-id="1e91d-106">Un esempio è l'uso della proprietà <xref:System.Array.Length%2A> per ottenere la lunghezza della matrice.</span><span class="sxs-lookup"><span data-stu-id="1e91d-106">An example of this would be using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="1e91d-107">Il codice seguente assegna la lunghezza della matrice `numbers`, ovvero `5`, a una variabile denominata `lengthOfNumbers`:</span><span class="sxs-lookup"><span data-stu-id="1e91d-107">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>  
  
 <span data-ttu-id="1e91d-108">[!code-cs[csProgGuideArrays#3](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1e91d-108">[!code-cs[csProgGuideArrays#3](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_1.cs)]</span></span>  
  
 <span data-ttu-id="1e91d-109">La classe <xref:System.Array> offre numerosi altri utili metodi e proprietà per l'ordinamento, la ricerca e la copia di matrici.</span><span class="sxs-lookup"><span data-stu-id="1e91d-109">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e91d-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="1e91d-110">Example</span></span>  
 <span data-ttu-id="1e91d-111">Questo esempio usa la proprietà <xref:System.Array.Rank%2A> per visualizzare il numero di dimensioni di una matrice.</span><span class="sxs-lookup"><span data-stu-id="1e91d-111">This example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>  
  
 <span data-ttu-id="1e91d-112">[!code-cs[csProgGuideArrays#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="1e91d-112">[!code-cs[csProgGuideArrays#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e91d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e91d-113">See Also</span></span>  
 <span data-ttu-id="1e91d-114">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1e91d-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1e91d-115">[Matrici](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="1e91d-115">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="1e91d-116">[Matrici unidimensionali](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="1e91d-116">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 <span data-ttu-id="1e91d-117">[Matrici multidimensionali](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="1e91d-117">[Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span></span>  
 [<span data-ttu-id="1e91d-118">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="1e91d-118">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

