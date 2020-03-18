---
title: '#warning - Riferimenti per C#'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 38c3807a696599390667060d3bf374c68845fed0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715065"
---
# <a name="warning-c-reference"></a><span data-ttu-id="5182b-102">#warning (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="5182b-102">#warning (C# Reference)</span></span>
<span data-ttu-id="5182b-103">`#warning` consente di generare l'avviso [CS1030](../../misc/cs1030.md) di livello uno del compilatore da una posizione specifica del codice.</span><span class="sxs-lookup"><span data-stu-id="5182b-103">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="5182b-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5182b-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="5182b-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5182b-105">Remarks</span></span>
 <span data-ttu-id="5182b-106">La direttiva `#warning` viene generalmente usata nelle direttive condizionali.</span><span class="sxs-lookup"><span data-stu-id="5182b-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="5182b-107">È possibile anche generare un errore definito dall'utente tramite [#error](./preprocessor-error.md).</span><span class="sxs-lookup"><span data-stu-id="5182b-107">It is also possible to generate a user-defined error with [#error](./preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5182b-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="5182b-108">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="5182b-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5182b-109">See also</span></span>

- [<span data-ttu-id="5182b-110">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="5182b-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5182b-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="5182b-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5182b-112">Direttive per il preprocessore di C</span><span class="sxs-lookup"><span data-stu-id="5182b-112">C# Preprocessor Directives</span></span>](./index.md)
