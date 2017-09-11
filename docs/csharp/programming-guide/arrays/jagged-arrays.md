---
title: Matrici irregolari (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
caps.latest.revision: 24
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
ms.openlocfilehash: cb6c0823af37924235dba7daa20e607cb8402a79
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="jagged-arrays-c-programming-guide"></a><span data-ttu-id="ec841-102">Matrici irregolari (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="ec841-102">Jagged Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="ec841-103">Una matrice di matrici è una matrice i cui elementi sono costituiti da matrici.</span><span class="sxs-lookup"><span data-stu-id="ec841-103">A jagged array is an array whose elements are arrays.</span></span> <span data-ttu-id="ec841-104">Gli elementi di una matrice di matrici possono presentare dimensioni e misure diverse.</span><span class="sxs-lookup"><span data-stu-id="ec841-104">The elements of a jagged array can be of different dimensions and sizes.</span></span> <span data-ttu-id="ec841-105">Una matrice di matrici è chiamata talvolta "matrice irregolare".</span><span class="sxs-lookup"><span data-stu-id="ec841-105">A jagged array is sometimes called an "array of arrays."</span></span> <span data-ttu-id="ec841-106">Gli esempi seguenti mostrano come dichiarare, inizializzare e accedere a matrici di matrici.</span><span class="sxs-lookup"><span data-stu-id="ec841-106">The following examples show how to declare, initialize, and access jagged arrays.</span></span>  
  
 <span data-ttu-id="ec841-107">Di seguito è riportata la dichiarazione di una matrice unidimensionale a tre elementi, ognuno dei quali è una matrice unidimensionale di Integer:</span><span class="sxs-lookup"><span data-stu-id="ec841-107">The following is a declaration of a single-dimensional array that has three elements, each of which is a single-dimensional array of integers:</span></span>  
  
 <span data-ttu-id="ec841-108">[!code-cs[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ec841-108">[!code-cs[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]</span></span>  
  
 <span data-ttu-id="ec841-109">Prima di poter usare `jaggedArray`, è necessario che siano stati inizializzati i relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="ec841-109">Before you can use `jaggedArray`, its elements must be initialized.</span></span> <span data-ttu-id="ec841-110">È possibile inizializzare gli elementi nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="ec841-110">You can initialize the elements like this:</span></span>  
  
 <span data-ttu-id="ec841-111">[!code-cs[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="ec841-111">[!code-cs[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]</span></span>  
  
 <span data-ttu-id="ec841-112">Ognuno degli elementi è costituito da una matrice unidimensionale di Integer.</span><span class="sxs-lookup"><span data-stu-id="ec841-112">Each of the elements is a single-dimensional array of integers.</span></span> <span data-ttu-id="ec841-113">Il primo elemento è una matrice di 5 Integer, il secondo una matrice di 4 Integer e il terzo una matrice di 2 Integer.</span><span class="sxs-lookup"><span data-stu-id="ec841-113">The first element is an array of 5 integers, the second is an array of 4 integers, and the third is an array of 2 integers.</span></span>  
  
 <span data-ttu-id="ec841-114">È possibile usare gli inizializzatori anche per immettere i valori negli elementi delle matrici. In questo caso, non occorre conoscere le dimensioni delle matrici.</span><span class="sxs-lookup"><span data-stu-id="ec841-114">It is also possible to use initializers to fill the array elements with values, in which case you do not need the array size.</span></span> <span data-ttu-id="ec841-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ec841-115">For example:</span></span>  
  
 <span data-ttu-id="ec841-116">[!code-cs[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="ec841-116">[!code-cs[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]</span></span>  
  
 <span data-ttu-id="ec841-117">È inoltre possibile inizializzare la matrice al momento della dichiarazione, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ec841-117">You can also initialize the array upon declaration like this:</span></span>  
  
 <span data-ttu-id="ec841-118">[!code-cs[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="ec841-118">[!code-cs[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]</span></span>  
  
 <span data-ttu-id="ec841-119">È possibile usare la forma abbreviata seguente.</span><span class="sxs-lookup"><span data-stu-id="ec841-119">You can use the following shorthand form.</span></span> <span data-ttu-id="ec841-120">Non è possibile omettere l'operatore `new` poiché non è prevista alcuna inizializzazione predefinita per gli elementi:</span><span class="sxs-lookup"><span data-stu-id="ec841-120">Notice that you cannot omit the `new` operator from the elements initialization because there is no default initialization for the elements:</span></span>  
  
 <span data-ttu-id="ec841-121">[!code-cs[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="ec841-121">[!code-cs[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]</span></span>  
  
 <span data-ttu-id="ec841-122">Una matrice irregolare è una matrice di matrici, quindi i relativi elementi sono tipi di riferimento inizializzati su `null`.</span><span class="sxs-lookup"><span data-stu-id="ec841-122">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
 <span data-ttu-id="ec841-123">È possibile accedere ai singoli elementi di una matrice, come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec841-123">You can access individual array elements like these examples:</span></span>  
  
 <span data-ttu-id="ec841-124">[!code-cs[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="ec841-124">[!code-cs[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]</span></span>  
  
 <span data-ttu-id="ec841-125">È possibile combinare matrici di matrici e matrici multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="ec841-125">It is possible to mix jagged and multidimensional arrays.</span></span> <span data-ttu-id="ec841-126">Di seguito sono riportate la dichiarazione e l'inizializzazione di una matrice di matrici unidimensionale che contiene tre elementi matrice bidimensionali con dimensioni diverse.</span><span class="sxs-lookup"><span data-stu-id="ec841-126">The following is a declaration and initialization of a single-dimensional jagged array that contains three two-dimensional array elements of different sizes.</span></span> <span data-ttu-id="ec841-127">Per altre informazioni sulle matrici bidimensionali, vedere [Matrici multidimensionali](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="ec841-127">For more information about two-dimensional arrays, see [Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).</span></span>  
  
 <span data-ttu-id="ec841-128">[!code-cs[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="ec841-128">[!code-cs[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]</span></span>  
  
 <span data-ttu-id="ec841-129">È possibile accedere a singoli elementi, come illustrato in questo esempio, in cui viene visualizzato il valore dell'elemento `[1,0]` della prima matrice (valore `5`):</span><span class="sxs-lookup"><span data-stu-id="ec841-129">You can access individual elements as shown in this example, which displays the value of the element `[1,0]` of the first array (value `5`):</span></span>  
  
 <span data-ttu-id="ec841-130">[!code-cs[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="ec841-130">[!code-cs[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]</span></span>  
  
 <span data-ttu-id="ec841-131">Il metodo `Length` restituisce il numero di matrici contenute nella matrice di matrici.</span><span class="sxs-lookup"><span data-stu-id="ec841-131">The method `Length` returns the number of arrays contained in the jagged array.</span></span> <span data-ttu-id="ec841-132">Si supponga, ad esempio, che sia stata dichiarata la matrice precedente. In questo caso, la riga</span><span class="sxs-lookup"><span data-stu-id="ec841-132">For example, assuming you have declared the previous array, this line:</span></span>  
  
 <span data-ttu-id="ec841-133">[!code-cs[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="ec841-133">[!code-cs[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]</span></span>  
  
 <span data-ttu-id="ec841-134">restituisce il valore 3.</span><span class="sxs-lookup"><span data-stu-id="ec841-134">returns a value of 3.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec841-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="ec841-135">Example</span></span>  
 <span data-ttu-id="ec841-136">In questo esempio viene compilata una matrice i cui elementi sono costituiti da matrici.</span><span class="sxs-lookup"><span data-stu-id="ec841-136">This example builds an array whose elements are themselves arrays.</span></span> <span data-ttu-id="ec841-137">Ogni elemento della matrice ha una dimensione diversa.</span><span class="sxs-lookup"><span data-stu-id="ec841-137">Each one of the array elements has a different size.</span></span>  
  
 <span data-ttu-id="ec841-138">[!code-cs[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="ec841-138">[!code-cs[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec841-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec841-139">See Also</span></span>  
 <span data-ttu-id="ec841-140"><xref:System.Array></span><span class="sxs-lookup"><span data-stu-id="ec841-140"><xref:System.Array></span></span>   
 <span data-ttu-id="ec841-141">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ec841-141">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ec841-142">[Matrici](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="ec841-142">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="ec841-143">[Matrici unidimensionali](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="ec841-143">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 [<span data-ttu-id="ec841-144">Matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="ec841-144">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)

