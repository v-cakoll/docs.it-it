---
title: Passaggio di matrici mediante ref e out (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
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
ms.openlocfilehash: 58fc359881295a9e6627ac1269ef17aa298009c7
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a><span data-ttu-id="41e47-102">Passaggio di matrici mediante ref e out (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="41e47-102">Passing Arrays Using ref and out (C# Programming Guide)</span></span>
<span data-ttu-id="41e47-103">Analogamente a tutti i parametri [out](../../../csharp/language-reference/keywords/out.md), anche il parametro `out` di un tipo di matrice deve essere assegnato prima dell'utilizzo, ovvero assegnato dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="41e47-103">Like all [out](../../../csharp/language-reference/keywords/out.md) parameters, an `out` parameter of an array type must be assigned before it is used; that is, it must be assigned by the callee.</span></span> <span data-ttu-id="41e47-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="41e47-104">For example:</span></span>  
  
 <span data-ttu-id="41e47-105">[!code-cs[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="41e47-105">[!code-cs[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]</span></span>  
  
 <span data-ttu-id="41e47-106">Come tutti i parametri [ref](../../../csharp/language-reference/keywords/ref.md), anche il parametro `ref` di un tipo di matrice deve essere assegnato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="41e47-106">Like all [ref](../../../csharp/language-reference/keywords/ref.md) parameters, a `ref` parameter of an array type must be definitely assigned by the caller.</span></span> <span data-ttu-id="41e47-107">Non è pertanto necessario che venga assegnato dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="41e47-107">Therefore, there is no need to be definitely assigned by the callee.</span></span> <span data-ttu-id="41e47-108">Il parametro `ref` di un tipo di matrice può risultare modificato in conseguenza della chiamata.</span><span class="sxs-lookup"><span data-stu-id="41e47-108">A `ref` parameter of an array type may be altered as a result of the call.</span></span> <span data-ttu-id="41e47-109">È possibile, ad esempio, che alla matrice venga assegnato il valore [null](../../../csharp/language-reference/keywords/null.md) o che venga inizializzata con una matrice diversa.</span><span class="sxs-lookup"><span data-stu-id="41e47-109">For example, the array can be assigned the [null](../../../csharp/language-reference/keywords/null.md) value or can be initialized to a different array.</span></span> <span data-ttu-id="41e47-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="41e47-110">For example:</span></span>  
  
 <span data-ttu-id="41e47-111">[!code-cs[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="41e47-111">[!code-cs[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]</span></span>  
  
 <span data-ttu-id="41e47-112">Nei due esempi che seguono viene illustrata la differenza tra `out` e `ref` quando vengono utilizzati per passare matrici a metodi.</span><span class="sxs-lookup"><span data-stu-id="41e47-112">The following two examples demonstrate the difference between `out` and `ref` when used in passing arrays to methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41e47-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="41e47-113">Example</span></span>  
 <span data-ttu-id="41e47-114">In questo esempio la matrice `theArray` viene dichiarata nel chiamante (il metodo `Main`) e inizializzata nel metodo `FillArray`.</span><span class="sxs-lookup"><span data-stu-id="41e47-114">In this example, the array `theArray` is declared in the caller (the `Main` method), and initialized in the `FillArray` method.</span></span> <span data-ttu-id="41e47-115">Gli elementi vengono quindi restituiti al chiamante e visualizzati.</span><span class="sxs-lookup"><span data-stu-id="41e47-115">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 <span data-ttu-id="41e47-116">[!code-cs[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="41e47-116">[!code-cs[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="41e47-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="41e47-117">Example</span></span>  
 <span data-ttu-id="41e47-118">In questo esempio la matrice `theArray` viene inizializzata nel chiamante (il metodo `Main`) e passata al metodo `FillArray` utilizzando il parametro `ref`.</span><span class="sxs-lookup"><span data-stu-id="41e47-118">In this example, the array `theArray` is initialized in the caller (the `Main` method), and passed to the `FillArray` method by using the `ref` parameter.</span></span> <span data-ttu-id="41e47-119">Alcuni degli elementi della matrice vengono aggiornati nel metodo `FillArray`.</span><span class="sxs-lookup"><span data-stu-id="41e47-119">Some of the array elements are updated in the `FillArray` method.</span></span> <span data-ttu-id="41e47-120">Gli elementi vengono quindi restituiti al chiamante e visualizzati.</span><span class="sxs-lookup"><span data-stu-id="41e47-120">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 <span data-ttu-id="41e47-121">[!code-cs[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="41e47-121">[!code-cs[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41e47-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41e47-122">See Also</span></span>  
 <span data-ttu-id="41e47-123">[ref](../../../csharp/language-reference/keywords/ref.md) </span><span class="sxs-lookup"><span data-stu-id="41e47-123">[ref](../../../csharp/language-reference/keywords/ref.md) </span></span>  
 <span data-ttu-id="41e47-124">[Modificatore del parametro out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) </span><span class="sxs-lookup"><span data-stu-id="41e47-124">[out parameter modifier](../../../csharp/language-reference/keywords/out-parameter-modifier.md) </span></span>  
 <span data-ttu-id="41e47-125">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="41e47-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="41e47-126">[Matrici](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="41e47-126">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="41e47-127">[Matrici unidimensionali](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="41e47-127">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 <span data-ttu-id="41e47-128">[Matrici multidimensionali](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="41e47-128">[Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span></span>  
 [<span data-ttu-id="41e47-129">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="41e47-129">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

