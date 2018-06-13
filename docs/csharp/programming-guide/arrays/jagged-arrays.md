---
title: Matrici irregolari (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
ms.openlocfilehash: c1825e1a731c40a5945060f8085bd612b5d62008
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33297368"
---
# <a name="jagged-arrays-c-programming-guide"></a><span data-ttu-id="ab812-102">Matrici irregolari (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="ab812-102">Jagged Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="ab812-103">Una matrice di matrici è una matrice i cui elementi sono costituiti da matrici.</span><span class="sxs-lookup"><span data-stu-id="ab812-103">A jagged array is an array whose elements are arrays.</span></span> <span data-ttu-id="ab812-104">Gli elementi di una matrice di matrici possono presentare dimensioni e misure diverse.</span><span class="sxs-lookup"><span data-stu-id="ab812-104">The elements of a jagged array can be of different dimensions and sizes.</span></span> <span data-ttu-id="ab812-105">Una matrice di matrici è chiamata talvolta "matrice irregolare".</span><span class="sxs-lookup"><span data-stu-id="ab812-105">A jagged array is sometimes called an "array of arrays."</span></span> <span data-ttu-id="ab812-106">Gli esempi seguenti mostrano come dichiarare, inizializzare e accedere a matrici di matrici.</span><span class="sxs-lookup"><span data-stu-id="ab812-106">The following examples show how to declare, initialize, and access jagged arrays.</span></span>  
  
 <span data-ttu-id="ab812-107">Di seguito è riportata la dichiarazione di una matrice unidimensionale a tre elementi, ognuno dei quali è una matrice unidimensionale di Integer:</span><span class="sxs-lookup"><span data-stu-id="ab812-107">The following is a declaration of a single-dimensional array that has three elements, each of which is a single-dimensional array of integers:</span></span>  
  
 [!code-csharp[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]  
  
 <span data-ttu-id="ab812-108">Prima di poter usare `jaggedArray`, è necessario che siano stati inizializzati i relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="ab812-108">Before you can use `jaggedArray`, its elements must be initialized.</span></span> <span data-ttu-id="ab812-109">È possibile inizializzare gli elementi nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="ab812-109">You can initialize the elements like this:</span></span>  
  
 [!code-csharp[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]  
  
 <span data-ttu-id="ab812-110">Ognuno degli elementi è costituito da una matrice unidimensionale di Integer.</span><span class="sxs-lookup"><span data-stu-id="ab812-110">Each of the elements is a single-dimensional array of integers.</span></span> <span data-ttu-id="ab812-111">Il primo elemento è una matrice di 5 Integer, il secondo una matrice di 4 Integer e il terzo una matrice di 2 Integer.</span><span class="sxs-lookup"><span data-stu-id="ab812-111">The first element is an array of 5 integers, the second is an array of 4 integers, and the third is an array of 2 integers.</span></span>  
  
 <span data-ttu-id="ab812-112">È possibile usare gli inizializzatori anche per immettere i valori negli elementi delle matrici. In questo caso, non occorre conoscere le dimensioni delle matrici.</span><span class="sxs-lookup"><span data-stu-id="ab812-112">It is also possible to use initializers to fill the array elements with values, in which case you do not need the array size.</span></span> <span data-ttu-id="ab812-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ab812-113">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]  
  
 <span data-ttu-id="ab812-114">È inoltre possibile inizializzare la matrice al momento della dichiarazione, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ab812-114">You can also initialize the array upon declaration like this:</span></span>  
  
 [!code-csharp[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]  
  
 <span data-ttu-id="ab812-115">È possibile usare la forma abbreviata seguente.</span><span class="sxs-lookup"><span data-stu-id="ab812-115">You can use the following shorthand form.</span></span> <span data-ttu-id="ab812-116">Non è possibile omettere l'operatore `new` poiché non è prevista alcuna inizializzazione predefinita per gli elementi:</span><span class="sxs-lookup"><span data-stu-id="ab812-116">Notice that you cannot omit the `new` operator from the elements initialization because there is no default initialization for the elements:</span></span>  
  
 [!code-csharp[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]  
  
 <span data-ttu-id="ab812-117">Una matrice irregolare è una matrice di matrici, quindi i relativi elementi sono tipi di riferimento inizializzati su `null`.</span><span class="sxs-lookup"><span data-stu-id="ab812-117">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
 <span data-ttu-id="ab812-118">È possibile accedere ai singoli elementi di una matrice, come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab812-118">You can access individual array elements like these examples:</span></span>  
  
 [!code-csharp[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]  
  
 <span data-ttu-id="ab812-119">È possibile combinare matrici di matrici e matrici multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="ab812-119">It is possible to mix jagged and multidimensional arrays.</span></span> <span data-ttu-id="ab812-120">Di seguito sono riportate la dichiarazione e l'inizializzazione di una matrice di matrici unidimensionale che contiene tre elementi matrice bidimensionali con dimensioni diverse.</span><span class="sxs-lookup"><span data-stu-id="ab812-120">The following is a declaration and initialization of a single-dimensional jagged array that contains three two-dimensional array elements of different sizes.</span></span> <span data-ttu-id="ab812-121">Per altre informazioni sulle matrici bidimensionali, vedere [Matrici multidimensionali](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="ab812-121">For more information about two-dimensional arrays, see [Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).</span></span>  
  
 [!code-csharp[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]  
  
 <span data-ttu-id="ab812-122">È possibile accedere a singoli elementi, come illustrato in questo esempio, in cui viene visualizzato il valore dell'elemento `[1,0]` della prima matrice (valore `5`):</span><span class="sxs-lookup"><span data-stu-id="ab812-122">You can access individual elements as shown in this example, which displays the value of the element `[1,0]` of the first array (value `5`):</span></span>  
  
 [!code-csharp[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]  
  
 <span data-ttu-id="ab812-123">Il metodo `Length` restituisce il numero di matrici contenute nella matrice di matrici.</span><span class="sxs-lookup"><span data-stu-id="ab812-123">The method `Length` returns the number of arrays contained in the jagged array.</span></span> <span data-ttu-id="ab812-124">Si supponga, ad esempio, che sia stata dichiarata la matrice precedente. In questo caso, la riga</span><span class="sxs-lookup"><span data-stu-id="ab812-124">For example, assuming you have declared the previous array, this line:</span></span>  
  
 [!code-csharp[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]  
  
 <span data-ttu-id="ab812-125">restituisce il valore 3.</span><span class="sxs-lookup"><span data-stu-id="ab812-125">returns a value of 3.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab812-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="ab812-126">Example</span></span>  
 <span data-ttu-id="ab812-127">In questo esempio viene compilata una matrice i cui elementi sono costituiti da matrici.</span><span class="sxs-lookup"><span data-stu-id="ab812-127">This example builds an array whose elements are themselves arrays.</span></span> <span data-ttu-id="ab812-128">Ogni elemento della matrice ha una dimensione diversa.</span><span class="sxs-lookup"><span data-stu-id="ab812-128">Each one of the array elements has a different size.</span></span>  
  
 [!code-csharp[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ab812-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab812-129">See Also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="ab812-130">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="ab812-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ab812-131">Array</span><span class="sxs-lookup"><span data-stu-id="ab812-131">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="ab812-132">Matrici unidimensionali</span><span class="sxs-lookup"><span data-stu-id="ab812-132">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="ab812-133">Matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="ab812-133">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)
