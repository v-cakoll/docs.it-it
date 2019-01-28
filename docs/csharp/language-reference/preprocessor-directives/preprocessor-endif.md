---
title: '#endif - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 58e29363ca1298966ecf88e6b456f33f43a176b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573046"
---
# <a name="endif-c-reference"></a><span data-ttu-id="1e9ae-102">#endif (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="1e9ae-102">#endif (C# Reference)</span></span>
<span data-ttu-id="1e9ae-103">`#endif` specifica la fine di una direttiva condizionale iniziata con la direttiva [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="1e9ae-103">`#endif` specifies the end of a conditional directive, which began with the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive.</span></span> <span data-ttu-id="1e9ae-104">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="1e9ae-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="1e9ae-105">Note</span><span class="sxs-lookup"><span data-stu-id="1e9ae-105">Remarks</span></span>  
 <span data-ttu-id="1e9ae-106">Una direttiva condizionale che inizia con `#if` deve terminare in modo esplicito con una direttiva `#endif`.</span><span class="sxs-lookup"><span data-stu-id="1e9ae-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="1e9ae-107">Per un esempio di utilizzo di `#endif`, vedere [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="1e9ae-107">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e9ae-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e9ae-108">See also</span></span>

- [<span data-ttu-id="1e9ae-109">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="1e9ae-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="1e9ae-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="1e9ae-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="1e9ae-111">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="1e9ae-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
