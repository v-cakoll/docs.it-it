---
title: '#else - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: d6a514f71b3526b2ffe347cdd971b81907fb0aad
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605721"
---
# <a name="else-c-reference"></a><span data-ttu-id="a293e-102">#else (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a293e-102">#else (C# Reference)</span></span>
<span data-ttu-id="a293e-103">`#else` consente di creare una direttiva condizionale composita. In questo modo, se nessuna delle espressioni delle direttive [#if](./preprocessor-if.md) o [#elif](./preprocessor-elif.md) (facoltativa) precedenti ha restituito `true`, il compilatore valuterà tutto il codice tra `#else` e l'espressione `#endif` successiva.</span><span class="sxs-lookup"><span data-stu-id="a293e-103">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](./preprocessor-if.md) or (optional) [#elif](./preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a293e-104">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a293e-104">Remarks</span></span>  
 <span data-ttu-id="a293e-105">La direttiva per il preprocessore `#else` deve essere seguita da [#endif](./preprocessor-endif.md).</span><span class="sxs-lookup"><span data-stu-id="a293e-105">[#endif](./preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="a293e-106">Per un esempio di utilizzo di `#else`, vedere [#if](./preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="a293e-106">See [#if](./preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a293e-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a293e-107">See also</span></span>

- [<span data-ttu-id="a293e-108">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="a293e-108">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a293e-109">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a293e-109">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a293e-110">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="a293e-110">C# Preprocessor Directives</span></span>](./index.md)
