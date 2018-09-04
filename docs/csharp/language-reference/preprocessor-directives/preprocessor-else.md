---
title: '#else (Riferimenti per C#)'
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: 000cbaac4458a104214e3197442a21dcb4740a37
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43406154"
---
# <a name="else-c-reference"></a><span data-ttu-id="8b897-102">#else (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="8b897-102">#else (C# Reference)</span></span>
<span data-ttu-id="8b897-103">`#else` consente di creare una direttiva condizionale composita. In questo modo, se nessuna delle espressioni delle direttive [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) o [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) (facoltativa) precedenti ha restituito `true`, il compilatore valuterà tutto il codice tra `#else` e l'espressione `#endif` successiva.</span><span class="sxs-lookup"><span data-stu-id="8b897-103">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) or (optional) [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b897-104">Note</span><span class="sxs-lookup"><span data-stu-id="8b897-104">Remarks</span></span>  
 <span data-ttu-id="8b897-105">La direttiva per il preprocessore `#else` deve essere seguita da [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md).</span><span class="sxs-lookup"><span data-stu-id="8b897-105">[#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="8b897-106">Per un esempio di utilizzo di `#else`, vedere [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="8b897-106">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b897-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b897-107">See Also</span></span>

- [<span data-ttu-id="8b897-108">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="8b897-108">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="8b897-109">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="8b897-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="8b897-110">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="8b897-110">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
