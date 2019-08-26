---
title: '#warning - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 3d09cd95ef4d53e3f11d9feb9675ebba22d6f857
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608520"
---
# <a name="warning-c-reference"></a><span data-ttu-id="e6e0d-102">#warning (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e6e0d-102">#warning (C# Reference)</span></span>
<span data-ttu-id="e6e0d-103">`#warning` consente di generare l'avviso [CS1030](../../misc/cs1030.md) di livello uno del compilatore da una posizione specifica del codice.</span><span class="sxs-lookup"><span data-stu-id="e6e0d-103">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="e6e0d-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e6e0d-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="e6e0d-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e6e0d-105">Remarks</span></span>
 <span data-ttu-id="e6e0d-106">La direttiva `#warning` viene generalmente usata nelle direttive condizionali.</span><span class="sxs-lookup"><span data-stu-id="e6e0d-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="e6e0d-107">È possibile anche generare un errore definito dall'utente tramite [#error](./preprocessor-error.md).</span><span class="sxs-lookup"><span data-stu-id="e6e0d-107">It is also possible to generate a user-defined error with [#error](./preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6e0d-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6e0d-108">Example</span></span>  

```csharp
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass
{  
    static void Main()
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  

## <a name="see-also"></a><span data-ttu-id="e6e0d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6e0d-109">See also</span></span>

- [<span data-ttu-id="e6e0d-110">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e6e0d-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e6e0d-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e6e0d-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e6e0d-112">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="e6e0d-112">C# Preprocessor Directives</span></span>](./index.md)
