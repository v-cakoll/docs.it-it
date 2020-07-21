---
title: Matrici irregolari - Guida per programmatori C#
description: Una matrice di matrici in C# è una matrice i cui elementi sono matrici di dimensioni e dimensioni diverse. Informazioni su come dichiarare, inizializzare e accedere a matrici di matrici.
ms.date: 07/20/2015
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
ms.openlocfilehash: 40da9fbda34aef4e69ebf2ae20485e883b79f871
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474683"
---
# <a name="jagged-arrays-c-programming-guide"></a><span data-ttu-id="8cfc5-104">Matrici irregolari (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="8cfc5-104">Jagged Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="8cfc5-105">Una matrice di matrici è una matrice i cui elementi sono costituiti da matrici.</span><span class="sxs-lookup"><span data-stu-id="8cfc5-105">A jagged array is an array whose elements are arrays.</span></span> <span data-ttu-id="8cfc5-106">Gli elementi di una matrice di matrici possono presentare dimensioni e misure diverse.</span><span class="sxs-lookup"><span data-stu-id="8cfc5-106">The elements of a jagged array can be of different dimensions and sizes.</span></span> <span data-ttu-id="8cfc5-107">Una matrice di matrici è chiamata talvolta "matrice irregolare".</span><span class="sxs-lookup"><span data-stu-id="8cfc5-107">A jagged array is sometimes called an "array of arrays."</span></span> <span data-ttu-id="8cfc5-108">Gli esempi seguenti mostrano come dichiarare, inizializzare e accedere a matrici di matrici.</span><span class="sxs-lookup"><span data-stu-id="8cfc5-108">The following examples show how to declare, initialize, and access jagged arrays.</span></span>  
  
 <span data-ttu-id="8cfc5-109">Di seguito è riportata la dichiarazione di una matrice unidimensionale a tre elementi, ognuno dei quali è una matrice unidimensionale di Integer:</span><span class="sxs-lookup"><span data-stu-id="8cfc5-109">The following is a declaration of a single-dimensional array that has three elements, each of which is a single-dimensional array of integers:</span></span>  
  
 [!code-csharp[csProgGuideArrays#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#19)]  
  
 <span data-ttu-id="8cfc5-110">Prima di poter usare `jaggedArray`, è necessario che siano stati inizializzati i relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="8cfc5-110">Before you can use `jaggedArray`, its elements must be initialized.</span></span> <span data-ttu-id="8cfc5-111">È possibile inizializzare gli elementi nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="8cfc5-111">You can initialize the elements like this:</span></span>  
  
 [!code-csharp[csProgGuideArrays#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#20)]  
  
 <span data-ttu-id="8cfc5-112">Ognuno degli elementi è costituito da una matrice unidimensionale di Integer.</span><span class="sxs-lookup"><span data-stu-id="8cfc5-112">Each of the elements is a single-dimensional array of integers.</span></span> <span data-ttu-id="8cfc5-113">Il primo elemento è una matrice di 5 Integer, il secondo una matrice di 4 Integer e il terzo una matrice di 2 Integer.</span><span class="sxs-lookup"><span data-stu-id="8cfc5-113">The first element is an array of 5 integers, the second is an array of 4 integers, and the third is an array of 2 integers.</span></span>  
  
 <span data-ttu-id="8cfc5-114">È possibile usare gli inizializzatori anche per immettere i valori negli elementi delle matrici. In questo caso, non occorre conoscere le dimensioni delle matrici.</span><span class="sxs-lookup"><span data-stu-id="8cfc5-114">It is also possible to use initializers to fill the array elements with values, in which case you do not need the array size.</span></span> <span data-ttu-id="8cfc5-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8cfc5-115">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#21)]  
  
 <span data-ttu-id="8cfc5-116">È inoltre possibile inizializzare la matrice al momento della dichiarazione, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="8cfc5-116">You can also initialize the array upon declaration like this:</span></span>  
  
 [!code-csharp[csProgGuideArrays#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#22)]  
  
 <span data-ttu-id="8cfc5-117">È possibile usare la forma abbreviata seguente.</span><span class="sxs-lookup"><span data-stu-id="8cfc5-117">You can use the following shorthand form.</span></span> <span data-ttu-id="8cfc5-118">Non è possibile omettere l'operatore `new` poiché non è prevista alcuna inizializzazione predefinita per gli elementi:</span><span class="sxs-lookup"><span data-stu-id="8cfc5-118">Notice that you cannot omit the `new` operator from the elements initialization because there is no default initialization for the elements:</span></span>  
  
 [!code-csharp[csProgGuideArrays#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#23)]  
  
 <span data-ttu-id="8cfc5-119">Una matrice irregolare è una matrice di matrici, quindi i relativi elementi sono tipi di riferimento inizializzati su `null`.</span><span class="sxs-lookup"><span data-stu-id="8cfc5-119">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
 <span data-ttu-id="8cfc5-120">È possibile accedere ai singoli elementi di una matrice, come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8cfc5-120">You can access individual array elements like these examples:</span></span>  
  
 [!code-csharp[csProgGuideArrays#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#24)]  
  
 <span data-ttu-id="8cfc5-121">È possibile combinare matrici di matrici e matrici multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="8cfc5-121">It is possible to mix jagged and multidimensional arrays.</span></span> <span data-ttu-id="8cfc5-122">Di seguito sono riportate la dichiarazione e l'inizializzazione di una matrice di matrici unidimensionale che contiene tre elementi matrice bidimensionali con dimensioni diverse.</span><span class="sxs-lookup"><span data-stu-id="8cfc5-122">The following is a declaration and initialization of a single-dimensional jagged array that contains three two-dimensional array elements of different sizes.</span></span> <span data-ttu-id="8cfc5-123">Per altre informazioni sulle matrici bidimensionali, vedere [Matrici multidimensionali](./multidimensional-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="8cfc5-123">For more information about two-dimensional arrays, see [Multidimensional Arrays](./multidimensional-arrays.md).</span></span>  
  
 [!code-csharp[csProgGuideArrays#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#25)]  
  
 <span data-ttu-id="8cfc5-124">È possibile accedere a singoli elementi, come illustrato in questo esempio, in cui viene visualizzato il valore dell'elemento `[1,0]` della prima matrice (valore `5`):</span><span class="sxs-lookup"><span data-stu-id="8cfc5-124">You can access individual elements as shown in this example, which displays the value of the element `[1,0]` of the first array (value `5`):</span></span>  
  
 [!code-csharp[csProgGuideArrays#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#26)]  
  
 <span data-ttu-id="8cfc5-125">Il metodo `Length` restituisce il numero di matrici contenute nella matrice di matrici.</span><span class="sxs-lookup"><span data-stu-id="8cfc5-125">The method `Length` returns the number of arrays contained in the jagged array.</span></span> <span data-ttu-id="8cfc5-126">Si supponga, ad esempio, che sia stata dichiarata la matrice precedente. In questo caso, la riga</span><span class="sxs-lookup"><span data-stu-id="8cfc5-126">For example, assuming you have declared the previous array, this line:</span></span>  
  
 [!code-csharp[csProgGuideArrays#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#27)]  
  
 <span data-ttu-id="8cfc5-127">restituisce il valore 3.</span><span class="sxs-lookup"><span data-stu-id="8cfc5-127">returns a value of 3.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cfc5-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="8cfc5-128">Example</span></span>

 <span data-ttu-id="8cfc5-129">In questo esempio viene compilata una matrice i cui elementi sono costituiti da matrici.</span><span class="sxs-lookup"><span data-stu-id="8cfc5-129">This example builds an array whose elements are themselves arrays.</span></span> <span data-ttu-id="8cfc5-130">Ogni elemento della matrice ha una dimensione diversa.</span><span class="sxs-lookup"><span data-stu-id="8cfc5-130">Each one of the array elements has a different size.</span></span>  
  
 [!code-csharp[csProgGuideArrays#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#18)]  
  
## <a name="see-also"></a><span data-ttu-id="8cfc5-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cfc5-131">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="8cfc5-132">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="8cfc5-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8cfc5-133">Matrici</span><span class="sxs-lookup"><span data-stu-id="8cfc5-133">Arrays</span></span>](./index.md)
- [<span data-ttu-id="8cfc5-134">Matrici unidimensionali</span><span class="sxs-lookup"><span data-stu-id="8cfc5-134">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="8cfc5-135">Matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="8cfc5-135">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
