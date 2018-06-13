---
title: Passaggio di matrici mediante ref e out (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
ms.openlocfilehash: a186399125e01bb2535f3a8b488c6fbd85932246
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33313570"
---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a><span data-ttu-id="858aa-102">Passaggio di matrici mediante ref e out (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="858aa-102">Passing Arrays Using ref and out (C# Programming Guide)</span></span>
<span data-ttu-id="858aa-103">Analogamente a tutti i parametri [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), anche il parametro `out` di un tipo di matrice deve essere assegnato prima dell'utilizzo, ovvero assegnato dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="858aa-103">Like all [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameters, an `out` parameter of an array type must be assigned before it is used; that is, it must be assigned by the callee.</span></span> <span data-ttu-id="858aa-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="858aa-104">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]  
  
 <span data-ttu-id="858aa-105">Come tutti i parametri [ref](../../../csharp/language-reference/keywords/ref.md), anche il parametro `ref` di un tipo di matrice deve essere assegnato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="858aa-105">Like all [ref](../../../csharp/language-reference/keywords/ref.md) parameters, a `ref` parameter of an array type must be definitely assigned by the caller.</span></span> <span data-ttu-id="858aa-106">Non è pertanto necessario che venga assegnato dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="858aa-106">Therefore, there is no need to be definitely assigned by the callee.</span></span> <span data-ttu-id="858aa-107">Il parametro `ref` di un tipo di matrice può risultare modificato in conseguenza della chiamata.</span><span class="sxs-lookup"><span data-stu-id="858aa-107">A `ref` parameter of an array type may be altered as a result of the call.</span></span> <span data-ttu-id="858aa-108">È possibile, ad esempio, che alla matrice venga assegnato il valore [null](../../../csharp/language-reference/keywords/null.md) o che venga inizializzata con una matrice diversa.</span><span class="sxs-lookup"><span data-stu-id="858aa-108">For example, the array can be assigned the [null](../../../csharp/language-reference/keywords/null.md) value or can be initialized to a different array.</span></span> <span data-ttu-id="858aa-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="858aa-109">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]  
  
 <span data-ttu-id="858aa-110">Nei due esempi che seguono viene illustrata la differenza tra `out` e `ref` quando vengono utilizzati per passare matrici a metodi.</span><span class="sxs-lookup"><span data-stu-id="858aa-110">The following two examples demonstrate the difference between `out` and `ref` when used in passing arrays to methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="858aa-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="858aa-111">Example</span></span>  
 <span data-ttu-id="858aa-112">In questo esempio la matrice `theArray` viene dichiarata nel chiamante (il metodo `Main`) e inizializzata nel metodo `FillArray`.</span><span class="sxs-lookup"><span data-stu-id="858aa-112">In this example, the array `theArray` is declared in the caller (the `Main` method), and initialized in the `FillArray` method.</span></span> <span data-ttu-id="858aa-113">Gli elementi vengono quindi restituiti al chiamante e visualizzati.</span><span class="sxs-lookup"><span data-stu-id="858aa-113">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 [!code-csharp[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="858aa-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="858aa-114">Example</span></span>  
 <span data-ttu-id="858aa-115">In questo esempio la matrice `theArray` viene inizializzata nel chiamante (il metodo `Main`) e passata al metodo `FillArray` utilizzando il parametro `ref`.</span><span class="sxs-lookup"><span data-stu-id="858aa-115">In this example, the array `theArray` is initialized in the caller (the `Main` method), and passed to the `FillArray` method by using the `ref` parameter.</span></span> <span data-ttu-id="858aa-116">Alcuni degli elementi della matrice vengono aggiornati nel metodo `FillArray`.</span><span class="sxs-lookup"><span data-stu-id="858aa-116">Some of the array elements are updated in the `FillArray` method.</span></span> <span data-ttu-id="858aa-117">Gli elementi vengono quindi restituiti al chiamante e visualizzati.</span><span class="sxs-lookup"><span data-stu-id="858aa-117">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 [!code-csharp[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="858aa-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="858aa-118">See Also</span></span>  
 [<span data-ttu-id="858aa-119">ref</span><span class="sxs-lookup"><span data-stu-id="858aa-119">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
 [<span data-ttu-id="858aa-120">Modificatore del parametro out</span><span class="sxs-lookup"><span data-stu-id="858aa-120">out parameter modifier</span></span>](../../../csharp/language-reference/keywords/out-parameter-modifier.md)  
 [<span data-ttu-id="858aa-121">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="858aa-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="858aa-122">Array</span><span class="sxs-lookup"><span data-stu-id="858aa-122">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="858aa-123">Matrici unidimensionali</span><span class="sxs-lookup"><span data-stu-id="858aa-123">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="858aa-124">Matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="858aa-124">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="858aa-125">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="858aa-125">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
