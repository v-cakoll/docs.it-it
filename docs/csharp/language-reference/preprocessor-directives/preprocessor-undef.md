---
title: '#undef (Riferimenti per C#)'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 3957d58f61e51fab01618f5e1146be9cd0da58fd
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44185967"
---
# <a name="undef-c-reference"></a><span data-ttu-id="f420c-102">#undef (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f420c-102">#undef (C# Reference)</span></span>
<span data-ttu-id="f420c-103">`#undef` consente di rimuovere la definizione di un simbolo. In questo modo, se si usa il simbolo come espressione in una direttiva [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), l'espressione restituirà `false`.</span><span class="sxs-lookup"><span data-stu-id="f420c-103">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="f420c-104">Un simbolo può essere definito con la direttiva [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) o con l'opzione di compilazione [-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f420c-104">A symbol can be defined either with the [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) directive or the [-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="f420c-105">È necessario che la direttiva `#undef` venga visualizzata in un file prima di usare istruzioni che non siano anche direttive.</span><span class="sxs-lookup"><span data-stu-id="f420c-105">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f420c-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="f420c-106">Example</span></span>  

```csharp
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass
{  
    static void Main()
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```

<span data-ttu-id="f420c-107">**DEBUG non è stato definito**</span><span class="sxs-lookup"><span data-stu-id="f420c-107">**DEBUG is not defined**</span></span>

## <a name="see-also"></a><span data-ttu-id="f420c-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f420c-108">See Also</span></span>

- [<span data-ttu-id="f420c-109">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="f420c-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="f420c-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f420c-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f420c-111">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="f420c-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
