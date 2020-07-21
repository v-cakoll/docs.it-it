---
title: Uso di foreach con matrici - Guida per programmatori C#
description: L'istruzione foreach in C# scorre gli elementi di una matrice. Per le matrici unidimensionali, foreach elabora gli elementi in ordine di indice crescente.
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: d924a3ef3351cbb30b809a1542f35314ee721852
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474540"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="2838a-104">Utilizzo di foreach con matrici (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="2838a-104">Using foreach with arrays (C# Programming Guide)</span></span>

<span data-ttu-id="2838a-105">L'istruzione [foreach](../../language-reference/keywords/foreach-in.md) offre un metodo semplice e diretto per scorrere gli elementi di una matrice.</span><span class="sxs-lookup"><span data-stu-id="2838a-105">The [foreach](../../language-reference/keywords/foreach-in.md) statement provides a simple, clean way to iterate through the elements of an array.</span></span>

<span data-ttu-id="2838a-106">Per le matrici unidimensionali, l'istruzione `foreach` elabora gli elementi in ordine di indice crescente, a partire dall'indice 0 e terminando con l'indice `Length - 1`:</span><span class="sxs-lookup"><span data-stu-id="2838a-106">For single-dimensional arrays, the `foreach` statement processes elements in increasing index order, starting with index 0 and ending with index `Length - 1`:</span></span>

 [!code-csharp[csProgGuideArrays#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#28)]

<span data-ttu-id="2838a-107">Per le matrici multidimensionali, l'attraversamento degli elementi avviene in modo da incrementare per primi gli indici della dimensione all'estrema destra, per poi proseguire con la dimensione successiva a sinistra e così via verso sinistra:</span><span class="sxs-lookup"><span data-stu-id="2838a-107">For multi-dimensional arrays, elements are traversed such that the indices of the rightmost dimension are increased first, then the next left dimension, and so on to the left:</span></span>

 [!code-csharp[csProgGuideArrays#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#29)]

<span data-ttu-id="2838a-108">Con le matrici multidimensionali, tuttavia, l'uso di un ciclo [for](../../language-reference/keywords/for.md) annidato fornisce maggiore controllo sull'ordine di elaborazione degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="2838a-108">However, with multidimensional arrays, using a nested [for](../../language-reference/keywords/for.md) loop gives you more control over the order in which to process the array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="2838a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2838a-109">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="2838a-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="2838a-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2838a-111">Matrici</span><span class="sxs-lookup"><span data-stu-id="2838a-111">Arrays</span></span>](index.md)
- [<span data-ttu-id="2838a-112">Matrici unidimensionali</span><span class="sxs-lookup"><span data-stu-id="2838a-112">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="2838a-113">Matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="2838a-113">Multidimensional Arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="2838a-114">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="2838a-114">Jagged Arrays</span></span>](jagged-arrays.md)
