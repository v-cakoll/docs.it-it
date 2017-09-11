---
title: Matrici unidimensionali (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
caps.latest.revision: 18
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
ms.openlocfilehash: cc42640715274b89c4c4a12ced8c0ae6af603318
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="47d44-102">Matrici unidimensionali (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="47d44-102">Single-Dimensional Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="47d44-103">È possibile dichiarare una matrice unidimensionale di cinque valori integer, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="47d44-103">You can declare a single-dimensional array of five integers as shown in the following example:</span></span>  
  
 <span data-ttu-id="47d44-104">[!code-cs[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="47d44-104">[!code-cs[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]</span></span>  
  
 <span data-ttu-id="47d44-105">Questa matrice contiene gli elementi da `array[0]` a `array[4]`.</span><span class="sxs-lookup"><span data-stu-id="47d44-105">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="47d44-106">L'operatore [new](../../../csharp/language-reference/keywords/new.md) viene usato per creare la matrice e inizializzare gli elementi della matrice ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="47d44-106">The [new](../../../csharp/language-reference/keywords/new.md) operator is used to create the array and initialize the array elements to their default values.</span></span> <span data-ttu-id="47d44-107">In questo esempio, tutti gli elementi della matrice vengono inizializzati su zero.</span><span class="sxs-lookup"><span data-stu-id="47d44-107">In this example, all the array elements are initialized to zero.</span></span>  
  
 <span data-ttu-id="47d44-108">È possibile dichiarare una matrice che archivia elementi stringa nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="47d44-108">An array that stores string elements can be declared in the same way.</span></span> <span data-ttu-id="47d44-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="47d44-109">For example:</span></span>  
  
 <span data-ttu-id="47d44-110">[!code-cs[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="47d44-110">[!code-cs[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]</span></span>  
  
## <a name="array-initialization"></a><span data-ttu-id="47d44-111">Inizializzazione di una matrice</span><span class="sxs-lookup"><span data-stu-id="47d44-111">Array Initialization</span></span>  
 <span data-ttu-id="47d44-112">È possibile inizializzare una matrice al momento della dichiarazione. In tal caso, l'identificatore del numero di dimensioni non è necessario perché è già fornito dal numero di elementi nell'elenco di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="47d44-112">It is possible to initialize an array upon declaration, in which case, the rank specifier is not needed because it is already supplied by the number of elements in the initialization list.</span></span> <span data-ttu-id="47d44-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="47d44-113">For example:</span></span>  
  
 <span data-ttu-id="47d44-114">[!code-cs[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="47d44-114">[!code-cs[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]</span></span>  
  
 <span data-ttu-id="47d44-115">Una matrice di stringhe può essere inizializzata nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="47d44-115">A string array can be initialized in the same way.</span></span> <span data-ttu-id="47d44-116">Di seguito è riportata una dichiarazione di una matrice di stringhe in cui ogni elemento della matrice viene inizializzato da un nome di un giorno:</span><span class="sxs-lookup"><span data-stu-id="47d44-116">The following is a declaration of a string array where each array element is initialized by a name of a day:</span></span>  
  
 <span data-ttu-id="47d44-117">[!code-cs[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="47d44-117">[!code-cs[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]</span></span>  
  
 <span data-ttu-id="47d44-118">Durante l'inizializzazione di una matrice al momento della dichiarazione, è possibile usare i collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="47d44-118">When you initialize an array upon declaration, you can use the following shortcuts:</span></span>  
  
 <span data-ttu-id="47d44-119">[!code-cs[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="47d44-119">[!code-cs[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]</span></span>  
  
 <span data-ttu-id="47d44-120">È possibile dichiarare una variabile di matrice senza inizializzazione, ma è necessario usare l'operatore `new` quando si assegna una matrice a questa variabile.</span><span class="sxs-lookup"><span data-stu-id="47d44-120">It is possible to declare an array variable without initialization, but you must use the `new` operator when you assign an array to this variable.</span></span> <span data-ttu-id="47d44-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="47d44-121">For example:</span></span>  
  
 <span data-ttu-id="47d44-122">[!code-cs[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="47d44-122">[!code-cs[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]</span></span>  
  
 <span data-ttu-id="47d44-123">In C# 3.0 sono state introdotte le matrici tipizzate in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="47d44-123">C# 3.0 introduces implicitly typed arrays.</span></span> <span data-ttu-id="47d44-124">Per altre informazioni, vedere [Matrici tipizzate in modo implicito](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="47d44-124">For more information, see [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="47d44-125">Matrici di tipo valore e di tipo riferimento</span><span class="sxs-lookup"><span data-stu-id="47d44-125">Value Type and Reference Type Arrays</span></span>  
 <span data-ttu-id="47d44-126">Considerare la dichiarazione di matrice seguente:</span><span class="sxs-lookup"><span data-stu-id="47d44-126">Consider the following array declaration:</span></span>  
  
 <span data-ttu-id="47d44-127">[!code-cs[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="47d44-127">[!code-cs[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]</span></span>  
  
 <span data-ttu-id="47d44-128">Il risultato di questa istruzione dipende dal fatto che `SomeType` sia un tipo valore o un tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="47d44-128">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="47d44-129">Se è un tipo valore, l'istruzione crea una matrice di 10 elementi, ognuno dei quali ha il tipo `SomeType`.</span><span class="sxs-lookup"><span data-stu-id="47d44-129">If it is a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="47d44-130">Se `SomeType` è un tipo riferimento, l'istruzione crea una matrice di 10 elementi, ognuno dei quali è inizializzato su un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="47d44-130">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span>  
  
 <span data-ttu-id="47d44-131">Per altre informazioni su tipi valore e tipi riferimento, vedere [Tipi](../../../csharp/language-reference/keywords/types.md).</span><span class="sxs-lookup"><span data-stu-id="47d44-131">For more information about value types and reference types, see [Types](../../../csharp/language-reference/keywords/types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47d44-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47d44-132">See Also</span></span>  
 <span data-ttu-id="47d44-133"><xref:System.Array></span><span class="sxs-lookup"><span data-stu-id="47d44-133"><xref:System.Array></span></span>   
 <span data-ttu-id="47d44-134">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="47d44-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="47d44-135">[Matrici](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="47d44-135">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="47d44-136">[Matrici multidimensionali](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="47d44-136">[Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span></span>  
 [<span data-ttu-id="47d44-137">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="47d44-137">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

