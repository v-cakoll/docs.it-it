---
title: '#else - Riferimenti per C#'
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: 967ef38687b739ef3bea3f8923ab26bba0b6cea9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712559"
---
# <a name="else-c-reference"></a><span data-ttu-id="e27db-102">#else (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e27db-102">#else (C# Reference)</span></span>
<span data-ttu-id="e27db-103">`#else` consente di creare una direttiva condizionale composita. In questo modo, se nessuna delle espressioni delle direttive [#if](./preprocessor-if.md) o [#elif](./preprocessor-elif.md) (facoltativa) precedenti ha restituito `true`, il compilatore valuterà tutto il codice tra `#else` e l'espressione `#endif` successiva.</span><span class="sxs-lookup"><span data-stu-id="e27db-103">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](./preprocessor-if.md) or (optional) [#elif](./preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e27db-104">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e27db-104">Remarks</span></span>  
 <span data-ttu-id="e27db-105">La direttiva per il preprocessore `#else` deve essere seguita da [#endif](./preprocessor-endif.md).</span><span class="sxs-lookup"><span data-stu-id="e27db-105">[#endif](./preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="e27db-106">Per un esempio di utilizzo di `#else`, vedere [#if](./preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="e27db-106">See [#if](./preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e27db-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e27db-107">See also</span></span>

- [<span data-ttu-id="e27db-108">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="e27db-108">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e27db-109">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e27db-109">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e27db-110">Direttive per il preprocessore di C</span><span class="sxs-lookup"><span data-stu-id="e27db-110">C# Preprocessor Directives</span></span>](./index.md)
