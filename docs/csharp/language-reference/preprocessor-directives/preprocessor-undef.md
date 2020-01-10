---
title: '#undef - Riferimenti per C#'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 21923412aa178c3b86e94a54bd911130e48e4deb
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712442"
---
# <a name="undef-c-reference"></a><span data-ttu-id="4d5cc-102">#undef (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="4d5cc-102">#undef (C# Reference)</span></span>
<span data-ttu-id="4d5cc-103">`#undef` consente di rimuovere la definizione di un simbolo. In questo modo, se si usa il simbolo come espressione in una direttiva [#if](./preprocessor-if.md), l'espressione restituirà `false`.</span><span class="sxs-lookup"><span data-stu-id="4d5cc-103">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](./preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="4d5cc-104">Un simbolo può essere definito con la direttiva [#define](./preprocessor-define.md) o con l'opzione di compilazione [-define](../compiler-options/define-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="4d5cc-104">A symbol can be defined either with the [#define](./preprocessor-define.md) directive or the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="4d5cc-105">È necessario che la direttiva `#undef` venga visualizzata in un file prima di usare istruzioni che non siano anche direttive.</span><span class="sxs-lookup"><span data-stu-id="4d5cc-105">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d5cc-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d5cc-106">Example</span></span>  

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

<span data-ttu-id="4d5cc-107">**DEBUG non è stato definito**</span><span class="sxs-lookup"><span data-stu-id="4d5cc-107">**DEBUG is not defined**</span></span>

## <a name="see-also"></a><span data-ttu-id="4d5cc-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d5cc-108">See also</span></span>

- [<span data-ttu-id="4d5cc-109">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="4d5cc-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4d5cc-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4d5cc-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4d5cc-111">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="4d5cc-111">C# Preprocessor Directives</span></span>](./index.md)
