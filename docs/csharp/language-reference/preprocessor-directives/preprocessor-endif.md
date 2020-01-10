---
title: '#endif - Riferimenti per C#'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: cc344a224e2308e843328b228dd5e2466d02069f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712546"
---
# <a name="endif-c-reference"></a><span data-ttu-id="9f95d-102">#endif (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="9f95d-102">#endif (C# Reference)</span></span>
<span data-ttu-id="9f95d-103">`#endif` specifica la fine di una direttiva condizionale iniziata con la direttiva [#if](./preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="9f95d-103">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="9f95d-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9f95d-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="9f95d-105">Note</span><span class="sxs-lookup"><span data-stu-id="9f95d-105">Remarks</span></span>  
 <span data-ttu-id="9f95d-106">Una direttiva condizionale che inizia con `#if` deve terminare in modo esplicito con una direttiva `#endif`.</span><span class="sxs-lookup"><span data-stu-id="9f95d-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="9f95d-107">Per un esempio di utilizzo di `#endif`, vedere [#if](./preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="9f95d-107">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f95d-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f95d-108">See also</span></span>

- [<span data-ttu-id="9f95d-109">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="9f95d-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9f95d-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="9f95d-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9f95d-111">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="9f95d-111">C# Preprocessor Directives</span></span>](./index.md)
