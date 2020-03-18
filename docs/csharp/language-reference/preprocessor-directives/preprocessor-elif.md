---
title: '#elif - Riferimenti per C#'
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: c78818f40b76414d289af6c704ff019b63befe37
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712572"
---
# <a name="elif-c-reference"></a><span data-ttu-id="3a089-102">#elif (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="3a089-102">#elif (C# Reference)</span></span>
<span data-ttu-id="3a089-103">`#elif` consente di creare una direttiva condizionale composita.</span><span class="sxs-lookup"><span data-stu-id="3a089-103">`#elif` lets you create a compound conditional directive.</span></span> <span data-ttu-id="3a089-104">L'espressione `#elif` viene valutata quando né l'espressione [#if](./preprocessor-if.md) che la precede, né eventuali espressioni delle direttive `#elif` facoltative che la precedono, restituiscono `true`.</span><span class="sxs-lookup"><span data-stu-id="3a089-104">The `#elif` expression will be evaluated if neither the preceding [#if](./preprocessor-if.md) nor any preceding, optional, `#elif` directive expressions evaluate to `true`.</span></span> <span data-ttu-id="3a089-105">Se un'espressione `#elif` restituisce `true`, il compilatore valuterà tutto il codice compreso tra `#elif` e la direttiva condizionale successiva.</span><span class="sxs-lookup"><span data-stu-id="3a089-105">If a `#elif` expression evaluates to `true`, the compiler evaluates all the code between the `#elif` and the next conditional directive.</span></span> <span data-ttu-id="3a089-106">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3a089-106">For example:</span></span>  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 <span data-ttu-id="3a089-107">È possibile usare gli operatori `==` (uguaglianza), `!=` (disuguaglianza), `&&` (and), e `||` (or) per valutare più simboli.</span><span class="sxs-lookup"><span data-stu-id="3a089-107">You can use the operators `==` (equality), `!=` (inequality), `&&` (and), and `||` (or), to evaluate multiple symbols.</span></span> <span data-ttu-id="3a089-108">È anche possibile raggruppare simboli e operatori tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="3a089-108">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a089-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3a089-109">Remarks</span></span>  
 <span data-ttu-id="3a089-110">`#elif` equivale a usare:</span><span class="sxs-lookup"><span data-stu-id="3a089-110">`#elif` is equivalent to using:</span></span>  
  
```csharp
#else  
#if  
```  
  
 <span data-ttu-id="3a089-111">L'utilizzo di `#elif` è più semplice perché ogni espressione `#if` richiede un'espressione [#endif](./preprocessor-endif.md), mentre un'espressione `#elif` può essere usata anche senza un'espressione `#endif` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="3a089-111">Using `#elif` is simpler, because each `#if` requires a [#endif](./preprocessor-endif.md), whereas a `#elif` can be used without a matching `#endif`.</span></span>  
  
 <span data-ttu-id="3a089-112">Per un esempio di utilizzo di `#elif`, vedere [#if](./preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="3a089-112">See [#if](./preprocessor-if.md) for an example of how to use `#elif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a089-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a089-113">See also</span></span>

- [<span data-ttu-id="3a089-114">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="3a089-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3a089-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3a089-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3a089-116">Direttive per il preprocessore di C</span><span class="sxs-lookup"><span data-stu-id="3a089-116">C# Preprocessor Directives</span></span>](./index.md)
