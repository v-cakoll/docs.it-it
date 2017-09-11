---
title: '#<a name="endif-c-reference"></a>endif (Riferimenti per C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#endif'
dev_langs:
- CSharp
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
caps.latest.revision: 9
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
ms.openlocfilehash: e4c37657a1ca81b7e5403e58123cf630a224b8ec
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="endif-c-reference"></a><span data-ttu-id="dc0b3-102">#endif (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="dc0b3-102">#endif (C# Reference)</span></span>
<span data-ttu-id="dc0b3-103">`#endif` specifica la fine di una direttiva condizionale iniziata con la direttiva [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="dc0b3-103">`#endif` specifies the end of a conditional directive, which began with the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive.</span></span> <span data-ttu-id="dc0b3-104">Di seguito è riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="dc0b3-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="dc0b3-105">Note</span><span class="sxs-lookup"><span data-stu-id="dc0b3-105">Remarks</span></span>  
 <span data-ttu-id="dc0b3-106">Una direttiva condizionale che inizia con `#if` deve terminare in modo esplicito con una direttiva `#endif`.</span><span class="sxs-lookup"><span data-stu-id="dc0b3-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="dc0b3-107">Per un esempio di utilizzo di `#endif`, vedere [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="dc0b3-107">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc0b3-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc0b3-108">See Also</span></span>  
 <span data-ttu-id="dc0b3-109">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="dc0b3-109">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="dc0b3-110">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="dc0b3-110">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="dc0b3-111">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="dc0b3-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

