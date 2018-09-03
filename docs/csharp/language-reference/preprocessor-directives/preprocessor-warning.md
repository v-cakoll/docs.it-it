---
title: '#warning (Riferimenti per C#)'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 59ca63d5089e377627a9116f24f9a0a1681bb4b2
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932677"
---
# <a name="warning-c-reference"></a><span data-ttu-id="50053-102">#warning (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="50053-102">#warning (C# Reference)</span></span>
<span data-ttu-id="50053-103">`#warning` consente di generare l'avviso [CS1030](../../misc/cs1030.md) di livello uno del compilatore da una posizione specifica del codice.</span><span class="sxs-lookup"><span data-stu-id="50053-103">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="50053-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="50053-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="50053-105">Note</span><span class="sxs-lookup"><span data-stu-id="50053-105">Remarks</span></span>
 <span data-ttu-id="50053-106">La direttiva `#warning` viene generalmente usata nelle direttive condizionali.</span><span class="sxs-lookup"><span data-stu-id="50053-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="50053-107">È possibile anche generare un errore definito dall'utente tramite [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span><span class="sxs-lookup"><span data-stu-id="50053-107">It is also possible to generate a user-defined error with [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="50053-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="50053-108">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="50053-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50053-109">See Also</span></span>

- [<span data-ttu-id="50053-110">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="50053-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="50053-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="50053-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="50053-112">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="50053-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
