---
title: Matrici multidimensionali (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
caps.latest.revision: 16
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
ms.openlocfilehash: 0203046e2038e97cf791141f6863fd8940b22ea4
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="multidimensional-arrays-c-programming-guide"></a><span data-ttu-id="d9777-102">Matrici multidimensionali (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="d9777-102">Multidimensional Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="d9777-103">Le matrici possono avere più di una dimensione.</span><span class="sxs-lookup"><span data-stu-id="d9777-103">Arrays can have more than one dimension.</span></span> <span data-ttu-id="d9777-104">La dichiarazione seguente, ad esempio, crea una matrice bidimensionale di quattro righe e due colonne.</span><span class="sxs-lookup"><span data-stu-id="d9777-104">For example, the following declaration creates a two-dimensional array of four rows and two columns.</span></span>  
  
 <span data-ttu-id="d9777-105">[!code-cs[csProgGuideArrays#11](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d9777-105">[!code-cs[csProgGuideArrays#11](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_1.cs)]</span></span>  
  
 <span data-ttu-id="d9777-106">La dichiarazione seguente crea una matrice a tre dimensioni: 4, 2 e 3.</span><span class="sxs-lookup"><span data-stu-id="d9777-106">The following declaration creates an array of three dimensions, 4, 2, and 3.</span></span>  
  
 <span data-ttu-id="d9777-107">[!code-cs[csProgGuideArrays#12](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d9777-107">[!code-cs[csProgGuideArrays#12](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_2.cs)]</span></span>  
  
## <a name="array-initialization"></a><span data-ttu-id="d9777-108">Inizializzazione di una matrice</span><span class="sxs-lookup"><span data-stu-id="d9777-108">Array Initialization</span></span>  
 <span data-ttu-id="d9777-109">È possibile inizializzare la matrice al momento della dichiarazione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d9777-109">You can initialize the array upon declaration, as is shown in the following example.</span></span>  
  
 <span data-ttu-id="d9777-110">[!code-cs[csProgGuideArrays#13](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="d9777-110">[!code-cs[csProgGuideArrays#13](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_3.cs)]</span></span>  
  
 <span data-ttu-id="d9777-111">È possibile anche inizializzare la matrice senza specificarne il numero di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d9777-111">You also can initialize the array without specifying the rank.</span></span>  
  
 <span data-ttu-id="d9777-112">[!code-cs[csProgGuideArrays#14](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="d9777-112">[!code-cs[csProgGuideArrays#14](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_4.cs)]</span></span>  
  
 <span data-ttu-id="d9777-113">Se si sceglie di dichiarare una variabile di matrice senza inizializzazione, è necessario usare l'operatore `new` per assegnare una matrice alla variabile.</span><span class="sxs-lookup"><span data-stu-id="d9777-113">If you choose to declare an array variable without initialization, you must use the `new` operator to assign an array to the variable.</span></span> <span data-ttu-id="d9777-114">L'utilizzo di `new` è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d9777-114">The use of `new` is shown in the following example.</span></span>  
  
 <span data-ttu-id="d9777-115">[!code-cs[csProgGuideArrays#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="d9777-115">[!code-cs[csProgGuideArrays#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_5.cs)]</span></span>  
  
 <span data-ttu-id="d9777-116">Nell'esempio seguente viene assegnato un valore a un elemento specifico della matrice.</span><span class="sxs-lookup"><span data-stu-id="d9777-116">The following example assigns a value to a particular array element.</span></span>  
  
 <span data-ttu-id="d9777-117">[!code-cs[csProgGuideArrays#16](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="d9777-117">[!code-cs[csProgGuideArrays#16](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_6.cs)]</span></span>  
  
 <span data-ttu-id="d9777-118">Analogamente, nell'esempio seguente viene ottenuto il valore di un elemento specifico della matrice, che viene assegnato alla variabile `elementValue`.</span><span class="sxs-lookup"><span data-stu-id="d9777-118">Similarly, the following example gets the value of a particular array element and assigns it to variable `elementValue`.</span></span>  
  
 <span data-ttu-id="d9777-119">[!code-cs[csProgGuideArrays#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="d9777-119">[!code-cs[csProgGuideArrays#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_7.cs)]</span></span>  
  
 <span data-ttu-id="d9777-120">Nell'esempio di codice seguente, gli elementi della matrice vengono inizializzati in base ai valori predefiniti (ad eccezione delle matrici di matrici).</span><span class="sxs-lookup"><span data-stu-id="d9777-120">The following code example initializes the array elements to default values (except for jagged arrays).</span></span>  
  
 <span data-ttu-id="d9777-121">[!code-cs[csProgGuideArrays#17](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="d9777-121">[!code-cs[csProgGuideArrays#17](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_8.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9777-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9777-122">See Also</span></span>  
 <span data-ttu-id="d9777-123">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d9777-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d9777-124">[Matrici](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="d9777-124">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="d9777-125">[Matrici unidimensionali](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="d9777-125">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 [<span data-ttu-id="d9777-126">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="d9777-126">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

