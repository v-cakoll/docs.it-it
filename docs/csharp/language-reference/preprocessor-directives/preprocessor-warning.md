---
title: '#warning (Riferimenti per C#)'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: c56458e0100c23450655e48b2abfb346e18e0bb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268183"
---
# <a name="warning-c-reference"></a><span data-ttu-id="4c0ff-102">#warning (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="4c0ff-102">#warning (C# Reference)</span></span>
<span data-ttu-id="4c0ff-103">`#warning` consente di generare un avviso di livello uno da una posizione specifica del codice.</span><span class="sxs-lookup"><span data-stu-id="4c0ff-103">`#warning` lets you generate a level one warning from a specific location in your code.</span></span> <span data-ttu-id="4c0ff-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4c0ff-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="4c0ff-105">Note</span><span class="sxs-lookup"><span data-stu-id="4c0ff-105">Remarks</span></span>  
 <span data-ttu-id="4c0ff-106">La direttiva `#warning` viene generalmente usata nelle direttive condizionali.</span><span class="sxs-lookup"><span data-stu-id="4c0ff-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="4c0ff-107">È possibile anche generare un errore definito dall'utente tramite [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span><span class="sxs-lookup"><span data-stu-id="4c0ff-107">It is also possible to generate a user-defined error with [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c0ff-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c0ff-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4c0ff-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c0ff-109">See Also</span></span>  
 [<span data-ttu-id="4c0ff-110">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="4c0ff-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4c0ff-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4c0ff-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4c0ff-112">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="4c0ff-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
