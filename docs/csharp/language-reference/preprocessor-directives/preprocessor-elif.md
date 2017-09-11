---
title: '#<a name="elif-c-reference"></a>elif (Riferimenti per C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#elif'
dev_langs:
- CSharp
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
caps.latest.revision: 14
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
ms.openlocfilehash: 7635365222621101253ecb2a3676701c2e6a2b88
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="elif-c-reference"></a><span data-ttu-id="03042-102">#elif (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="03042-102">#elif (C# Reference)</span></span>
<span data-ttu-id="03042-103">`#elif` consente di creare una direttiva condizionale composita.</span><span class="sxs-lookup"><span data-stu-id="03042-103">`#elif` lets you create a compound conditional directive.</span></span> <span data-ttu-id="03042-104">L'espressione `#elif` viene valutata quando né l'espressione [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) che la precede, né eventuali espressioni delle direttive `#elif` facoltative che la precedono, restituiscono `true`.</span><span class="sxs-lookup"><span data-stu-id="03042-104">The `#elif` expression will be evaluated if neither the preceding [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) nor any preceding, optional, `#elif` directive expressions evaluate to `true`.</span></span> <span data-ttu-id="03042-105">Se un'espressione `#elif` restituisce `true`, il compilatore valuterà tutto il codice compreso tra `#elif` e la direttiva condizionale successiva.</span><span class="sxs-lookup"><span data-stu-id="03042-105">If a `#elif` expression evaluates to `true`, the compiler evaluates all the code between the `#elif` and the next conditional directive.</span></span> <span data-ttu-id="03042-106">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="03042-106">For example:</span></span>  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.Writeline("Debug build");  
#elif VC7  
    Console.Writeline("Visual Studio 7");  
#endif  
```  
  
 <span data-ttu-id="03042-107">È possibile usare gli operatori `==` (uguaglianza), `!=` (disuguaglianza), `&&` (and), e `||` (or) per valutare più simboli.</span><span class="sxs-lookup"><span data-stu-id="03042-107">You can use the operators `==` (equality), `!=` (inequality), `&&` (and), and `||` (or), to evaluate multiple symbols.</span></span> <span data-ttu-id="03042-108">È anche possibile raggruppare simboli e operatori tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="03042-108">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03042-109">Note</span><span class="sxs-lookup"><span data-stu-id="03042-109">Remarks</span></span>  
 <span data-ttu-id="03042-110">`#elif` equivale a usare:</span><span class="sxs-lookup"><span data-stu-id="03042-110">`#elif` is equivalent to using:</span></span>  
  
```csharp
#else  
#if  
```  
  
 <span data-ttu-id="03042-111">L'utilizzo di `#elif` è più semplice perché ogni espressione `#if` richiede un'espressione [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), mentre un'espressione `#elif` può essere usata anche senza un'espressione `#endif` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="03042-111">Using `#elif` is simpler, because each `#if` requires a [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), whereas a `#elif` can be used without a matching `#endif`.</span></span>  
  
 <span data-ttu-id="03042-112">Per un esempio di utilizzo di `#elif`, vedere [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="03042-112">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#elif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03042-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03042-113">See Also</span></span>  
 <span data-ttu-id="03042-114">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="03042-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="03042-115">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="03042-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="03042-116">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="03042-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

