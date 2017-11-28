---
title: Utilizzo di foreach con matrici (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 797cb9a63a5e1009b170b2afda8634bd21a50035
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="cb980-102">Utilizzo di foreach con matrici (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="cb980-102">Using foreach with Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="cb980-103">In C# è disponibile anche l'istruzione [foreach](../../../csharp/language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="cb980-103">C# also provides the [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement.</span></span> <span data-ttu-id="cb980-104">Questa istruzione offre un metodo semplice e diretto per scorrere gli elementi di una matrice o qualsiasi raccolta enumerabile.</span><span class="sxs-lookup"><span data-stu-id="cb980-104">This statement provides a simple, clean way to iterate through the elements of an array or any enumerable collection.</span></span> <span data-ttu-id="cb980-105">L'istruzione `foreach` elabora gli elementi nell'ordine restituito dalla matrice o dall'enumeratore del tipo di raccolta, in genere dall'elemento zero all'ultimo.</span><span class="sxs-lookup"><span data-stu-id="cb980-105">The `foreach` statement processes elements in the order returned by the array or collection type’s enumerator, which is usually from the 0th element to the last.</span></span> <span data-ttu-id="cb980-106">Il codice che segue, ad esempio, consente la creazione di una matrice denominata `numbers` e di scorrere tale matrice con l'istruzione `foreach`:</span><span class="sxs-lookup"><span data-stu-id="cb980-106">For example, the following code creates an array called `numbers` and iterates through it with the `foreach` statement:</span></span>  
  
 [!code-csharp[csProgGuideArrays#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_1.cs)]  
  
 <span data-ttu-id="cb980-107">Con le matrici multidimensionali è possibile utilizzare lo stesso metodo per scorrere gli elementi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cb980-107">With multidimensional arrays, you can use the same method to iterate through the elements, for example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#29](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_2.cs)]  
  
 <span data-ttu-id="cb980-108">Con le matrici multidimensionali, tuttavia, l'uso di un ciclo [for](../../../csharp/language-reference/keywords/for.md) annidato fornisce maggiore controllo sugli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="cb980-108">However, with multidimensional arrays, using a nested [for](../../../csharp/language-reference/keywords/for.md) loop gives you more control over the array elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb980-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb980-109">See Also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="cb980-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="cb980-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="cb980-111">Array</span><span class="sxs-lookup"><span data-stu-id="cb980-111">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="cb980-112">Matrici unidimensionali</span><span class="sxs-lookup"><span data-stu-id="cb980-112">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="cb980-113">Matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="cb980-113">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="cb980-114">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="cb980-114">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
