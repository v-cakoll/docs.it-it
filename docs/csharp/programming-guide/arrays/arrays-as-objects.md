---
title: Matrici come oggetti - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: d8b929eccf9be259874d03dd93f49a49798bb349
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715097"
---
# <a name="arrays-as-objects-c-programming-guide"></a><span data-ttu-id="9df54-102">Matrici come oggetti (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="9df54-102">Arrays as Objects (C# Programming Guide)</span></span>

<span data-ttu-id="9df54-103">In C# le matrici sono in effetti oggetti e non semplicemente aree indirizzabili di memoria contigua come in C e C++.</span><span class="sxs-lookup"><span data-stu-id="9df54-103">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="9df54-104"><xref:System.Array> è il tipo di base astratto di tutti i tipi di matrice.</span><span class="sxs-lookup"><span data-stu-id="9df54-104"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="9df54-105">È possibile utilizzare le proprietà <xref:System.Array> e altri membri di classe che dispone di.</span><span class="sxs-lookup"><span data-stu-id="9df54-105">You can use the properties and other class members that <xref:System.Array> has.</span></span> <span data-ttu-id="9df54-106">Un esempio di questo <xref:System.Array.Length%2A> è l'utilizzo della proprietà per ottenere la lunghezza di una matrice.</span><span class="sxs-lookup"><span data-stu-id="9df54-106">An example of this is using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="9df54-107">Il codice seguente assegna la lunghezza della matrice `numbers`, ovvero `5`, a una variabile denominata `lengthOfNumbers`:</span><span class="sxs-lookup"><span data-stu-id="9df54-107">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>

[!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]

<span data-ttu-id="9df54-108">La classe <xref:System.Array> offre numerosi altri utili metodi e proprietà per l'ordinamento, la ricerca e la copia di matrici.</span><span class="sxs-lookup"><span data-stu-id="9df54-108">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span>

## <a name="example"></a><span data-ttu-id="9df54-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="9df54-109">Example</span></span>

<span data-ttu-id="9df54-110">Questo esempio usa la proprietà <xref:System.Array.Rank%2A> per visualizzare il numero di dimensioni di una matrice.</span><span class="sxs-lookup"><span data-stu-id="9df54-110">This example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>

[!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]

## <a name="see-also"></a><span data-ttu-id="9df54-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9df54-111">See also</span></span>

- [<span data-ttu-id="9df54-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="9df54-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9df54-113">Matrici</span><span class="sxs-lookup"><span data-stu-id="9df54-113">Arrays</span></span>](./index.md)
- [<span data-ttu-id="9df54-114">Matrici unidimensionali</span><span class="sxs-lookup"><span data-stu-id="9df54-114">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="9df54-115">Matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="9df54-115">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="9df54-116">Matrici frastagliate</span><span class="sxs-lookup"><span data-stu-id="9df54-116">Jagged Arrays</span></span>](./jagged-arrays.md)
