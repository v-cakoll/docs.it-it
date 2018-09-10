---
title: Utilizzo di foreach con matrici (Guida per programmatori C#)
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: 298ee915bbe11313f3b33ea7dae9353ef956a231
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509535"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="661c1-102">Utilizzo di foreach con matrici (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="661c1-102">Using foreach with Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="661c1-103">L'istruzione [foreach](../../language-reference/keywords/foreach-in.md) offre un metodo semplice e diretto per scorrere gli elementi di una matrice.</span><span class="sxs-lookup"><span data-stu-id="661c1-103">The [foreach](../../language-reference/keywords/foreach-in.md) statement provides a simple, clean way to iterate through the elements of an array.</span></span>

<span data-ttu-id="661c1-104">Per le matrici unidimensionali, l'istruzione `foreach` elabora gli elementi in ordine di indice crescente, a partire dall'indice 0 e terminando con l'indice `Length - 1`:</span><span class="sxs-lookup"><span data-stu-id="661c1-104">For single-dimensional arrays, the `foreach` statement processes elements in increasing index order, starting with index 0 and ending with index `Length - 1`:</span></span>

[!code-csharp[csProgGuideArrays#28](./codesnippet/CSharp/using-foreach-with-arrays_1.cs)]

<span data-ttu-id="661c1-105">Per le matrici multidimensionali, l'attraversamento degli elementi avviene in modo da incrementare per primi gli indici della dimensione all'estrema destra, per poi proseguire con la dimensione successiva a sinistra e così via verso sinistra:</span><span class="sxs-lookup"><span data-stu-id="661c1-105">For multi-dimensional arrays, elements are traversed such that the indices of the rightmost dimension are increased first, then the next left dimension, and so on to the left:</span></span>

[!code-csharp[csProgGuideArrays#29](./codesnippet/CSharp/using-foreach-with-arrays_2.cs)]

<span data-ttu-id="661c1-106">Con le matrici multidimensionali, tuttavia, l'uso di un ciclo [for](../../language-reference/keywords/for.md) annidato fornisce maggiore controllo sull'ordine di elaborazione degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="661c1-106">However, with multidimensional arrays, using a nested [for](../../language-reference/keywords/for.md) loop gives you more control over the order in which to process the array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="661c1-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="661c1-107">See Also</span></span>

- <xref:System.Array>  
- [<span data-ttu-id="661c1-108">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="661c1-108">C# Programming Guide</span></span>](../index.md)  
- [<span data-ttu-id="661c1-109">Array</span><span class="sxs-lookup"><span data-stu-id="661c1-109">Arrays</span></span>](index.md)  
- [<span data-ttu-id="661c1-110">Matrici unidimensionali</span><span class="sxs-lookup"><span data-stu-id="661c1-110">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)  
- [<span data-ttu-id="661c1-111">Matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="661c1-111">Multidimensional Arrays</span></span>](multidimensional-arrays.md)  
- [<span data-ttu-id="661c1-112">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="661c1-112">Jagged Arrays</span></span>](jagged-arrays.md)
