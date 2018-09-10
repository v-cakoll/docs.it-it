---
title: Passaggio di matrici mediante ref e out (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
ms.openlocfilehash: 8da3bf9f8eede72a7bc3cf8380eab66ca2b56e86
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526765"
---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a><span data-ttu-id="0a3af-102">Passaggio di matrici mediante ref e out (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="0a3af-102">Passing Arrays Using ref and out (C# Programming Guide)</span></span>

<span data-ttu-id="0a3af-103">Analogamente a tutti i parametri [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), anche il parametro `out` di un tipo di matrice deve essere assegnato prima dell'utilizzo, ovvero assegnato dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="0a3af-103">Like all [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameters, an `out` parameter of an array type must be assigned before it is used; that is, it must be assigned by the callee.</span></span> <span data-ttu-id="0a3af-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0a3af-104">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]  
  
 <span data-ttu-id="0a3af-105">Come tutti i parametri [ref](../../../csharp/language-reference/keywords/ref.md), anche il parametro `ref` di un tipo di matrice deve essere assegnato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="0a3af-105">Like all [ref](../../../csharp/language-reference/keywords/ref.md) parameters, a `ref` parameter of an array type must be definitely assigned by the caller.</span></span> <span data-ttu-id="0a3af-106">Non è pertanto necessario che venga assegnato dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="0a3af-106">Therefore, there is no need to be definitely assigned by the callee.</span></span> <span data-ttu-id="0a3af-107">Il parametro `ref` di un tipo di matrice può risultare modificato in conseguenza della chiamata.</span><span class="sxs-lookup"><span data-stu-id="0a3af-107">A `ref` parameter of an array type may be altered as a result of the call.</span></span> <span data-ttu-id="0a3af-108">È possibile, ad esempio, che alla matrice venga assegnato il valore [null](../../../csharp/language-reference/keywords/null.md) o che venga inizializzata con una matrice diversa.</span><span class="sxs-lookup"><span data-stu-id="0a3af-108">For example, the array can be assigned the [null](../../../csharp/language-reference/keywords/null.md) value or can be initialized to a different array.</span></span> <span data-ttu-id="0a3af-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0a3af-109">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]  
  
 <span data-ttu-id="0a3af-110">Nei due esempi che seguono viene illustrata la differenza tra `out` e `ref` quando vengono utilizzati per passare matrici a metodi.</span><span class="sxs-lookup"><span data-stu-id="0a3af-110">The following two examples demonstrate the difference between `out` and `ref` when used in passing arrays to methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a3af-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="0a3af-111">Example</span></span>

 <span data-ttu-id="0a3af-112">In questo esempio la matrice `theArray` viene dichiarata nel chiamante (il metodo `Main`) e inizializzata nel metodo `FillArray`.</span><span class="sxs-lookup"><span data-stu-id="0a3af-112">In this example, the array `theArray` is declared in the caller (the `Main` method), and initialized in the `FillArray` method.</span></span> <span data-ttu-id="0a3af-113">Gli elementi vengono quindi restituiti al chiamante e visualizzati.</span><span class="sxs-lookup"><span data-stu-id="0a3af-113">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 [!code-csharp[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]

## <a name="example"></a><span data-ttu-id="0a3af-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="0a3af-114">Example</span></span>

 <span data-ttu-id="0a3af-115">In questo esempio la matrice `theArray` viene inizializzata nel chiamante (il metodo `Main`) e passata al metodo `FillArray` utilizzando il parametro `ref`.</span><span class="sxs-lookup"><span data-stu-id="0a3af-115">In this example, the array `theArray` is initialized in the caller (the `Main` method), and passed to the `FillArray` method by using the `ref` parameter.</span></span> <span data-ttu-id="0a3af-116">Alcuni degli elementi della matrice vengono aggiornati nel metodo `FillArray`.</span><span class="sxs-lookup"><span data-stu-id="0a3af-116">Some of the array elements are updated in the `FillArray` method.</span></span> <span data-ttu-id="0a3af-117">Gli elementi vengono quindi restituiti al chiamante e visualizzati.</span><span class="sxs-lookup"><span data-stu-id="0a3af-117">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 [!code-csharp[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0a3af-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a3af-118">See Also</span></span>

- [<span data-ttu-id="0a3af-119">ref</span><span class="sxs-lookup"><span data-stu-id="0a3af-119">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
- [<span data-ttu-id="0a3af-120">Modificatore del parametro out</span><span class="sxs-lookup"><span data-stu-id="0a3af-120">out parameter modifier</span></span>](../../../csharp/language-reference/keywords/out-parameter-modifier.md)  
- [<span data-ttu-id="0a3af-121">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="0a3af-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="0a3af-122">Array</span><span class="sxs-lookup"><span data-stu-id="0a3af-122">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
- [<span data-ttu-id="0a3af-123">Matrici unidimensionali</span><span class="sxs-lookup"><span data-stu-id="0a3af-123">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
- [<span data-ttu-id="0a3af-124">Matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="0a3af-124">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
- [<span data-ttu-id="0a3af-125">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="0a3af-125">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
