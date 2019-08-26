---
title: '#undef - Riferimenti per C#'
ms.custom: seodec18
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: fdf22e90be766e87e823a7f8cc27ea00c17d2bb5
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605591"
---
# <a name="undef-c-reference"></a><span data-ttu-id="f1af5-102">#undef (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f1af5-102">#undef (C# Reference)</span></span>
<span data-ttu-id="f1af5-103">`#undef` consente di rimuovere la definizione di un simbolo. In questo modo, se si usa il simbolo come espressione in una direttiva [#if](./preprocessor-if.md), l'espressione restituirà `false`.</span><span class="sxs-lookup"><span data-stu-id="f1af5-103">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](./preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="f1af5-104">Un simbolo può essere definito con la direttiva [#define](./preprocessor-define.md) o con l'opzione di compilazione [-define](../compiler-options/define-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f1af5-104">A symbol can be defined either with the [#define](./preprocessor-define.md) directive or the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="f1af5-105">È necessario che la direttiva `#undef` venga visualizzata in un file prima di usare istruzioni che non siano anche direttive.</span><span class="sxs-lookup"><span data-stu-id="f1af5-105">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1af5-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="f1af5-106">Example</span></span>  

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

<span data-ttu-id="f1af5-107">**DEBUG non è stato definito**</span><span class="sxs-lookup"><span data-stu-id="f1af5-107">**DEBUG is not defined**</span></span>

## <a name="see-also"></a><span data-ttu-id="f1af5-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1af5-108">See also</span></span>

- [<span data-ttu-id="f1af5-109">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="f1af5-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f1af5-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f1af5-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f1af5-111">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="f1af5-111">C# Preprocessor Directives</span></span>](./index.md)
