---
title: '#elif - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: 00a9298be6ecd6f5e775d930190ddb6e227e4711
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587229"
---
# <a name="elif-c-reference"></a><span data-ttu-id="e1664-102">#elif (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e1664-102">#elif (C# Reference)</span></span>
<span data-ttu-id="e1664-103">`#elif` consente di creare una direttiva condizionale composita.</span><span class="sxs-lookup"><span data-stu-id="e1664-103">`#elif` lets you create a compound conditional directive.</span></span> <span data-ttu-id="e1664-104">L'espressione `#elif` viene valutata quando né l'espressione [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) che la precede, né eventuali espressioni delle direttive `#elif` facoltative che la precedono, restituiscono `true`.</span><span class="sxs-lookup"><span data-stu-id="e1664-104">The `#elif` expression will be evaluated if neither the preceding [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) nor any preceding, optional, `#elif` directive expressions evaluate to `true`.</span></span> <span data-ttu-id="e1664-105">Se un'espressione `#elif` restituisce `true`, il compilatore valuterà tutto il codice compreso tra `#elif` e la direttiva condizionale successiva.</span><span class="sxs-lookup"><span data-stu-id="e1664-105">If a `#elif` expression evaluates to `true`, the compiler evaluates all the code between the `#elif` and the next conditional directive.</span></span> <span data-ttu-id="e1664-106">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e1664-106">For example:</span></span>  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 <span data-ttu-id="e1664-107">È possibile usare gli operatori `==` (uguaglianza), `!=` (disuguaglianza), `&&` (and), e `||` (or) per valutare più simboli.</span><span class="sxs-lookup"><span data-stu-id="e1664-107">You can use the operators `==` (equality), `!=` (inequality), `&&` (and), and `||` (or), to evaluate multiple symbols.</span></span> <span data-ttu-id="e1664-108">È anche possibile raggruppare simboli e operatori tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="e1664-108">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1664-109">Note</span><span class="sxs-lookup"><span data-stu-id="e1664-109">Remarks</span></span>  
 <span data-ttu-id="e1664-110">`#elif` equivale a usare:</span><span class="sxs-lookup"><span data-stu-id="e1664-110">`#elif` is equivalent to using:</span></span>  
  
```csharp
#else  
#if  
```  
  
 <span data-ttu-id="e1664-111">L'utilizzo di `#elif` è più semplice perché ogni espressione `#if` richiede un'espressione [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), mentre un'espressione `#elif` può essere usata anche senza un'espressione `#endif` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="e1664-111">Using `#elif` is simpler, because each `#if` requires a [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), whereas a `#elif` can be used without a matching `#endif`.</span></span>  
  
 <span data-ttu-id="e1664-112">Per un esempio di utilizzo di `#elif`, vedere [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="e1664-112">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#elif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1664-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1664-113">See also</span></span>

- [<span data-ttu-id="e1664-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e1664-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="e1664-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e1664-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e1664-116">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="e1664-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
