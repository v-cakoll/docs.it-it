---
title: Matrici come oggetti - Guida per programmatori C#
description: Le matrici in C# sono oggetti della matrice astratta del tipo di base. È possibile usare le proprietà e altri membri della classe Array, ad esempio la proprietà Length.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: 984def3ef74b07d7099fae6cae6d6f8ce7e03e12
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474722"
---
# <a name="arrays-as-objects-c-programming-guide"></a><span data-ttu-id="38709-104">Matrici come oggetti (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="38709-104">Arrays as Objects (C# Programming Guide)</span></span>

<span data-ttu-id="38709-105">In C# le matrici sono in effetti oggetti e non semplicemente aree indirizzabili di memoria contigua come in C e C++.</span><span class="sxs-lookup"><span data-stu-id="38709-105">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="38709-106"><xref:System.Array> è il tipo di base astratto di tutti i tipi di matrice.</span><span class="sxs-lookup"><span data-stu-id="38709-106"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="38709-107">È possibile usare le proprietà e altri membri della classe <xref:System.Array> con.</span><span class="sxs-lookup"><span data-stu-id="38709-107">You can use the properties and other class members that <xref:System.Array> has.</span></span> <span data-ttu-id="38709-108">Un esempio è l'uso della <xref:System.Array.Length%2A> proprietà per ottenere la lunghezza di una matrice.</span><span class="sxs-lookup"><span data-stu-id="38709-108">An example of this is using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="38709-109">Il codice seguente assegna la lunghezza della matrice `numbers`, ovvero `5`, a una variabile denominata `lengthOfNumbers`:</span><span class="sxs-lookup"><span data-stu-id="38709-109">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>

[!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]

<span data-ttu-id="38709-110">La classe <xref:System.Array> offre numerosi altri utili metodi e proprietà per l'ordinamento, la ricerca e la copia di matrici.</span><span class="sxs-lookup"><span data-stu-id="38709-110">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span>

## <a name="example"></a><span data-ttu-id="38709-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="38709-111">Example</span></span>

<span data-ttu-id="38709-112">Questo esempio usa la proprietà <xref:System.Array.Rank%2A> per visualizzare il numero di dimensioni di una matrice.</span><span class="sxs-lookup"><span data-stu-id="38709-112">This example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>

[!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]

## <a name="see-also"></a><span data-ttu-id="38709-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38709-113">See also</span></span>

- [<span data-ttu-id="38709-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="38709-114">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="38709-115">Matrici</span><span class="sxs-lookup"><span data-stu-id="38709-115">Arrays</span></span>](./index.md)
- [<span data-ttu-id="38709-116">Matrici unidimensionali</span><span class="sxs-lookup"><span data-stu-id="38709-116">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="38709-117">Matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="38709-117">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="38709-118">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="38709-118">Jagged Arrays</span></span>](./jagged-arrays.md)
