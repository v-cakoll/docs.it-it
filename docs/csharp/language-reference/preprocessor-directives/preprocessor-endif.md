---
title: '#endif - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 74205c836b4eeb2d8b17b907bb13708f3225df08
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608573"
---
# <a name="endif-c-reference"></a><span data-ttu-id="622d6-102">#endif (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="622d6-102">#endif (C# Reference)</span></span>
<span data-ttu-id="622d6-103">`#endif` specifica la fine di una direttiva condizionale iniziata con la direttiva [#if](./preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="622d6-103">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="622d6-104">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="622d6-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="622d6-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="622d6-105">Remarks</span></span>  
 <span data-ttu-id="622d6-106">Una direttiva condizionale che inizia con `#if` deve terminare in modo esplicito con una direttiva `#endif`.</span><span class="sxs-lookup"><span data-stu-id="622d6-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="622d6-107">Per un esempio di utilizzo di `#endif`, vedere [#if](./preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="622d6-107">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="622d6-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="622d6-108">See also</span></span>

- [<span data-ttu-id="622d6-109">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="622d6-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="622d6-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="622d6-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="622d6-111">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="622d6-111">C# Preprocessor Directives</span></span>](./index.md)
